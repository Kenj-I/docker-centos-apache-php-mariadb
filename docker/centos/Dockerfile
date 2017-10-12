FROM centos:latest

# timezone
# RUN timedatectl set-timezone Asia/Tokyo
ENV TZ=Asia/Tokyo

#Yum update
RUN yum -y update

#Yum install
RUN yum -y install \
		wget \
		curl \
		httpd

# Install & Add repo
RUN yum -y install epel-release
RUN rpm -Uvh http://rpms.famillecollet.com/enterprise/remi-release-7.rpm

# Install PHP56
# RUN yum install --enablerepo=remi,remi-php56 -y \

# Install PHP71
RUN yum install --enablerepo=remi,remi-php71 -y \
		php \
		php-devel \
		php-mbstring
		php-pdo \
		php-gd \
		php-mysql \
		php-curl \
		php-posix \
		php-xml \
		php-pecl-apc \
		php-bcmath

# expose
EXPOSE 80

# Clear yum cache
RUN yum clean all

ADD httpd.conf /etc/httpd/conf/httpd.conf
ADD vhosts.conf /etc/httpd/conf.d/

CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]
