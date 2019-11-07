# docker-lsyncd
A utility for one-way synchronisation of a local folder with a folder on a remote machine. When you delete a file or folder in a local folder, the deletion does not occur in the deleted folder (as an option). Perfect for mirroring data.
## Launching
1. Cloning the repository
```
git clone https://github.com/abataloff/docker-lsyncd.git
```
2. Configuration
    1. Rename the lsyncd/lsyncd.config.example file to lsyncd.config
    2. Set the hostname of the remote host in the parameter _sync.host_ in lsyncd.config
    3. Set the path to directory on remote host in the parameter _sync.targetdir_ in lsyncd.config
    4. Set path to local directory as volume (./data:/data) in docker-compose file
    5. Create the folder _keys_ with ssh private key for autorization on remote host (he should be without a password and with permission 600)
    6. Create the known_hosts file in _keys_
3. Run container
```
docker-compose up -d
```
