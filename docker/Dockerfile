FROM python
ENV COMPOSER_MAIL_PARSER_PATH=/tmp/composer_mailparser
ARG BRANCH=develop
RUN apt-get -yqq update; \
    apt-get -yqq --no-install-recommends install libemail-outlook-message-perl; \
    apt-get clean; \
    rm -rf /var/lib/apt/lists/*; \
    git clone -b $BRANCH --single-branch https://github.com/ScaleFactor/composer-mail-parser.git $COMPOSER_MAIL_PARSER_PATH; \
    cd $COMPOSER_MAIL_PARSER_PATH && python setup.py install
ENTRYPOINT ["composer_mailparser"]
CMD ["-h"]
