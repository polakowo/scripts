Mounting a remote folder on macOS over SSH:
- Install [FUSE for macOS](https://osxfuse.github.io)
- Install [SSHFS](https://osxfuse.github.io)
- Create a folder which will point to the remote host:
```bash
mkdir $local_folder
```
- Enable SSH on a remote Mac:
```bash
sudo systemsetup -setremotelogin on
```
- Note: It should be accessible from outside, thus permit SSH connections in router settings.
- Mount the remote folder:
```bash
sshfs $remote_user@$remote_host:$remote_folder $local_folder
```
- Then to unmount the folder:
```bash
umount $local_folder
rm -rf $local_folder
```
