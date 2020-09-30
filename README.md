# Fastest USB Wi-Fi in 2020

Recent USB adapters are based on Realtek RTL8814AU chip capable of AC1900: 4x4x3

This means that a usb port can become a 90 Mb/s access point on Linux

Some adapters are:
* Netgear A7000 $69.99
* Trendnet TEW-809UB
* Edimax EW-7833UAC
* ASUS USB-AC68

As of September 2020, any USB device that claims AC1900 is going to be rtl8814

0bda:8813

Vendor ID: 0bda
Device ID: 8813

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
ht_capab=[HT40+]
ieee80211n=1
ieee80211ac=1
vht_oper_chwidth=1
vht_oper_centr_freq_seg0_idx=42
</blockquote></pre>

Note: for 80 MHz channels, vht_oper_centr_freq_seg0_idx is channel + 6

What channel number that can be used depends on country, ie. the regulatory domain, e helpful picture is here: http://www.revolutionwifi.net/revolutionwifi/2013/03/80211ac-channel-planning.html

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
ht_capab=[HT40+]
ieee80211n=1
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

# Driver for Linux
This driver is based on 5.8.5 and continuously updated, offers dkms and 2020 Linux kernels:

https://github.com/aircrack-ng/rtl8812au

The produced kernel module is named 88XXau

The kernel tree and most distributions do not have any or any recent driver
