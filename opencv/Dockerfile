FROM  continuumio/miniconda3:23.9.0-0
COPY ./requirements.txt ./requirements.txt
RUN /bin/bash -c '/opt/conda/bin/conda install -c conda-forge --file requirements.txt -y --quiet \
    && apt-get update \
    && apt-get install --quite --assume-yes --no-install-recommends ffmpeg libsm6 libxext6 \
    && apt-get clean \
    && mkdir /opt/notebooks'
COPY docker-entrypoint docker-entrypoint
RUN chmod 700 ./docker-entrypoint
ENTRYPOINT [ "./docker-entrypoint" ]
