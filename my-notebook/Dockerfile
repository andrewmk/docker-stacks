ARG OWNER="jupyter"
ARG BASE_CONTAINER=$OWNER/minimal-notebook
FROM $BASE_CONTAINER

LABEL maintainer="andrewmk"

USER root

RUN apt-get update --yes && \
    apt-get install --yes --no-install-recommends \
    # Extra packages
    selenium \
    python3-bs4 && \
    # Extra modules
    pip3 install PySimpleGUI &&
    apt-get clean && rm -rf /var/lib/apt/lists/*

# Switch back to jovyan to avoid accidental container runs as root
USER ${NB_UID}
