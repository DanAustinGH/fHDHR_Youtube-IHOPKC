# FakeHDHR_Youtube-IHOPKC

Welcome to the world of streaming to Plex! We use some fancy python here to achieve a system of:

**H**ome
**D**istribution
**H**iatus
**R**ecreation

(based off of original code from

  * [tvhProxy by jkaberg](https://github.com/jkaberg/tvhProxy)
  * [locast2plex by tgorgdotcom](https://github.com/tgorgdotcom/locast2plex)
  * myself coding for locast2plex
  * a direct fork of the normal Youtube Proxy, but with scheduling information specific to IHOP KC

  )

Until I have time to do the wiki thing for this project, instructions will be in this `README.md`.

PRs welcome for:

* Docker support


Vague Instructions (specific details intentionally excluded):

* install java

* Install ffmpeg, and verify it is accessible in PATH. Otherwise, you may specify it's path in your configuration later.
* Install Python3 and Python3-pip. There will be no support for Python2.
* Download the zip of the `master` branch, or `git clone`.
* `pip3 install -r requirements.txt`
* Copy the included configuration example to a known path, and adjust as needed. The script will look in the current directory for `config.ini`, but this can be specified with the commandline argument `--config_file=`
