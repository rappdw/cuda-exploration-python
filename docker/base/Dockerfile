FROM rappdw/nvidia-python:p3.7.2-u18.04-c10.0-n7.0

RUN set -ex; \
    apt-get update; \
    apt-get install -y \
        build-essential \
        cmake \
        cuda-command-line-tools-10-0 \
        less \
        vim \
        wget \
    ; \
    apt-get clean; \
    rm -rf /var/tmp/* /tmp/* /var/lib/apt/lists/*

RUN set -ex; \
    pip install --no-cache-dir \
        numba \
        numpy \
        six \
    ; \
    rm -rf /var/tmp/* /tmp/* /var/lib/apt/lists/*

#RUN set -ex; \
#    pip install --no-cache-dir \
#        pycuda \
#    ; \
#    rm -rf /var/tmp/* /tmp/* /var/lib/apt/lists/*


# setup necessary env variables (see numba [installation in README](https://github.com/numba/numba#custom-python-environments))
ENV NUMBAPRO_CUDA_DRIVER=/usr/lib/x86_64-linux-gnu/libcuda.so.410.79 \
    NUMBAPRO_NVVM=/usr/local/cuda-10.0/nvvm/lib64/libnvvm.so \
    NUMBAPRO_LIBDEVICE=/usr/local/cuda-10.0/nvvm/libdevice/ \
    PATH=$PATH:/usr/local/cuda-10.0/bin/ \
    LD_LIBRARY_PATH=$LD_LIBRARY_PATH:


RUN mkdir /workdir
WORKDIR /workdir