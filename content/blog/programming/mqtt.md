+++
title = "金錢無法帶給你真正的滿足"
#description = "spf13-vim is a cross platform distribution of vim plugins and resources for Vim."
date = "2019-08-14"
categories = ["Programming"]
#slug = "spf13-vim-3-0-release-and-new-website"
#tags = [".vimrc", "plugins", "spf13-vim", "vim"]
type = "post"
draft = true
+++

安裝 mosquitto 之後，如果作業系統重開機，需要再下

`sudo mosquitto -D` 指令，daemon 才會重開

檢查 mosquitto 有沒有在運行
`sudo service mosquitto status`

讓 mosquitto 一開機就會啟動
`sudo systemctl enable mosquitto.service`

broadcast MQTT port
`avahi-publish -s KKLINX-LINUX _kklinx._tcp 5566 CPath=/device &`