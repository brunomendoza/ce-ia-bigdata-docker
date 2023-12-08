FROM  continuumio/miniconda3:23.9.0-0
COPY ./requirements.txt ./requirements.txt
RUN /bin/bash -c '/opt/conda/bin/conda install --channel=conda-forge --file=requirements.txt --yes --quiet \
    && mkdir /opt/notebooks'
COPY docker-entrypoint docker-entrypoint
RUN chmod 700 ./docker-entrypoint
ENTRYPOINT [ "./docker-entrypoint" ]
