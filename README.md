# ZONES_CME

Add monitoring blade to automated deployed GW from Check Point

------- No supported in production ------- Enable monitoring blade Needs to be run in Autoprovision template with "ZONE" as a custom parameter

Usage.

First need to copy the bash into the management server

curl_cli -k https://url/of/raw -O .bash
Change permissions to let the admin execute the file

chmod +x .bash
Now you need to enable the file to be used as custom script on the CME

autoprov-cfg set management -cs /path/to/.bash
Enable the parameter to launch the script, in this case the bash is looking for 'MONITORING' to be trigger

autoprov-cfg set template -tn -cp ZONE
Whit this everytime the Gateway is launched it send a command and this will launch

**NOTE a variable called POLICY_PACKAGE_NAME= need to be adequated to your policy or can be passed as parameter.
