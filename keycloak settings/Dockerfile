# Dockerfile for creating custom Keycloak image with imported sport-realm
# Use the official Keycloak image as the base
FROM quay.io/keycloak/keycloak:latest

# Set environment variables for Keycloak configuration
ENV KEYCLOAK_ADMIN=admin
ENV KEYCLOAK_ADMIN_PASSWORD=admin
ENV KEYCLOAK_IMPORT=/opt/keycloak/data/import/realm-export.json


## Enable script uploads
#ENV KC_SPI_THEME_STATIC_FILE_MAX_SIZE=1048576
#ENV KC_SPI_THEME_JAR_MAX_SIZE=1048576

# Copy the realm configuration file into the container
COPY realm-export.json /opt/keycloak/data/import/realm-export.json

# Set the entrypoint to include the import of the realm
ENTRYPOINT ["/opt/keycloak/bin/kc.sh", "start-dev", "--import-realm"]