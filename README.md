### How to backup?
Backup continuously to GCS.

```
docker run -v DIRECTORY_TO_BACKUP:/data -e GCLOUD_KEYFILE_BASE64= -e GCLOUD_PROJECT= -e BUCKET=gs:// gregory90/file-backup-gcs /run
```

##### Environment variables
GCLOUD_KEYFILE_BASE64 - service account json key,  
GCLOUD_PROJECT - project id,  
BUCKET - GCS bucket for backup.  

### Restore backup
Restore file from GCS.

```
docker run -v DIRECTORY_TO_RESTORE_TO:/data -e GCLOUD_KEYFILE_BASE64= -e GCLOUD_PROJECT= -e BUCKET=gs:// -e FILE= gregory90/file-backup-gcs /restore
```

##### Environment variables
GCLOUD_KEYFILE_BASE64 - service account json key,  
GCLOUD_PROJECT - project id,  
BUCKET - GCS bucket for backup.  
FILE - file to restore (without extension),  
