# Playbooks for PCF deploys:

Deploy playbook: pcf_push.yml

## Accepted arguments

### api_endpoint 
	PCF Apps endpoint for the foundation (eg) api.sys.pcfdev.one.west.com. If not provided, it will use the default in vars section

### sso_passcode
	The sso passcode to log in to the foundry. This is optional. If not provided, ansible script uses the user & password parameters to log in to the foundation

### user, password
	If not using sso_passcode, ansible will log in to foundation using user and password. If not provided, default values from vars section is used 

### space
	Space within the foundation to deploy to. (eg) Dev, Test, Stage, Prod

### artifact_location
	URL to of deployable jar/war (in Artifactory/Nexus)

### app_name
	Name of the PCF application (eg) tagging-service

### manifest\_file\_location
	URL of manifest.yml (in Artifactory/Nexus)

### blue\_green\_route
	The blue green route to choose. 


## Sample:

	ansible-playbook -vvv -i pcf-app-local-deploy-hosts pcf_push.yml --extra-vars '{"api_endpoint":"api.sys.pcfdev.one.west.com", "space":"Dev", "artifact_location":"http://artifactory-location", "app_name":"tagging-service", "manifest_file_location":"http://artifactory-location"}'  

