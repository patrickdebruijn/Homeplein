# Homeplein servers
Overview of my servers setup and configurations

### Servers overview
* [**Cameron** - _Custom build - Primary workhorse and NAS_](#Cameron)
    * [_Docker services overview_](#Docker-services)
* [**Carl** - _Fujitsu futro s920: amd g-series gx-415g, 4GB RAM - PFsense gateway_ ](#carl)
    * [_Pfsense configurations_](../Network/Pfsense/README.md)
* [**Grace** - _Raspberry Pi 4 - Pihole DNS_ ](#Grace)

#### Useful links
* [Where I get my stuff](#Where-I-get-my-stuff)
* [Resources / Guides](#Resources-/-Guides )
* [Good hardware](#Good-hardware)
___   
## Cameron
_Primary server that does all of the work, runs latest OMV version with snapraid and mergerFS and quite a few docker containers. It currently has multiple roles: NAS, Backup, Media (jellyfin, etc) and Home assistant. I'm want to split this in the future when I acquire some more low power hardware._ 

### Hardware specs
|  |  |
| ------------- | ------------- |
| **CPU** | [E3-1265L v2](https://ark.intel.com/content/www/us/en/ark/products/65728/intel-xeon-processor-e3-1265l-v2-8m-cache-2-50-ghz.html) |
| **RAM** | [Kingston 16gb PC3 12800E](https://nl.aliexpress.com/item/32952281698.html?spm=a2g0s.9042311.0.0.49594c4dgHLvPP) (16Gb ordered) |
| **Motherboard** | [Supermicro X9SCM-F](https://www.supermicro.com/products/motherboard/Xeon/C202_C204/X9SCM-F.cfm) |
| **Network** | 2x onboard intel quad gigabit  |
| **Storage #1**** | [Western Digital Green 240GB SSD](https://shop.westerndigital.com/en-us/products/internal-drives/wd-green-sata-ssd#WDS240G2G0A) |
| **Storage #2** | [Seagate Barracuda ST3000DM001-1ER1 3TB 64MB Cache SATA 6.0Gb/s 3.5](https://hdd.userbenchmark.com/Seagate-Barracuda-720014-3TB/Rating/1374) |
| **Storage #3** | [Seagate Barracuda ST3000DM001-1ER1 3TB 64MB Cache SATA 6.0Gb/s 3.5](https://hdd.userbenchmark.com/Seagate-Barracuda-720014-3TB/Rating/1374) |
| **Storage #4** | [Hitachi  HUS723030ALS640 3TB 7.2K SAS 3.5](https://www.ebay.nl/itm/Hitachi-3TB-7-2K-SAS-3-5-Hard-Drive-HUS723030ALS640-B26311/113999516942?ssPageName=STRK%3AMEBIDX%3AIT&_trksid=p2057872.m2749.l2649) |
| **Storage #5** | [Hitachi  HUS723030ALS640 3TB 7.2K SAS 3.5](https://www.ebay.nl/itm/Hitachi-3TB-7-2K-SAS-3-5-Hard-Drive-HUS723030ALS640-B26311/113999516942?ssPageName=STRK%3AMEBIDX%3AIT&_trksid=p2057872.m2749.l2649) |
| **Storage #6** | [Hitachi  HUS723030ALS640 3TB 7.2K SAS 3.5](https://www.ebay.nl/itm/Hitachi-3TB-7-2K-SAS-3-5-Hard-Drive-HUS723030ALS640-B26311/113999516942?ssPageName=STRK%3AMEBIDX%3AIT&_trksid=p2057872.m2749.l2649) |
| **Case** | [Inter-tech ipc 4u-4098-s](https://www.inter-tech.de/en/products/ipc/server-cases/4u-4098-s) |

### Docker services   
<table>
  <tr>
   <td><strong>Name</strong>
   </td>
   <td><strong>Provider</strong>
   </td>
   <td><strong>Description</strong>
   </td>
   <td><strong>Port</strong>
   </td>
  </tr>
  <tr>
   <td>Airsonic
   </td>
   <td>Dockstarter
   </td>
   <td>
   </td>
   <td>4041
   </td>
  </tr>
  <tr>
   <td>Bazarr
   </td>
   <td>Dockstarter
   </td>
   <td>
   </td>
   <td>6767
   </td>
  </tr>
  <tr>
   <td>Codeserver
   </td>
   <td>Dockstarter
   </td>
   <td>
   </td>
   <td>8443
   </td>
  </tr>
  <tr>
   <td>Duplicati
   </td>
   <td>Dockstarter
   </td>
   <td>
   </td>
   <td>8200
   </td>
  </tr>
  <tr>
   <td>HomeAssistant
   </td>
   <td>Dockstarter
   </td>
   <td>
   </td>
   <td>8123
   </td>
  </tr>
  <tr>
   <td>Hydra2
   </td>
   <td>Dockstarter
   </td>
   <td>
   </td>
   <td>5076
   </td>
  </tr>
  <tr>
   <td>Influxdb
   </td>
   <td>Dockstarter
   </td>
   <td>
   </td>
   <td>8086
   </td>
  </tr>
  <tr>
   <td>Ipam
   </td>
   <td>Blaineventurine
   </td>
   <td>
   </td>
   <td>3280
   </td>
  </tr>
  <tr>
   <td>Jackett
   </td>
   <td>Dockstarter
   </td>
   <td>
   </td>
   <td>9117
   </td>
  </tr>
  <tr>
   <td>Jellyfin
   </td>
   <td>Dockstarter
   </td>
   <td>
   </td>
   <td>8096,8920
   </td>
  </tr>
  <tr>
   <td>LazyLibrarian
   </td>
   <td>Dockstarter
   </td>
   <td>
   </td>
   <td>5299
   </td>
  </tr>
  <tr>
   <td>Lidar
   </td>
   <td>Dockstarter
   </td>
   <td>
   </td>
   <td>8686 (http), 6868 (https)
   </td>
  </tr>
  <tr>
   <td>MariaDB
   </td>
   <td>Dockstarter
   </td>
   <td>
   </td>
   <td>3306
   </td>
  </tr>
  <tr>
   <td>MaryTTS
   </td>
   <td>Blaineventurine
   </td>
   <td>
   </td>
   <td>59125
   </td>
  </tr>
  <tr>
   <td>Mosquitto
   </td>
   <td>Blaineventurine
   </td>
   <td>
   </td>
   <td>1883, 9001
   </td>
  </tr>
  <tr>
   <td>Netdata
   </td>
   <td>Dockstarter
   </td>
   <td>
   </td>
   <td>19999
   </td>
  </tr>
  <tr>
   <td>Nextcloud
   </td>
   <td>Dockstarter
   </td>
   <td>
   </td>
   <td>444
   </td>
  </tr>
  <tr>
   <td>Nodered
   </td>
   <td>Blaineventurine
   </td>
   <td>
   </td>
   <td>1880
   </td>
  </tr>
  <tr>
   <td>Ombi
   </td>
   <td>Dockstarter
   </td>
   <td>
   </td>
   <td>3579
   </td>
  </tr>
  <tr>
   <td>OpenMediaVault
   </td>
   <td>Dockstarter
   </td>
   <td>
   </td>
   <td>81
   </td>
  </tr>
  <tr>
   <td>Organizr
   </td>
   <td>Dockstarter
   </td>
   <td>
   </td>
   <td>8006
   </td>
  </tr>
  <tr>
   <td>Phpmyadmin
   </td>
   <td>Dockstarter
   </td>
   <td>
   </td>
   <td>8007
   </td>
  </tr>
  <tr>
   <td>Portainer
   </td>
   <td>Dockstarter
   </td>
   <td>
   </td>
   <td>9000
   </td>
  </tr>
  <tr>
   <td>Qbittorrent
   </td>
   <td>Dockstarter
   </td>
   <td>
   </td>
   <td>8082,8128
   </td>
  </tr>
  <tr>
   <td>Radarr
   </td>
   <td>Dockstarter
   </td>
   <td>
   </td>
   <td>7878(http), 9898 (https)
   </td>
  </tr>
  <tr>
   <td>Rhasspy
   </td>
   <td>Blaineventurine
   </td>
   <td>
   </td>
   <td>12101
   </td>
  </tr>
  <tr>
   <td>Sabnzb
   </td>
   <td>Dockstarter
   </td>
   <td>
   </td>
   <td>8080(http),8090 (https),8118
   </td>
  </tr>
  <tr>
   <td>Sonarr
   </td>
   <td>Dockstarter
   </td>
   <td>
   </td>
   <td>8989 (http), 9898 (https)
   </td>
  </tr>
  <tr>
   <td>Unmanic
   </td>
   <td>Dockstarter
   </td>
   <td>
   </td>
   <td>8888
   </td>
  </tr>
</table>

### OMV / NAS Guides 
* [Michaelxander - diy-nas OMV + Snapraid](https://michaelxander.com/diy-nas/)
* [My perfect 2018 media-server openmediavault](https://medium.com/@yllanos/my-perfect-2018-media-server-openmediavault-nas-storage-multimedia-services-53e74ea33af3)
* [Diy nasmediaserver](https://linustechtips.com/main/topic/1077251-diy-nasmediaserver/)
* [Patshead - building-a-nas 2019](https://blog.patshead.com/2019/04/building-a-nas-buy-lots-of-drive-or-just-what-you-need.html)
* [The perfect media server 2017](https://blog.linuxserver.io/2017/06/24/the-perfect-media-server-2017/)
* [Building an open media vault nas part 3](https://ridwankhan.com/building-an-open-media-vault-nas-part-3-configuring-omv-ee15322602be)
* [Auto mount encrypted disks on boot with remote key file ](https://www.reddit.com/r/linuxadmin/comments/eursu8/mounting_luksencrypted_data_disks_with_a_keyfile/)
___
## Carl
_Small Fujitsu futro s920 server to host PFSense as a network gateway_

### Hardware specs
|  |  |
| ------------- |-------------|
| **CPU** | amd g-series gx-415ga (quad core), 2 mb, 1.50 Ghz |
| **RAM** | 4gb |
| **Network** | 1x onboard, 4x intel quad gigabit pci-e |
| **Storage** | msata, 32 gb, flash drive MLC |
| **Case** | 52 x 195 x 250 mm |

___
## Grace
_Raspberry PI 4 4GB running Pihole DNS_

___
## Where I get my stuff
* [BVA auctions](https://www.bva-auctions.com/en/home) 
* [Troostwijk auctions](https://www.troostwijkauctions.com/nl/)
* [/r/homelabsales](https://www.reddit.com/r/homelabsales/)
* [/r/hardwareswap](https://www.reddit.com/r/hardwareswap/)
* [Tweakers.net vraag & aanbod servers](https://tweakers.net/categorie/714/servers/aanbod/)
* [Tweakers.net vraag & aanbod hard disks](https://tweakers.net/categorie/50/interne-harde-schijven/aanbod/)
* [Tweakers.net vraag & aanbod Super micro](https://tweakers.net/merk/1113/supermicro/aanbod/#filter:q1YqqSxILVayilZKVIqtBQA)
* [Serverhome](https://www.serverhome.nl)

## Wishlist
* Quadro p400
* Patch panel
* Harddisks (alot)
* APC/pdu metered

## Resources / Guides 
* [Nas killer build](https://forums.serverbuilds.net/t/nas-killer-4-0-build-guide-fast-quiet-power-efficient-and-flexible-starting-at-125/667)
* [CPU Comparison](https://www.serverbuilds.net/cpu-comparison)

## Good hardware
* Network
    * [Braided cables](https://www.amazon.com/gp/product/B07R3Z58MS/ref=ppx_yo_dt_b_asin_title_o00_s02?ie=UTF8&psc=1)
* Storage
    * [LSI sas 9201](https://www.ebay.com/p/1301621744?iid=182100909150)
    * [Mini sas to sata cable](https://aliexpress.com/item/32889723678.html?spm=a2g0s.9042311.0.0.73134c4dKkZEnH)
    * [Sata power splitter](https://nl.aliexpress.com/item/4000152246625.html?spm=a2g0s.9042311.0.0.73134c4dKkZEnH)
* Switches
    * [Mikrotik CSS326-24G-2S+RM SwOS powered 24 port Gigabit Ethernet switch with two SFP+](https://mikrotik.com/product/CSS326-24G-2SplusRM)
