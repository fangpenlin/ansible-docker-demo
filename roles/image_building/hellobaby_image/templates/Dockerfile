FROM {{ hellobaby_base_name }}:{{ hellobaby_base_tag }}
MAINTAINER Victor Lin <bornstub@gmail.com>

# update apt and install dependencies
RUN apt-get -qq update
RUN apt-get install -y python python-dev python-pip python-virtualenv
RUN apt-get install -y build-essential gcc
RUN easy_install -U setuptools

# install packages
ADD hellobaby.tar /srv/hellobaby
RUN echo "{{ hellobaby_image_tag }}" > /srv/hellobaby/hellobaby/version.txt
RUN echo "{{ hellobaby_repo.after }}" > /srv/hellobaby/hellobaby/git_revision.txt
RUN pip install -e /srv/hellobaby

# run hellobaby app as a runit service
RUN mkdir /etc/service/hellobaby
ADD runapp.sh /etc/service/hellobaby/run
RUN chmod +x /etc/service/hellobaby/run

EXPOSE 6543

# Clean up APT when done.
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
