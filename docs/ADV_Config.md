<p align="center">fHDHR    <img src="images/logo.ico" alt="Logo"/></p>

---
[Main](README.md)  |  [Setup and Usage](Usage.md)  |  [Youtube-IHOPKC](Origin.md)  |  [Credits/Related Projects](Related-Projects.md)
---
**f**un
**H**ome
**D**istribution
**H**iatus
**R**ecreation

---

[Basic Configuration](Config.md)  | [Advanced Configuration](ADV_Config.md) |  [WebUI](WebUI.md)

---

Here, we'll break down all of the configuration options per section.

## Main
Here's the `main` section.
* `uuid` will be created automatically, you need not worry about this.
* `cache_dir` is handy for keeping cached files out of the script directory. This is helpful for reinstalls as well as development.

````
[main]
# uuid =
# cache_dir =
````

## fhdhr

The `fhdhr` contains all the configuration options for interfacing between this script and your media platform.
* `address` and `port` are what we will allow the script to listen on. `0.0.0.0` is the default, and will respond to all.
* `discovery_address` may be helpful for making SSDP work properly. If `address` is not `0.0.0.0`, we will use that. If this is not set to a real IP, we won't run SSDP. SSDP is only really helpful for discovering in Plex/Emby. It's a wasted resource since you can manually add the `ip:port` of the script to Plex.
* `tuner_count` is a limit of devices able to stream from the script.
* `friendlyname` is to set the name that Plex sees the script as.
* `stream_type` can be set to `ffmpeg`, `vlc` or `direct`.


````
[fhdhr]
# address = 0.0.0.0
# discovery_address = 0.0.0.0
# port = 5004
# stream_type = direct
# tuner_count =  4
# friendlyname = fHDHR-Youtube-IHOPKC
# reporting_firmware_name = fHDHR_Youtube-IHOPKC
# reporting_manufacturer = BoronDust
# reporting_model = fHDHR
# reporting_firmware_ver = 20201001
# reporting_tuner_type = Antenna
# device_auth = fHDHR
````

# EPG
* `images` can be set to `proxy` or `pass`. If you choose `proxy`, images will be reverse proxied through fHDHR.
* `method` defaults to `origin` and will pull the xmltv data. Other Options include `blocks` which is an hourly schedule with minimal channel information. Another option is `zap2it`, which is another source of EPG information. Channel Numbers may need to be manually mapped.
* `update_frequency` * `epg_update_frequency` determines how often we check for new scheduling information. In Seconds.

````
[epg]
# images = pass
# method = origin
# update_frequency = 43200
````

## ffmpeg

The `ffmpeg` section includes:
* `path` is useful if ffmpeg is not in your systems PATH, or you want to manually specify.
* `bytes_per_read` determines how many bytes of the stream to read before sending the data to your client. Increasing this value may cause longer load times, and lowering it may effect `stuttering`.

````
[ffmpeg]
# path = ffmpeg
# bytes_per_read = 1152000
````

## vlc

The `vlc` section includes:
* `path` is useful if ffmpeg is not in your systems PATH, or you want to manually specify.
* `bytes_per_read` determines how many bytes of the stream to read before sending the data to your client. Increasing this value may cause longer load times, and lowering it may effect `stuttering`.

````
[vlc]
# path = ffmpeg
# bytes_per_read = 1152000
````

## direct_stream

The `direct_stream` section is for when you set the `[fhdhr]stream_type` to `direct`
* `chunksize` is how much data to read at a time.

````
[direct_stream]
# chunksize = 1024*1024
````

# Logging
* `level` determines the amount of logging you wish to see in the console, as well as to the logfile (stored in your cache directory).

````
[logging]
# level = WARNING
````

# Database
* experiment with these settings at your own risk. We use sqlalchemy to provide database options, but we default to sqlite.

TODO: improve documentation here.

````
[database]
# type = sqlite
# driver = None
````

## Youtube
The `youtube` section
* `api_key` is something you'll need to get from google.

````
[youtube]
api_key =
````
