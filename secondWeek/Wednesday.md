### ����һ
* �Զ���װjava����(���°�������)
	* cd /home/hadoop/bin
	* > creatjava.sh
	* vim creatjava.sh
	* ��vim��д����
	```
	#!/bin/bash
	echo "����ҳ������ѹ����"
	wget --no-check-certificate --no-cookies --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u191-b12/2787e4a523244c269598db4e85c51e0c/jdk-8u191-linux-x64.tar.gz
	echo "��ѹ�ļ���"
	javatar=$(ls | sed -n '/jdk.*gz$/p')
	tar -zxf $javatar
	rm -rf $javatar
	echo "���û�������"
	jdkname=$(ls | grep jdk)
	cd $jdkname
	javaname=$(pwd)
	echo "export JAVA_HOME=$javaname" >> /etc/profile
	echo 'export PATH=$PATH:$JAVA_HOME/bin' >> /etc/profile
	echo 'export CLASSPATH=$:CLASSPATH:$JAVA_HOME/lib/' >>/etc/profile
	. /etc/profile
	```




