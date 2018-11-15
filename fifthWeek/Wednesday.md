## Hive��jdbc�ӿڵ�һЩ����
* ����jdbc�ӿڵķ���
	* beeline
	* !connection jdbc:hive2://localhost:10000
	* �ٸ���һ���Ự��hiveserver2�����ִ�״̬����
* �������ݿ�
	* create database ���ݿ���;
* չʾ�������ݿ�
	* show databases;
* �����ڲ���
	* create table ����(id int,name string) 
	* row format delimited fields terminated by '\t';
* �����ⲿ��
	* create external table exzl(id int,name string)
	* row format delimited fields terminated by '\t';
* ����������
	* create table ����(id int,name string) 
	* partitioned by(gender string) 
	* row format delimited fields terminated by '\t';
	* ps���൱���ڱ����ַ���С�������ǿ��Լ�����һ������ʱ�Ĳ�ѯ��������
	  ������ѯЧ�ʷ�������ֻ����һ��ģ����Դ���������ʽ����С��������
	  С����������
	* create table zltime(id int,name string)
	* partitioned by(year string,month string)
	* row format delimited fields terminated by '\t';
	* ![33.png](https://upload-images.jianshu.io/upload_images/14467401-08f1643e9678bba9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* ���ڴ������һЩ
	* ![ͼƬ1.png](https://upload-images.jianshu.io/upload_images/14467401-e54e6b40e731a323.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* location ָ�������ļ���ŵ�hdfsĿ¼����hdfs�ϵ��ļ���·������
		* create external table ����(id int,name string)
		* row format delimited fields terminated by '\t'
		* location /dbdata/;
	* �ڲ�����ⲿ�������
	```
	1.ͨ��external�ؼ�������������
	2.��Ϊ�ⲿ��������������ⲿ�����ݣ�Ҳ��ϣ����ԭʼ���ݼ����ƻ���
	  ����Ҫ���location��ָ���ⲿ��Ҫ��ȡ���ݵ�λ��
	3.ɾ����������ڲ����Ὣ����������ɾ������������ⲿ��ֻ�Ὣ
	  ��Ĺ�����Ϣɾ��������ָ��λ���µ�����û�κ�Ӱ�죬��Ȼ����˵��
	  ����Ͳ���ʹ��location
	```
* �鿴�����
	* show partitions ����;
* �鿴���еı�
	* show tables;
* �鿴��ṹ
	* desc ����;
	* ![desc.png](https://upload-images.jianshu.io/upload_images/14467401-5bb24382830fe47b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* ��ձ�
	* truncate table ����;
* ��ѯ������
	* select * from ����;
	* select count(*) from man;
	* ![33.png](https://upload-images.jianshu.io/upload_images/14467401-d09f934ce6a01aed.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

* �������ݣ�
	* ��hdfs�е�������
		* load data inpath 'hdfs�ϵ�·��' into table ����;
	* �ӱ��ص�������
		* load data local inpath '����·��' into table ����;
	* ps��load���ļ��൱�ڼ��У����ʹ���� OVERWRITE �ؼ��֣���Ŀ������߷������е����ݻᱻ����	
* �޸ı���
	* alter table ���� rename to �±���;
* ����/�ı�/�滻��
	* alter table ���� add columns (sex string);
	* alter table ���� change sex gender string;
	* alter table ���� replace columns (id string,name string);
	* ps���滻�������н�֮ǰ���еĶ��滻��
* ɾ����
	* drop table ����;
* ɾ������
	* alter table ���� drop partition(sex='man');
* ���ӷ���
	* alter table ���� add partition(sex='man');
* ��������
	* ��ͨ����
		* insert into ���� values('1','zl');
	* ���������������ӵ�һ���ձ�
		* insert into ���� select * from man;
	* ��һ�ű�����ֱ�Ӳ����±���
		* create table �±��� as select * from man;
* ��̬����
	* insert into zlpart partition(gender='woman')
	* select id,name,gender from persons;
* ��̬����
	* ʹ�ó�����
		* ��������ݽ��з�����ʱ�������õ�������ȴδ�����Ѿ��ֺ������ļ���
		  ������ֱ��load data�����ã���ʱ�;���ʹ�ö�̬������������������
		  �����ļ��������ݼ��뵽���·ݷ����ı���
		  
		* ![�����ļ�.png](https://upload-images.jianshu.io/upload_images/14467401-aee73aaf0ffb31e9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
 
	* ʵ�֣�
		```
		1.�����ҵ����ݴ���һ�����У�
		2.������Ӧ�ķ�����
		  create table zlpart(id int,name string) 
		  partitioned by (gender string)
		  row format delimited fields terminated by '\t';
		3.�������̬��������
		  insert into zlpart partition(gender)
		  select id,name,gender from persons;
		3.1���Ҫ���ж�̬�������Ͳ�Ҫ��partition(month)�и��������ù̶�ֵ��
		   ��Ȼ�Ͳ��Ƕ�̬������
		3.2Ĭ��ʹ�õ����ϸ�ģʽ��������̬��������Ҫ��������ִ��
		   set hive.exec.dynamic.partition.mode=nonstrict
		3.3ʹ�ö�̬�����Ὣ��ѯ����������һ����Ϊ��������������select��ѯҪע��
		```
 		
		

	