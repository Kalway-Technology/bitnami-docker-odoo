FROM bitnami/minideb-extras:jessie-r24
LABEL maintainer "Bitnami <containers@bitnami.com>"

# Install required system packages and dependencies
RUN install_packages ghostscript imagemagick libbsd0 libbz2-1.0 libc6 libedit2 libffi6 libgcc1 libgcrypt20 libgmp10 libgnutls-deb0-28 libgpg-error0 libhogweed2 libldap-2.4-2 liblzma5 libmysqlclient18 libncurses5 libnettle4 libp11-kit0 libpq5 libreadline6 libsasl2-2 libsqlite3-0 libssl1.0.0 libstdc++6 libtasn1-6 libtinfo5 libxml2 libxslt1.1 zlib1g
RUN bitnami-pkg install python-3.6.4-0 --checksum efbf391a62624a6a6f0d33fa350aeefb24fc1d4e966843d323715a76577004ef
RUN bitnami-pkg install postgresql-client-10.2.0-0 --checksum d09f6674a2e48f14f22c8f9ff6eff1d43711e745c6a24c618ef2a8bcb6f3e662
RUN bitnami-pkg install node-7.10.1-1 --checksum 7f326edcdc911932655af0283eb29e1f72d28f1e4f9a7cf5869618fff135cbdb
RUN bitnami-pkg unpack odoo-11.0.20180115-0 --checksum 3da6607d4177f0d3921d795f76f63ec08e0e89166023cd8298633990f7247a5d

COPY rootfs /

ENV BITNAMI_APP_NAME="odoo" \
    BITNAMI_IMAGE_VERSION="11.0.20180115-r1" \
    ODOO_EMAIL="user@example.com" \
    ODOO_PASSWORD="bitnami" \
    PATH="/opt/bitnami/python/bin:/opt/bitnami/postgresql/bin:/opt/bitnami/node/bin:$PATH" \
    POSTGRESQL_HOST="postgresql" \
    POSTGRESQL_PASSWORD="" \
    POSTGRESQL_PORT_NUMBER="5432" \
    POSTGRESQL_USER="postgres" \
    SMTP_HOST="" \
    SMTP_PASSWORD="" \
    SMTP_PORT="" \
    SMTP_PROTOCOL="" \
    SMTP_USER=""

EXPOSE 8069 8071

ENTRYPOINT ["/app-entrypoint.sh"]
CMD ["nami","start","--foreground","odoo"]
