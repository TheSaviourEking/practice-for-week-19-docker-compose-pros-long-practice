FROM drupal:8.6

# RUN apt-get update \ 
#     && apt-get install -y git \
#     && rm -rf /var/lib/apt/lists/* 

RUN sed -i 's/deb.debian.org/archive.debian.org/g' /etc/apt/sources.list \
    && sed -i 's/security.debian.org/archive.debian.org/g' /etc/apt/sources.list \
    && sed -i '/stretch-updates/d' /etc/apt/sources.list \
    && apt-get update \ 
    && apt-get install -y git \
    && rm -rf /var/lib/apt/lists/* 

WORKDIR /var/www/html/themes

RUN git clone --branch 8.x-3.x --single-branch --depth 1 https://git.drupal.org/project/bootstrap.git

RUN chown -R www-data:www-data bootstrap
