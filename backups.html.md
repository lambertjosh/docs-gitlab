---
title: GitLab
---

## SSH into a gitlab-ee instance

To login to bosh you need to follow the bosh-ssh guide. You will need a `gateway_identity_file` to access the OpsManager machine in order to route your connection to the one of GitLab workers. [See this guide](https://github.com/cloudfoundry/bosh-lite/blob/master/docs/bosh-ssh.md).

To connect to gitlab-ee VM do:

```
$ bosh ssh --gateway_identity_file=~/.ssh/id_rsa_bosh  --gateway_host=AWS_IP --gateway_user=ubuntu gitlab-ee 0
```
Now you can run any GitLab commands. Note that you have to refer to path of `gitlab-rake`, rather than calling it directly. You will find this at `/opt/gitlab/bin/gitlab-rake`. For instance, the basic backup command becomes:

```
sudo /opt/gitlab/bin/gitlab-rake gitlab:backup:create
```

## Run the Backup tool

Once you have SSH access to the GitLab VM, you can use GitLab's raketasks to create a backup.
It is possible to backup all data or only part (only DB, only data).
The GitLab documentation has up to date information on this:

- [Doing a backup of GitLab](http://doc.gitlab.com/ee/raketasks/backup_restore.html#create-a-backup-of-the-gitlab-system)
- [Uploading your backups to Cloud storage such as S3](http://doc.gitlab.com/ee/raketasks/backup_restore.html#upload-backups-to-remote-cloud-storage)
- [Restoring GitLab backups](http://doc.gitlab.com/ee/raketasks/backup_restore.html#restore-a-previously-created-backup)

Note that it is not necessary to backup the configuration file of GitLab when using the Pivotal Cloud Foundry GitLab Tile, as PCF takes care of the configuration of GitLab.
