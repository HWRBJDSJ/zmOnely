* �������Ŀ¼�ṹ
![image.png](https://upload-images.jianshu.io/upload_images/14467401-3afb713864b364f7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* ��������
	* reboot
	* shutdown -r now ��������(root�û�ʹ��)
	* shutdown -r 10 ʮ���Ӻ��Զ�����(root�û�ʹ��)
	* shutdown -c �����ͨ��shutdown�������������Ļ��������ô�����ȡ������
* �ػ�����
	* halt ���̹ػ�
	* poweroff ���̹ػ�
	* shutdown -h now ���̹ػ�(root�û�ʹ��)
	* shutdown -h 10 10���Ӻ��Զ��ػ�(root�û�ʹ��)
* Linux���м���
	* �����ļ�: /etc/inittab
	![���м���.png](https://upload-images.jianshu.io/upload_images/14467401-b2d7ca6f5802ecf9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* ����
		* runlevel �鿴���м���
		���չʾ��ʽ���л�ǰ�����м��� ��ǰ�����м���
		* init ��ʱ�л����м���
		eg: �����м����л���3
		init 3
* ��������
	* �鿴������
		* hostname �鿴������
	* �޸�������
		* hostname ���� ��ʱ�޸�(һ�����޸�,����֮����ԭ��)
		* vi /etc/hostname �����޸�
		ps:���س�֮������һ�����棬��"i",ʹ�䴦�ڿ��Ա�д״̬��д���µ����֣�":wq"�����˳�
	* ������������
		* ping [ѡ��] Ŀ������
		eg:
		ping www.baidu.com
		ps:��Ctrl+C��ֹ����
	* �鿴����ӿ���Ϣ
		* ifconfig �鿴���л����ӿڵ���Ϣ
		* ifconfig ����ӿ��� �鿴ָ������ӿ���Ϣ?????????????����
		ps:Ifconfig�����ã�ʹ��yum���� 
		yum install net-tools yum�����൱��Linuxϵͳ��Ӧ���̵꣬���ذ�װ������Ҫ�����,"install"��˼�ǰ�װ
	* ���÷���ǽ
		* service firewalld status �鿴����ǽ״̬
		* systemctl stop firewalld ��ʱ�ر�centos7����ǽ
		* systemctl disable firewalld ��ֹ��������
	* ����������Ϣ
		* vi /etc/sysconfig/network-scripts/ifcfg-ens33 ??????????
	* ����SELinux
		* �鿴SElinux�����ܷ��صĽ��������
		Enforcing��ǿ��ģʽ�������¼��ȫ��������ֹ������Ϊ
		Permissive������ģʽ�������¼��ȫ���浫����ֹ������Ϊ
		Disable���ر�
		* ��ǰ��Ч
		setenforce	[ Enforcing | Permissive| 1| 0 ]
		��������������ı�SELinux����״̬����Enforcing ��Permissive  ֮���л�,�ػ�����֮��ʧЧ
		* ������Ч
		�޸������ļ�/etc/selinux/config,��SELINUX=enforcing�޸�ΪSELINUX=disabled������Ч

	
		
		
* �������������ͼ	
![�������������ͼ.png](https://upload-images.jianshu.io/upload_images/14467401-9a5e668357b59663.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

	

	
		
