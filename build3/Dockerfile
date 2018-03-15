FROM linode/lamp

ENV DRUPAL_VERSION 8.5.0

# Placing Drupal goods into /var/www
RUN apt-get update && apt-get install -y wget
RUN wget https://ftp.drupal.org/files/projects/drupal-${DRUPAL_VERSION}.tar.gz && tar -xvzf drupal-${DRUPAL_VERSION}.tar.gz
RUN rm -r drupal-${DRUPAL_VERSION}.tar.gz
RUN mv drupal-${DRUPAL_VERSION} /var/www/drupal

# Adding apache config file
ADD ./drupal.conf /etc/apache2/sites-available/drupal.conf
RUN ln -s /etc/apache2/sites-available/drupal.conf /etc/apache2/sites-enabled/drupal.conf
RUN rm /etc/apache2/sites-enabled/example.com.conf

# Init apache
CMD /usr/sbin/apache2ctl -D FOREGROUND
