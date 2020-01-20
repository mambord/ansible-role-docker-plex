# ansible-role-docker-plex
This role configures and starts a docker-compose based plex server. It uses the [plexinc/pms-docker](https://hub.docker.com/r/plexinc/pms-docker/) image.

## Defaults

### Plex settings

```yaml
docker_plex_timezone: 'Europe/Zurich'
docker_plex_host_ip: '192.168.1.2'
docker_plex_hostname: 'my.plex'
```

### Image tag
```yaml
# version tag, see https://hub.docker.com/r/plexinc/pms-docker/tags
docker_plex_image_tag: latest
```

### Folder structure

```yaml
# basedir where the data and docker-compose files are stored
docker_plex_base_dir: /opt/plex
```
The role writes a folder structure as follows:

```
/opt/plex/
├── data/                   # Your media library              
├── config/                 # Plex configuration & database
├── transcode/              # Temp directory for transcoding
└── docker-compose.yaml
```

### User & Group
Uid/Gid for the plex user in the container. Directories on host are chowned by uid:gid.
```yaml
# plex user & group
docker_plex_uid: 1000
docker_plex_gid: 1000
```

## Claim token

Optionaly, a Plex token can be provided. You can get your claim token from [www.plex.tv/claim](https://www.plex.tv/claim/).

```yaml
docker_plex_claim_token: claim-l6ZzsjD7Gkh64bbbWWDm
```
