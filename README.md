# ActivCam for Motion

[Motion](https://motion-project.github.io), a software motion detector, is a free software CCTV software application developed for Linux. 
[ActivMotion](https://esp8266.activcam.de) is an ESP8266 based alarm system. ActivCam is an Android app for both, [Motion](https://motion-project.github.io) and [ActivMotion](https://esp8266.activcam.de). 

Get the ActivCam app from the [Google Playstore](https://play.google.com/store/apps/details?id=de.avtivcam).

**made for 16:9 aspect ratio (HD camera and android device)**
 
  - based on webview service
  - start / stop motion detection
  - dynamic configuration changes
  - change orientation to landscape for full size video
  - touch for server & client side snapshot
  - wipe to switch from the overview to a camera and back
  - search more cams
  - action "eventend" supported for versions > 4.2
  - action "eventstart/makemovie" supported for versions > 4.2
  - alternative server url for home wifi-network

#### Basic configuration

motion.conf options for versions > 4.1:

    stream_localhost off
    webcontrol_localhost off
    webcontrol_interface 1
    webcontrol_parms 2
  
motion.conf options for versions > 3.2:
  
    stream_localhost off
    webcontrol_localhost off
    webcontrol_html_output off
    
#### Notifications ([BETA](https://play.google.com/apps/testing/de.avtivcam))

Motion currently doesn't include an integrated function for direct alerting when motion is detected.
ActivCam supports push notifications. Please use the notify dialog and get your messaging id. 
Configure your server as shown below.
  
    on_motion_detected wget https://alert.activcam.de/test.php?id=<see notify dialog>

Please note the [Google privacy policy](https://policies.google.com/privacy) in connection with 
Firebase Cloud Messaging. This feature is under development. The above url is only for testing.

#### Authentication 

    stream_auth_method 2
    stream_authentication <username:password>
    webcontrol_auth_method 2
    webcontrol_authentication <username:password>

#### Transport Layer Security 

    stream_tls on
    webcontrol_tls on
    webcontrol_cert <Full path and file name of the certificate file for tls: fullchain.pem>
    webcontrol_key <Full path and file name of the key file for tls: privkey.pem>

#### Permissions
The permission WRITE_EXTERNAL_STORAGE is necessary to make a client side snapshot. 
INTERNET and ACCESS_NETWORK_STATE privileges are used for the communication 
with your motion server. Only the files generated by the app will be processed. 
    
#### Privacy Statement

This content is published by a natural person in the course of a purely personal activity and 
thus with no connection to a professional or commercial activity. The European Union General 
Data Protection Regulation (GDPR) does not apply. However, the GDPR applies to 
[GitHub, Inc](https://help.github.com/articles/github-privacy-statement/).
