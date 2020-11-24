FROM splunk/splunk:latest
# Copy app thehive_ca to the container
WORKDIR /opt/splunk/etc/apps
COPY ta_thehive_ce_114.tgz ta_thehive_ce_114.tgz
RUN tar -zxvf ta_thehive_ce_114.tgz
# Copy lookup_file_editor to the container
COPY lookup-file-editor_346.tgz lookup-file-editor_346.tgz 
RUN  tar -zxvf lookup-file-editor_346.tgz
