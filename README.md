# open_jtalk docker image

## Description

Open JTalk is a Japanese text-to-speech system.

This image allows you to run Open JTalk in a completelly containerized
environment. It also includes several voices located in /usr/lib/hts-voice.
Voices included:

* mei_angry.htsvoice
* mei_bashful.htsvoice
* mei_happy.htsvoice
* mei_normal.htsvoice
* mei_sad.htsvoice
* nitech_jp_atr503_m001.htsvoice

Please check the following websites for license information:

* http://open-jtalk.sp.nitech.ac.jp/
* http://www.mmdagent.jp/

## How to use this image

Generate a wav file with the speech of word 車 (kuruma)

```
echo "くるま" | docker run \
        -i \
        --rm \
        -v $PWD:/tmp \
        fr3nd/open_jtalk \
        open_jtalk \
          -x /usr/dic \
          -m /usr/lib/hts-voice/mei_normal.htsvoice \
          -ow /tmp/out.wav
```
