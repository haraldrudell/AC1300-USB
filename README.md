# Fastest USB Wi-Fi in 2020

Recent USB adapters are based on Realtek RTL8814AU chip capable of Wi-Fi 5<br />&emsp;&#x2014; 802.11ac AC1900 4x4:3<br />&emsp;&#x2014; 1.3 Gb/s gross speed on 80 MHz channels in 5 GHz<br />&emsp;&#x2014; browsing throughput 500 Mb/s, about half the speed of a cable

This means that a usb3 port can become a 500 Mb/s throughput access point on Linux with eap-tls or wpa3

Some adapters are:
* Netgear A7000 $69.99: performs best in tests
* Trendnet TEW-809UB
* Edimax EW-7833UAC
* ASUS USB-AC68

As of September 2020, any USB device that claims AC1900 is going to be rtl8814

0bda:8813

Vendor ID: 0bda
Device ID: 8813

# 5 GHz Access Point 1.3 Gb/s (500 Mb/s throughput possible)
<pre><blockquote>
# directive order from: https://w1.fi/cgit/hostap/plain/hostapd/hostapd.conf
# © 2020-present Harald Rudell <harald.rudell@gmail.com>
interface=wlx08beac123456
ssid=five80
country_code=US
ieee80211d=1
ieee80211h=1
hw_mode=a
channel=36
#auth_algs=1
#ap_isolate=1
ieee80211n=1
ht_capab=[LDPC][HT40+][GF][SHORT-GI-20][SHORT-GI-40][RX-STBC123][MAX-AMSDU-7935]
#require_ht=1 # scan from clients may not work
ieee80211ac=1
vht_capab=[MAX-MPDU-11454][RXLDPC][SHORT-GI-80][TX-STBC-2BY1][RX-STBC-123][SU-BEAMFORMEE][MAX-A-MPDU-LEN-EXP3][HTC-VHT][SOUNDING-DIMENSION-3]
vht_oper_chwidth=1
vht_oper_centr_freq_seg0_idx=42
# insert authentication here such as 802.11x eap-tls or wpa2
</blockquote></pre>

# Wi-Fi 5 802.11ac Wide (fast) Channels

# AC1300 80 MHz in 5 GHz band
<pre><blockquote>
# directive order from: https://w1.fi/cgit/hostap/plain/hostapd/hostapd.conf
# © 2020-present Harald Rudell <harald.rudell@gmail.com>
interface=wlx08beac123456
ssid=ssid-36-80
country_code=US
hw_mode=a
channel=36
ieee80211n=1
ht_capab=[HT40+]
ieee80211ac=1
vht_oper_chwidth=1
vht_oper_centr_freq_seg0_idx=42
</blockquote></pre>

Note: for 80 MHz channels, vht_oper_centr_freq_seg0_idx is channel + 6

What channel number that can be used depends on country, ie. the regulatory domain, a helpful picture is here: http://www.revolutionwifi.net/revolutionwifi/2013/03/80211ac-channel-planning.html

**iw list** displays Wi-Fi device capabilities

# 40 MHz in 5 GHz band
<pre><blockquote>
# directive order from: https://w1.fi/cgit/hostap/plain/hostapd/hostapd.conf
# © 2020-present Harald Rudell <harald.rudell@gmail.com>
interface=wlx08beac123456
ssid=ssid-36-40
country_code=US
hw_mode=a
channel=36
ieee80211n=1
ht_capab=[HT40+]
ieee80211ac=1
</blockquote></pre>

# 20 MHz in 5 GHz band
<pre><blockquote>
# directive order from: https://w1.fi/cgit/hostap/plain/hostapd/hostapd.conf
# © 2020-present Harald Rudell <harald.rudell@gmail.com>
interface=wlx08beac123456
ssid=ssid-36-20
country_code=US
hw_mode=a
channel=36
ieee80211n=1
ieee80211ac=1
</blockquote></pre>

# 469 Mb/s Driver for Linux: 5.8.5

commissioning described here: https://github.com/aircrack-ng/rtl8812au/issues/740#issuecomment-706616355

# Driver for Linux
This driver is based on 5.8.5 and continuously updated, offers dkms and 2020 Linux kernels:

https://github.com/aircrack-ng/rtl8812au

The produced kernel module is named 88XXau

The kernel tree and most distributions do not have any or any recent driver

Note: as of 10/1/2020 07c704c, this driver is too buggy to be used as a client. However, it does work as an access point

10/10/2020
