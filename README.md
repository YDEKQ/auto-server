# auto-server
  docker-compose ʹ�� nginx-proxy ��һ̨С���²�������Ŀ ֧��ssl��
  ����Ŀ��Ŀ����Ϊ������ʱ�򷽱�,˳������¼,*����֤���в����������Ҹ߿���*��

## Ŀ¼
   use_ssl��֧��docker-composeһ�����ʹ��ssl
   normal��һЩ�˲�ϲ��https�����������cf���� Let��s Encrypt ����֤�������⡣��������������Ŀ¼�µ�
   ������Ŀ¼��ѡһ��ʹ��

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
    
## ����
 -��+*��http://einverne.github.io/post/2017/02/docker-nginx-host-multiple-websites.html
 ������ƪ���¿�ʼ���ڵ�
 -��+*��https://blog.csdn.net/jiangyu1013/article/details/80881097
 nginx-proxy ��ʹ�õ�docker�����ݾ�û���Զ�����أ���Ҫ�������ݾ�����ѿ��Բ�����ƪ

