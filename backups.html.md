---
title: GitLab
---

TODO: Add documentation explaining how to SSH into the GitLab VMs / deployment

## GitLab Backup

Once you have SSH access to the GitLab VM, you can use GitLab's raketasks to create a backup.
It is possible to backup all data or only part (only DB, only data).
The GitLab documentation has up to date information on this:

- [Doing a backup of GitLab](http://doc.gitlab.com/ee/raketasks/backup_restore.html#create-a-backup-of-the-gitlab-system)
- [Uploading your backups to Cloud storage such as S3](http://doc.gitlab.com/ee/raketasks/backup_restore.html#upload-backups-to-remote-cloud-storage)
- [Restoring GitLab backups](http://doc.gitlab.com/ee/raketasks/backup_restore.html#restore-a-previously-created-backup)

Note that it is not necessary to backup the configuration file of GitLab when using the Pivotal Cloud Foundry GitLab Tile, as PCF takes care of the configuration of GitLab.
