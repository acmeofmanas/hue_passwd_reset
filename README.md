# hue_passwd_reset

#fork from https://gethue.com/password-management-in-hue/


#set env:
HUE_CONF_DIR=/var/run/cloudera-scm-agent/process/-hue-HUE_SERVER-id
#-hue-HUE_SERVER-id=current process dir

echo $HUE_CONF_DIR

export HUE_CONF_DIR

#look for hue binary

cd /opt/cloudera/parcels/CDH-6.1.0-1.cdh6.1.0.p0.770702/lib/hue

#create superuser
 build/env/bin/hue createsuperuser --cm-managed
 
 # Go to Cloudera-hue-backed-change to DjangoBackend
 #backend=desktop.auth.backend.LdapBackend
 
-backend=desktop.auth.backend.LdapBackend	
+backend=desktop.auth.backend.AllowFirstUserDjangoBackend
 

