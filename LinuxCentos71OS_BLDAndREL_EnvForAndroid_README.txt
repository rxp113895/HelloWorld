### Android app as .APK file on 10.10.10.58 host
##BEGIN
# create demo user with sudo permission
usermod -aG wheel demo

# java openjdk including JRE installation
login as root
yum install java-1.8.0-openjdk-devel automatically into /usr/lib/jvm/*, and run "source \etc\profile.d\java-sdk.sh"

install *ant*.zip into /opt/ant/ and run "source \etc\profile.d\ant.sh"

install *maven*.zip into /opt/maven/ and run "source \etc\profile.d\maven.sh"

install *tomcat*.zip into /opt/tomcat/ and run "source \etc\profile.d\tomcat.sh"

# git installation
yum install git-all 

# install android toolkit as follows
unzip AndroidSDK-tools_r25.2.3-linux.zip for cmd-line tools into /opt/android-sdk
cd opt/android-sdk/bin
android list sdk (will list latest available online bundles)
android update sdk --no-ui --filter 1 (will install latest SDK/tools)
android update sdk --no-ui --filter 1 (will install platform-tools)
android update sdk --no-ui --filter 1 (will install build tools)

unzip android-ndk*.zip into /opt/android-ndk/

unzip android-studio into /opt/android-studio/ and run "source \etc\profile.d\androidstudio.sh"

# run build script
cd /root/apps/BuildAndroidAPK and edit repos.txt and run "./build.sh"

# Notes:
# Tested .APK file on Windows because Intel chips have the sufficient performance boost (that most chips on linux OS lack) to allow VDI
# Git Clone of Centos7.1/AndroidStudio2.3 project HelloWorld into Windows AndroidStudio IDE2.3 build needed following tweaks to build&run on VDI:
#   Editing project/local.properties file for sdk and ndk entries
#   Resolving error about 1 missing .layout by cliking on add and continue

## END
###
