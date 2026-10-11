FROM splunk/splunk:10.4-rhel9

# OS Python 3.14
USER root
RUN microdnf install -y python3.14 python3.14-pip \
    && microdnf clean all \
    && ln -sfn /usr/bin/python3.14 /usr/bin/python

WORKDIR /tmp/build
COPY ./requirements.txt ./

# Install OS Python dependencies and verify PyMySQL is available for Ansible MySQL modules.
RUN /usr/bin/python -m pip install --no-cache-dir -r requirements.txt
