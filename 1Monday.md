git�ֿ��ʹ��
һ����git�е�׼������
1.����һ���²ֿ⣬����������**.github.io��ʽ
2.ѡ��һ������
����git Bash����Ĳ���
1.cd ~
��ת����ǰ�û���homeĿ¼
2.pwd
�鿴��ǰ·��
eg;
/c/Users/Administrator
3.cd Desktop
���뵽������
ps������De����tab���Զ���ȫ
![1.png](https://upload-images.jianshu.io/upload_images/14467401-d7949fcfdd63dd41.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
4.ssh-keygen -t rsa -C "������"
������Կ��C:\Users\Administrator\.ssh��Ȼ���id_rsa.pub�������еĹ�Կ���ƣ�
��git�û���setting�µ�SSH and GPG keys������һ���µ�SSHԿ�ף�����Կ����
![2.png](https://upload-images.jianshu.io/upload_images/14467401-c4285772bfab7422.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
5.git clone ������
��������ȡ����git�ֿ⣬���Clone or download��ѡ��ʹ��SSH�����Ʋ�����
eg��
git@github.com:zmOnely/1Monday.github.io.git
![3.png](https://upload-images.jianshu.io/upload_images/14467401-deae08a7a18aa3bc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
6.ls
�鿴�����µ��ļ�
7.cd �ֿ���
���뵽�ֿ���
eg��
cd zmOnely.github.io/
8.ls
�鿴һ�²ֿ��е��ļ�
![4.png](https://upload-images.jianshu.io/upload_images/14467401-aee10feb8f2a86d8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

9.git status
�鿴״̬
10.touch �ļ���.md
�ڲֿ��д���һ���ļ�
eg��touch 1Monday.md
11.git status
�鿴������״̬
12.git add 1Monday.md
���´������ļ���ʱ��ӵ�������
![5.png](https://upload-images.jianshu.io/upload_images/14467401-79ba26d7bcbb42f3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
13.git status
�鿴״̬
14.git config --global user.email "����"
��¼����
15.git config --global user.name "�ļ���"
![6.png](https://upload-images.jianshu.io/upload_images/14467401-8874fd05f89c957a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
16.git commit -m "��"
�ύ
![7.png](https://upload-images.jianshu.io/upload_images/14467401-d12d3938d8957219.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
17.git push -u origin master
���ļ�ȫ���ŵ��ֿ���
![8.png](https://upload-images.jianshu.io/upload_images/14467401-15ab741b6861937e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)