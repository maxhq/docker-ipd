# Workflow

* Check for new version / pick a commit:
  * https://github.com/ndbroadbent/icloud_photos_downloader
* Docker:
  * edit Dockerfile on workstation
  * build Docker image (use date of commit as tag):
    * `docker build -t maxhq/ipd:2016-10-20 -t maxhq/ipd:latest ./`
  * test Docker image:
    * `docker run --rm -ti -v ~/icloud-photos:/photos -v ~/icloud-secrets:/auth maxhq/ipd myapple@id`
    * `docker run --rm -ti -v ~/icloud-photos:/photos -v ~/icloud-secrets:/auth --entrypoint=/bin/sh maxhq/ipd`
* Commit and push to GitHub:
  * `git commit -a`
  * `git push`
  * `git tag 2016-10-20`
  * `git push --tags`
