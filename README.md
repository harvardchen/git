# Git Origin Source Code
This is the origin source code of git(v0.99), i'm very interested in 
the principle and workflow of it. Maybe I will take some notes here on
reading the source code. Have fun!(the origin README is [here](./linus.README))

## Source Code
linus������һ��stupid content tracker,�������ԭ��ͳ�ʼ������������ȷ��������
SHA(Secure Hash Alogorithm)��һ������Ҫ�ĸ��ͨ��SHAֵ�ж��ļ��Ƿ�仯��tree��commit
Ҳͨ��Object�ļ��洢������ÿ���ļ���tree��commitҲ��ͨ��SHAֵ��Ψһ��ʶ��

![init commit files](./img/src.png)


## The Object Database(SHA1 FILE DIRECTORY)
����һ�����ڴ洢SHI1�ļ����ļ����ݿ⣬��ʵ������ֻ��һ���ļ��У����ڴ�����ύ���ļ����ļ�����Metadata��Ϣ��Blob���ݣ�����Zlibѹ�������SHA1����SHA1��ǰ2λ��Ϊ���ļ���������38λ��Ϊ�ļ�����Ŀ¼��ͼ��ʾ��

![object directory](./img/object.png)

�����ŵ��ļ��������֣�tree��blob��commit.

### blob
blob�ļ���ָ������ļ����ݣ����������ύ���ļ���Blob�ļ��ᱻѹ����Ȼ�����SHA1ֵ����������ļ�������û�з����仯����ô�Ͳ�������µ�Blob�ļ�����Ϊ���������SHA1����ͬ�ģ���SHA1ֵ��������ʵ�ʵĴ��·����

### tree
tree�ļ��д�ŵ������ύ���ļ��б�ÿһ����������¼��һ���ļ����������ļ���Ȩ�ޡ�·������SHA1ֵ��������ܹ����ڱ���ÿһ���ύ�ľ������ݣ�ͨ����ѯtree�ļ�������֪���ô��ύʱ�����е������ļ���Ȼ�����ÿһ���ļ���SHA1��������object database�����������ļ��������ʹﵽ�˱���ÿһ���ύ�ľ������ݵ�Ŀ�ġ�

### commit
commit�ļ������ڼ�¼ÿһ���ύ���ļ��������������У�tree��parents��author��committer��changelog������tree��ָ���ڱ���˴��ύ��tree�ļ���Parents��ָ�˴��ύ�ĸ���֧����Щ��Ҳ�Ƕ�Ӧ��tree�ļ���Author��committer��changelog���ύ�ļ�¼��Ϣ��

## ʹ��
1. ʹ��init-db��ʼ������Ŀ¼��������git init�����á�
2. ��Ŀ��д����ɾ�ĸ����ļ��ȵȡ�
3. ʹ��update-cache [file-path]����������������С��������һ��index�ļ������ļ����ڱ��浱ǰ��cache��
4. ʹ��write-tree�ύ�����еĸ��ġ��������һ��tree�ļ�����ǰ��cache�е��ļ���д�뵽tree�ļ���ȥ���������᷵��tree�ļ���sha1ֵ��
5. ʹ��commit-tree <tree-sha1> [-p parent-sha1] < changelog�ύ��θ��ġ����û��parent����Ϣ���ͻᵱ���ǵ�һ���ύ���еĻ��ͱ�ʾ�Ĵ��ύ����parent�������ύ�ġ�����Ҳֻ��һ����Ϣ�ļ�¼����ʵ���������Ƿ����child-parent�Ĺ�ϵ��
6. ��������show-diff�������Ƚϵ�ǰ����Ŀ¼�µ��ļ���cache�У���index�ļ�����¼���ļ�������
7. ��������cat-file <SHA1>���鿴ĳ��sha1�ļ���������һ��TEMP�ļ����������SHA1�ļ��е����ݡ�


## Summary
Now i got an overview about the principle and workflow of git, it's really simple and stupid.
And i mainly refer to this [artical](http://blog.csdn.net/gsyzhu/article/details/38065765).
