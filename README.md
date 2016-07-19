# AutoDeploy
Auto deploy a web-based project located on a remote server

## Instructions
These instructions assume the following paths on the intended server:
- Web Directory: `/srv/www/site.com`
- Repo: `/srv/repo/site.git`

## Process
- SSH into the intended server
- Navigate to the repo directory (`/srv/repo`)
- `sudo mkdir site.git && cd site.git`
- `sudo git init --bare` creates a bare repo
- `cd hooks`
- `sudo nano post-receive`
- Add the contents of the `post-receive` doc while changing the `DEPLOYDIR` to the location of the web directory (`/srv/www/site.com`)
- `ctrl + o` to write the file. `enter` to write the file to `post-receive`. `ctrl + x` to exit.
- `sudo chmod +x post-receive` to make `post-receive` executable
make it executable

Whichever user will be running the deploy commands needs to have the writable privileges to the web directory
- `sudo chown {username here} -R /srv/www/site.com`
