FROM postgres:9.6.17
RUN localedef -i fr_FR -c -f UTF-8 -A /usr/share/locale/locale.alias fr_FR.UTF-8
ENV LANG fr_FR.utf8

ARG USER_ID
ARG GROUP_ID

RUN userdel -f postgres &&\
    if getent group postgres ; then groupdel postgres; fi &&\
    groupadd -g ${USER_ID} postgres &&\
    useradd -l -u ${GROUP_ID} -g postgres -G sudo postgres -s /bin/bash &&\
    install -d -m 0755 -o postgres -g postgres /var/lib/postgresql


