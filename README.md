# mf-rack
See the ```mf_rack_deployment.ipynb``` notebook for instructions for installing MeasurementFramework on to a rack.


## Creating Releases
It is important that tagged releases are made for tested updates made to this repsitory. This ensures that the production racks have a consitent and solid release version. When a new release is ready, inform the operations team of the new release version.

### Remote Write Configuration Updates
A new release will have to be created when there are changes made to the remote write configurations. See the GitHub repo https://github.com/fabric-testbed/mf-parsers for instructions on updating the remote write file. This should only need to be done if changes have been made to the metrics choosen to be sent to the public metrics sites.

 If the remote write file has changed then the version of the remote_write_configs yaml filename in this repository will need to be updated in the file 
`mf-rack/instrumentize/prometheus/ansible/roles/fabric_rack/templates/Prometheus/prometheus_config.yml.j2`.

Look for the line 
`################# REMOTE WRITE for PUBLIC METRIC SITES ##################` 
and change the 
`YYYY.MM.dd.hh.mm_remote_write_out.yml`
filename in the following line: 
`{% include 'tmp_deployment_files/mf-parsers/remote_write/remote_write_configs/2024.01.29.21.41_public_remote_write_out.yml' %}`
