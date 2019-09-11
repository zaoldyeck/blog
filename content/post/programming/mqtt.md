+++
title = "作業系統重開機後，重啟 Mosquitto 的方法"
#description = "spf13-vim is a cross platform distribution of vim plugins and resources for Vim."
date = "2019-08-24"
categories = ["Programming"]
#slug = "spf13-vim-3-0-release-and-new-website"
tags = ["mosquitto", "mqtt", "avahi"]
type = "post"
draft = true
+++

安裝 mosquitto 之後，如果作業系統重開機

需要再下 `sudo mosquitto -D` 指令，daemon 才會重開

</br>

檢查 mosquitto 有沒有在運行

`sudo service mosquitto status`

</br>

讓 mosquitto 一開機就啟動

`sudo systemctl enable mosquitto.service`

</br>

用 Avahi 廣播 Local Service 的 Port

`avahi-publish -s KKLINX-LINUX _kklinx._tcp 5566 CPath=/device &`

`sudo vi /etc/mosquitto/conf.d/mosquitto.conf`
Add `listener 1883 127.0.0.1`
`sudo pkill -u mosquitto`
`sudo mosquitto -c /etc/mosquitto/conf.d/mosquitto.conf`