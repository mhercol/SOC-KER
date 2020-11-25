FROM splunk/splunk:latest
WORKDIR /opt/splunk/etc/apps
# Copy app thehive_ca to the container
COPY ta_thehive_ce_114.tgz ta_thehive_ce_114.tgz
RUN tar -zxvf ta_thehive_ce_114.tgz
# Copy lookup_file_editor to the container
COPY lookup-file-editor_346.tgz lookup-file-editor_346.tgz 
RUN  tar -zxvf lookup-file-editor_346.tgz

#ENV SPLUNK_HOME=/opt/splunk
#RUN /opt/splunk/bin/splunk add user thehive -password secretthehive -role admin -auth thehive:secretthehive
# Cannot copy CSV because user admin has not been inicialized yet, and therefore the folder does not exist
#USER splunk
#RUN mkdir  /opt/splunk/etc/users/thehive/ta_thehive_ce
#WORKDIR /opt/splunk/etc/users/thehive/ta_thehive_ce/lookups/
WORKDIR /tmp
COPY thehive_instance_list.csv thehive_instance_list.csv
# Will add to the container the avility to wait until the ansible book is completed in docker-compose
ADD https://github.com/ufoscout/docker-compose-wait/releases/download/2.7.3/wait wait
USER root
RUN chmod +x /tmp/wait
