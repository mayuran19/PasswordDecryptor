#Script that does project specifies path setting.
#!/bin/sh
##########################################################################################################################################################################

JAVA_HOME=/JavaHome/JDKHome; export JAVA_HOME
HQ_JAVA_HOME=/JavaHome/JDKHome; export HQ_JAVA_HOME
GROOVY_HOME=/opt/groovy; export GROOVY_HOME

PATH=/JavaHome/JDKHome/bin:/opt/groovy/bin:/opt/oracle/product/11.2.0/client_1/lib:/opt/sqlplus:/usr/bin:/usr/local/bin:/export/home/apmgr/.groovy:/usr/bin:/bin
export PATH

CLASSPATH=$CLASSPATH:/G3App/appfc/script/G3IPSBOWeb/groovy
export CLASSPATH

# ~~~~~~~~~~~~~~~~~~~~~~~~ Environment Start ~~~~~~~~~~~~~~~~~~~~~~~~ #
PROPGROOVYSCRIPT=/G3App/appfc/script/G3IPSBOWeb/groovy
PROPGROOVYEXECSCRIPT=/G3App/appfc/script/IPSGroovy

PROPIPSBOHOST=localhost
PROPIPSBOPORT=9292
PROPAPIUSERID=PACHOPR1
PROPAPIPWD=`java -classpath ".:/G3App/appfc/program/external/lib/*:/G3App/appshare/program/base/lib/*:passwordDecryptor.jar" com.bcsis.g3.utility.passwordDecryptor.Main`


PROPGROOVYOUTPUTPATH=/var/tmp/BCSISApp/logs/groovy
PROPGROOVYOUTPUTBACKUPPATH=/var/tmp/BCSISApp/logs/archived/groovy
PROPDOWNLOADFOLDER=/var/tmp
# ~~~~~~~~~~~~~~~~~~~~~~~~  Environment End  ~~~~~~~~~~~~~~~~~~~~~~~~ #
