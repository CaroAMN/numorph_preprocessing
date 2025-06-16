FROM matlabruntime/r2023a/release/update5/f000c0002000000000

# Create the directory
RUN mkdir -p /usr/bin/mlrtapp

COPY /build/numorph_preprocessing /usr/bin/mlrtapp
COPY /build/run_numorph_preprocessing.sh /usr/bin/mlrtapp
COPY /build/readme.txt /usr/bin/mlrtapp

RUN chmod -R a+rwx /usr/bin/mlrtapp/
# Create the directory
RUN mkdir /tmp/mcr_cache
RUN chmod a+rwx /tmp/mcr_cache

RUN useradd -ms /bin/bash appuser
USER appuser

# Set the MCR_CACHE_ROOT environment variable
ENV MCR_CACHE_ROOT=/tmp/mcr_cache

# Add MATLAB app directory to PATH
ENV PATH="/usr/bin/mlrtapp:${PATH}"

