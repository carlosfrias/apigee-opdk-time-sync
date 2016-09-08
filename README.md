Apigee OPDK Time Sync
=====================

This roles installs and minimally configures ntpd and sets the locale for an Apigee OPDK installation.  

Requirements
------------

A local ntp server can be specified by uncommenting and setting the preferred_server_ip variable. The installation of 
Apigee OPDK requires root access. Credentials must also be supplied to override the empty placeholders
provided here. It is recommended that credentials be consolidated into a single credentials.yml file that can be stored 
separately. It is assumed that files containing credentials are stored in the ~/.apigee folder. 

Role Variables
--------------

Set this to the desired timezone file

    timezone: /usr/share/zoneinfo/America/New_York

This is set as the preferred ntp server, feel free to set your own. 

    preferred_server_ip: 128.138.141.172

Location of the drift file

    drift_filename: /var/lib/ntp/drift


Location of the ntp stats dir

    stats_dir: /var/log/ntpstats

Location of the ntp configuration file

    ntp_conf: /etc/ntp.conf


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    ---
    - hosts: '{{ hosts }}'
      become: true
    
      roles:
      - opdk-time-sync

Author Information
------------------

Carlos Frias
