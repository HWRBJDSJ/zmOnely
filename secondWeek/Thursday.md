### ����java����
* ����������jdkѹ����
	* wget --no-check-certificate --no-cookies --header "Cookie: oraclelicense=accept-  securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u191-  b12/2787e4a523244c269598db4e85c51e0c/jdk-8u191-linux-x64.tar.gz
* ������ȡ�����ص�jar������
	* jdktar=$(ls | sed -n '/jdk.*gz$/p')
* ��ѹjar��
	* tar -zxf $jdktar
* ��ѹ֮��ɾ��ѹ����
	* rm -rf $jdktar
* ȡ����ѹ��İ�������
	* jdkname=$(ls | grep jdk)
* ����jdk����
	* cd $jdkname
* ȡ��������ڵ�·��
	* javahome=$(pwd)
* ���û���
	* echo "javahome:"$javahome
		* echo "export JAVA_HOME=$javahome" >> /etc/profile
		* echo 'export PATH=$PATH:$JAVA_HOME/bin' >> /etc/profile
		* echo 'export CLASSPATH=$:CLASSPATH:$JAVA_HOME/lib/' >> /etc/profile
		* . /etc/profile
* �˳�vim������.sh����
 
### ���õ���hadoop
* java����  ����jdk
* ��hadoop��jar.gz����ѹ
* ����ѹ��İ��Ƶ�hadoop�û��� ~ Ŀ¼��
* ���� hadoop��ѹ��İ�
* ����bin��ִ��hadoop������ִ�У��ɹ���
	* ���� ~ Ŀ¼��ִ��hadoop���ʧ��
* ����hdoop��������
* ���� ~ Ŀ¼
* vim .bash_profile���޸Ĵ��ļ�
	* export HADOOP_HOME=/home/hadoop/hadoop-2.7.3
	* PATH=$PATH:$HOME/bin:$HADOOP_HOME/bin:$HADOOP_HOME/sbin
* ִ��hadoop ������
* �� ~ ��ִ��hadoop�����⣬�ɹ�
	* ps������ʵ��hadoop�û������ø���

### ���� hadoopα�ֲ�ʽ
* �رշ���ǽ
	* systemctl stop firewalld
	* systemctl status firewalld �鿴�Ƿ�ر� 
	* ps����������Ҫ���ùرգ�systemctl disable firewalld
* �������굥��hadoop�Ļ����ϼ�������
* cd ~/hadoop-2.7.3/etc/hadoop/
* �����Ĵ��ļ�
	* vim core-site.xml 
		* <property>  
			* <name>hadoop.tmp.dir</name>  
			* <value>/usr/local/hadoop/tmp</value>
		* </property>  
		* <property>  
			* <name>fs.defaultFS</name>  
			* <value>hdfs://192.168.146.128:9000</value>  
		* </property> 

	* vim hdfs-site.xml 
		* <!-- <property>    
			* <name>dfs.replication</name>    
			* <value>1</value>    
		* </property> -->   
		* <property>    
			* <name>dfs.namenode.name.dir</name>    
			* <value>file:/usr/local/hadoop/dfs/name</value>    
		* </property>    
		* <property>    
			* <name>dfs.datanode.data.dir</name>    
			* <value>file:/usr/local/hadoop/dfs/data</value>    
		 * </property>

	* vim yarn-site.xml 
		* <property>  
			* <name>mapreduce.framework.name</name>  
			* <value>yarn</value>  
		* </property>   
		* <property>  
			* <name>yarn.nodemanager.aux-services</name>  
			* <value>mapreduce_shuffle</value>  
		* </property>
* cp mapred-site.xml.template mapred-site.xml
* vim mapred-site.xml
	* <property>
		* <name>mapreduce.framework.name</name>
		* <value>yarn</value>
    * </property>
* ��ʽ��
	* hadoop namenode -format
* ����
	* vim hadoop-env.sh
    * ��JAVA_HOME��Ϊ(echo $JAVA_HOME)�����н��
* ����
	* start-all.sh
* ����Ƿ�ɹ� jps
	* ![jps.png](https://upload-images.jianshu.io/upload_images/14467401-5f8a3a7e807fd295.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

* �˿ڱ�����ռ�õĽ������ 
	* ��һ�����鿴�˿��Ƿ�ռ�� 
		* netstat -tunlp|grep �˿ں�
	* �ڶ����������ռ�ã����ռ��
		* kill -9 ���̺� (pid ���̺�)
* Ȩ�޲����Ľ������
	* �鿴�Ƿ�֮ǰ��root�û���¼����sudo����
	* �鿴��־ 
		* cd /home/hadoop/hadoop-2.7.3/logs












