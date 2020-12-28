FROM jboss/keycloak:latest

ARG KEYCLOAK_ADMIN_USER=${ADMIN_USER:-admin}
ARG KEYCLOAK_ADMIN_PASS=${ADMIN_PASS:-'ola123'}

HEALTHCHECK --interval=30s --timeout=30s --start-period=60s --retries=3 CMD [ "curl --fail http://localhost:8080 || exit 1"]

#Be sure to not expose port 9990 outside of the host
EXPOSE 8080 8443 9990

WORKDIR /opt/jboss/keycloak

RUN ./bin/add-user-keycloak.sh -u ${KEYCLOAK_ADMIN_USER} -p ${KEYCLOAK_ADMIN_PASS}

