# Mount SMB shares
#### mount
* `mkdir <local-mount-folder>`
* `mount -t cifs -o user=<user>,password=<password>,rw,vers=1.0 //<SMB_target-IP>/<SMB_share> <local-mount-folder>`

## Cool resources