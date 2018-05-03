# Notes of ref-update hook for Gerrit 2.15.1

#### Install hooks plugin when you upgrade or clean install the Gerrit, select the option to install the plugin hooks
#### Create a directory call 'hooks' under the GERRIT_PATH
#### Put ref-update into the hooks directory
#### Add following line into the gerrit.config file under GERRIT_PATH/etc
```
[hooks]
        refUpdateHook = ref-update

```
#### When you do the "git push origin HEAD:refs/heads/master", it will call the ref-update hook
#### Change old ref-update script with '--uploader-username" and "args.uploader_username"


# Notes of ref-updateed hook for Gerrit 2.15.1
#### If you have setup msmtp on server, you can use the following code to send email with subject and body, need "\r\n\r\n" to setup subject and body
```
echo -e "Subject: $SUBJECT \r\n\r\n $BODY" | msmtp -d $EMAIL_LIST >> $LOG
```
