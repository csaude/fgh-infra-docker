FROM alpine:3.4

ENV MYSQL_ROOT_PASSWORD=root
ENV MYSQL_DATABASE=jiradb
ENV MYSQL_USER=jira
ENV MYSQL_PASSWORD=fghjira@2017
ENV MYSQL_DATA_DIRECTORY=/opt/data/system/mysql

ADD jira-mysql.cnf /root/.my.cnf
ADD backup /usr/bin/backup
ADD localtime /etc/localtime

RUN apk add --update mariadb mariadb-client; \
    rm /usr/bin/mysql_client_test_embedded; \
    rm /usr/bin/mysqltest; \
    rm /usr/bin/mysqltest_embedded;

COPY run.sh /run.sh

VOLUME /opt/data

EXPOSE 3306

CMD ["/run.sh"]