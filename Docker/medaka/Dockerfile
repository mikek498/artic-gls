FROM continuumio/miniconda3:latest
LABEL authors="Matt Bull" \
      description="Docker image containing requirements for medaka for the ARTIC project's ncov2019 pipeline"

COPY environment-medaka.yml /
RUN apt-get update && apt-get install -y g++ git make procps && apt-get clean -y
RUN git clone https://github.com/artic-network/artic-ncov2019 /artic-ncov2019
RUN /opt/conda/bin/conda env create -f /environment-medaka.yml && /opt/conda/bin/conda clean -a
ENV PATH /opt/conda/envs/artic-ncov2019-medaka/bin:$PATH
ENTRYPOINT ["/opt/conda/envs/artic-ncov2019-medaka/bin/artic"]

