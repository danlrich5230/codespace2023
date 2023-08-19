FROM debian:bullseye-slim

# Avoid warnings by switching to noninteractive
ENV DEBIAN_FRONTEND=noninteractive

# Configure apt and install packages
RUN apt-get update \
    && apt-get install -y --no-install-recommends postgresql postgresql-contrib \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/* \
    && service postgresql start \
    && su - postgres -c "psql -c \"ALTER USER postgres PASSWORD 'LenaRose@@22';\""

# Switch back to dialog for any ad-hoc use of apt-get
ENV DEBIAN_FRONTEND=dialog
