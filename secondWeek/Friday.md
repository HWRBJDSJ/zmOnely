##hadoop��ȫ�ֲ�ʽ��������ʹ��
* ׼������
	* �½�һ̨���������Ϊnamenodeʹ��
	```
	1.����һ��hadoop�û�
	2.visudo ��hadoop�û�����sudo
	3.����vim*    yum install -y vim*
	4.����net-tools
	5.���ùرշ���ǽ
	6.��jdk��hadoopѹ��������/home/hadoop��
	7.�������  
	(�������zl8�Ŀ��գ���Ϊ"����ʼ�����"�����������δ�رշ���ǽ��)
	```
	* ��¡��������Ϊdatanodeʹ��
		* ps��ֻ��¡�ã���Ҫ�����κ����ã���namenode�����ͬ������
* ��ʼ����
	* ���ú�hadoopα�ֲ�ʽ 
		* (���岽��ο�secondWeek/Thursday�ʼ�)
	* ��namenode��
	```
	1.�����������ļ�����datanode
	scp Ҫ��������� Ҫ�������Ե��û���@Ҫ�����ĵ���ip:Ҫ������̨���Ե�λ��
	(scp -r ~/hadoop2.7.3/etc/hadoop/ hadoop@172.18.24.2:/home/hadoop/hadoop-2.7.3/etc/)
	2.hadoop-daemon.sh start namenode ����namenode
	3.jps�鿴�Ƿ�����
	4.ȥ��ҳ���� namenodeip��50070
	ps�����رգ�����ʲ���
	```
	* ��datanode��
	```
	1.�������ͼ����뵽���жԻ�
	2.�Ƚ�namenode��/etc/profile������jdk��hadoop��������临��ճ����datanode����Ӧ�ļ���
	3.hadoop-daemon.sh start datanode
	4.jps�鿴�Ƿ�����
	```
* �����������⼰�������
	* �������ҳ�в鿴"���ŵĽڵ���һֱΪ0"
	```
	��namenode�в���
	1.cd /home/hadoop/dfs/data/current
	2.ls
	3.�鿴BP...
	4.vim VERSION���鿴ID�Ƿ�ƥ��
	```
	![VERSION.png](https://upload-images.jianshu.io/upload_images/14467401-b922f74a8a92188a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	```
	5.��ƥ�䣬������һ��
	6.��namenode��datanode���ر�
	hadoop-daemon.sh stop namenode(datanode)
	7.cd /home/hadoop/hadoop-2.7.3/etc/hadoop
	8.vim slaves ��datanode��ipд�����棬����ע��
	9.start-dfs.sh 
	(Ч����namenode������datanodeҲ��֮������ֻ�����namenode����)
	10.�鿴��־Ѱ�Ҵ���Դ
	cat ~/hadoop-2.7.3/logs/hadoop-hadoop-datanode-localhost.localdomain.log
	11.sudo vim /etc/hosts ��������Ϣ���룬��ͼ
	```
	![hosts.png](https://upload-images.jianshu.io/upload_images/14467401-aa8f22e995f29ac3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	```
	12.�����󣬲鿴��ҳ��"���ŵĽڵ�"
	   ����hdfs dfsadmin -report����
	```
	
	* ��������
	```
	��namenode�в���
	1.ssh-keygen  ������Կ
	2.ssh-copy-id ��Ҫ���ܵ��û���@��Ҫ���ܵ�ip
	ssh-copy-id hadoop@172.18.24.2
	ps��ע�⿴��Ҫ��������ĸ��û������룬������datanode�Ľ������ܲ���
	3.��namenode����
	cat .ssh/id_rsa.pub >> .ssh/authorized_keys
	4.ll -al ���鿴�����ļ�
	5.cd .ssh
	6.ll �����Բ鿴id_rsa.pub
	7.���ܲ�����ɺ󣬽����������
	
	* ������ǵ��Ȳ鿴��־��~~
	* cat ~/hadoop-2.7.3/logs/hadoop-hadoop-datanode-localhost.localdomain.log
	
		