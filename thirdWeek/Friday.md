### MapReduce��ʹ��
* ps�����Ǹ����Ĺ����������������ģ�
* ��һ��ͳ���ֻ��ţ���������
* ����
	* ��һ��
		* ����һ���࣬дmap����
		* ![map.png](https://upload-images.jianshu.io/upload_images/14467401-c737c6bbc50b7d4c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* �ڶ���
		* ����һ���࣬дreduce����
		* ![reduce.png](https://upload-images.jianshu.io/upload_images/14467401-8799891fdee9ff89.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* ������
		* �޸�main��
		* ![main.png](https://upload-images.jianshu.io/upload_images/14467401-0ca6adb273616393.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* ������ͳ���ֻ��ţ���������������������������
* ����
	* ��һ�� 
		* Ҫ�������ݽ��н�ģ���׳ƴ���ʵ����
			* ��׼��javaBean��+ toString()���� + [�вι���]
	* �ڶ���
		* ����һ���࣬дmap����
			* Ҫ����map�������β���ôд��map����������ô�����ݽ����и�ɸѡ
			* �����ݷ����Զ����ʵ���൱��
			* ���Ǻ�map���������key��value�������д�����
			* ps��
				* �Զ����ʵ����һ��Ҫ֧�����л�serializale��serializale��java�ṩ�����л�������
				* hadoop������ʹ��hadoop�����ṩ��writableComparable�ӿ���ʵ�����л��뷴���л���
				  �˽ӿ���Ҫʵ��write����д���ļ���readFields�������ļ��ж�ȡ�ķ�����������
				  reduce�׶λ�ȡ�������ݣ���һ��Ҫע��readFields���������е���read������ʱ��һ��
				  Ҫ����д���˳����ж�ȡ�����������Խ��и�ֵ������ᵼ�����������ݴ���			      
		* ![map.png](https://upload-images.jianshu.io/upload_images/14467401-71b35c66577f8058.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* ������
		* ����һ���࣬дreduce����
			* reduce����Ҫע���βκ����λ�ã��Լ���driver����Ӧ��reduceҪ���������
			* ��map������������ѭ�����
		* ![reduce.png](https://upload-images.jianshu.io/upload_images/14467401-40c232bea8638b43.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	* ���Ĳ�
		* �޸�main��
			* ע�������Ӧ��
		* ![main.png](https://upload-images.jianshu.io/upload_images/14467401-241105953f649dbe.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
		
		
			