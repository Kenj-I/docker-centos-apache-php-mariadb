FROM centos:latest

#Yum update
RUN yum -y update && yum clean all

# timezone
# RUN timedatectl set-timezone Asia/Tokyo
ENV TZ=Asia/Tokyo

#locale
RUN rm -f /etc/rpm/macros.image-language-conf && \
    sed -i '/^override_install_langs=/d' /etc/yum.conf && \
    yum -y reinstall glibc-common && \
    yum clean all

ENV LANG="en_US.UTF-8" \
    LANGUAGE="en_US:en" \
    LC_ALL="en_US.UTF-8"

CMD bash

#Yum install
RUN yum -y install \
		wget \
		curl \
		httpd

# Install & Add repo
RUN yum -y install epel-release
RUN rpm -Uvh http://rpms.famillecollet.com/enterprise/remi-release-7.rpm

# Install PHP71 & Apache
RUN yum install \
		--enablerepo=remi,remi-php71 \
		-y \
		php \
		php-devel \
		php-mbstring \
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

COPY httpd_foreground /usr/local/bin/httpd_foreground
RUN chmod a+x /usr/local/bin/httpd_foreground
CMD ["/usr/local/bin/httpd_foreground"]
