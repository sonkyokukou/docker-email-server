docker-email-server
===================

An email server with postfix and dovecot, as a docker container.

## Build

    docker build -t yuanying/email-server .

## Run

    docker run -d --link mysql:mysql \
        -e "POSTFIX_MYSQL_PASSWORD=postfixpassword" \
        -e "POSTFIXADMIN_SETUP_PASSWORD=POSTFIXADMIN_SETUP_PASSWORD" \
        -h 'mail.fraction.jp' \
        -v /home/vmail:/var/vmail \
        -p 25:25 -p 993:993 -p 8080:8080 \
        yuanying/email-server
