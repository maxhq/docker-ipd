# iCloud Photo Downloader

This is a wrapper around the [iCloud Photos Downloader](https://github.com/ndbroadbent/icloud_photos_downloader) Python script which uses the [pyicloud](https://github.com/picklepete/pyicloud) library to access Apple iCloud. It allows you to use the downloader script
without installing Python and the specific dependencies.

Please note that on first run and every X months Apple asks for the iCloud password (even though an access token is generated and saved).

## Docker volumes

You have to mount host directories to the following volumes:

* */photos* - target for the photos
* */auth* - place where the script will store your iCloud access tokens

## Usage

```bash
docker run --rm -ti -v <photo dir>:/photos -v <token dir>:/auth maxhq/ipd <apple id>
```

Example to store the photos in *~/icloud-photos*:

```bash
docker run --rm -ti -v ~/icloud-photos:/photos -v ~/icloud-secrets:/auth maxhq/ipd apple@id
```
