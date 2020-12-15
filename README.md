# auto-server
  docker-compose ʹ�� nginx-proxy ��һ̨С���²�������Ŀ ֧��ssl��
  ����Ŀ��Ŀ����Ϊ������ʱ�򷽱�,˳������¼,*����֤���в����������Ҹ߿���*��

## Ŀ¼
   use_ssl��֧��docker-composeһ�����ʹ��ssl
   normal��һЩ�˲�ϲ��https�����������cf���� Let��s Encrypt ����֤�������⡣��������������Ŀ¼�µ�
   tool: һЩ����������,ֱ��ʹ��ip���ʻ���ֱ��ʹ��docker�ܵĶ���

## ����
   use_ssl/nginx-proxy ���� normal/nginx-proxy Ŀ¼�µ�docker-compose�������������google image���������
   ���ֻ��ʹ�ÿ���ֱ������

## ʹ�ò���
   #### 1.����docker �� docker-compose ������
�������: [docker�ֲ�](https:://yeasy.gitbook.io/docker_practice/install "Markdown")��
   #### 2.����һ�� Docker network
    docker network create nginx-proxy
   #### 3.����ӦĿ¼���� nginx-proxy
    cd auto-server\use_ssl\nginx-proxy
    or
    cd auto-server\normal\nginx
    docker-compose up -d
   #### 4.�޸Ĳ�������Ҫ�����ķ����docker-compose�еĲ���
    ��bitwarden�µ�
      - VIRTUAL_HOST=example.test.com
      - LETSENCRYPT_HOST=example.test.com
      - DEFAULT_EMAIL=xxx@gmail.com
    ����Ӧ�������������޸�,��ʹ��ssl������� ֻ��Ҫ�޸�VIRTUAL_HOST
	һЩ��������������Ҫ�������ã��������ļ��е�ע��

## ��֪������
������cloudflare����https�����ϸ�������,��ʹ��use_ssl�еķ������п��ܳ���ssl���鲻�������,ʵ�������ʹ�����ģʽ��������docker-compose��
�ٸĳ��ϸ�ģʽ/ֱ��ʹ��normal��ʽ����cf���ó����ģʽ/cloudflareʹ���ϸ�ģʽ����dns�������㹻�õ��������Ȼ����ֱ��ʹ��use_ssl��������Ҳ��Ϊʲôһ��ʼ��û�з�����������ԭ��

## �����Ų��һЩ��������
������������Ŀ�����в���������ʹ��docker ps -a
��ѯ����Ӧdocker������id ��ʹ�� docker logs -f ����id�ķ�ʽ���Բ�ѯ����������������־�������������jrcs/letsencrypt-nginx-proxy-companionû��ǩ���ɹ�����ϸ����������issue������ֱ��ʹ��normal��ʽ

## �Ѿ�֧�ֵ���Ŀ
	bitwarden
	chevereto
	gitlab
	file_server(https://files.photo.gallery/demo)
	wordpress
	shadowsoks
	resilio
	syncthing
	transmission

## ����
 #### http://einverne.github.io/post/2017/02/docker-nginx-host-multiple-websites.html
 ������ƪ���¿�ʼ���ڵ�
 ####  https://blog.csdn.net/jiangyu1013/article/details/80881097
 nginx-proxy ��ʹ�õ�docker�����ݾ�û���Զ�����أ���Ҫ�������ݾ�����ѿ��Բ�����ƪ

