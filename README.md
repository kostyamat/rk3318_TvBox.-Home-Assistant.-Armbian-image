# rk3318_TvBox.-Home-Assistant.-Armbian-image
## Шо це?
Це створений мною образ Armbian 24.2.1 Bookworm with Linux 6.6.16-current-rockchip64 для Android TvBox H96 Max, на базі процесора Rockchip RK3318 або RK3328.
Оновлено станом на 04.04.2024.
- Встановлено OS-Agent 1.6.0
- Home Assistant Supervised v.17. Core 2024.4.0, Supervisor 2024.03.1
- включено доступ SSH, SFTP (PuTTY, WinSCP)
  
## Що працює?
Працює все, окрім внутрішньго пристрою Bluetooth. WiKi HA рекомендує використовувати ESPhome Bluetooth Proxy, на базі ESP32, і не рекомендує використовувати bluetooth під Linux. Тому я вважаю, що це не критично. Але буду радий любій допомозі побороти проблему з bluetooth.
```
user: root password: root123
user: user password: user123
```
# Знадобиться:
- SD картка, розміром щонайменше 16ГБ, USB Клавіатура.

## Завантажити: 
- Образ [armbian24_HA17_clear.7z](https://drive.google.com/file/d/1P3Tawogn7n4Tp01omC8F4UDEiAlUChNZ/view?usp=sharing)
- Образ [multitool.img.xz](https://drive.google.com/file/d/1uRYtn_xQ4WmM7CCYy34FkDKEzsRG75Bz/view?usp=sharing)
- Програма для запису образів для Windows [balenaEtcher](https://etcher.balena.io/)

## Встановити
- Підключить бокс до телевізора кабелем HDMI, підключіть клавіатуру, виберіть на телевізорі правильний порт HDMI.
- За допомогою balenaEtcher запишіть на SD картку, розміром не менше 16ГБ, multi-tool.img.xz
- Завантажте бокс з цієї картки. Далі [ OK ]. Виберіть пункт Shutdown. Це потрібно для того, щоб moolti-tool автоматично збільшив свій розділ MOOLTI-TOOL до максимального розміру картки SD.
- Вийміть з боксу та вставте картку в ПК, в системі з'являться два нових логічні диски, відкрийте диск MOOLTI-TOOL, дістаньте з архіву та скопіюйте образ armbian24_HA17_clear.img.xz в теку Images. 
- Знову завантажте бокс з картки. Далі [ OK ]. В меню виберіть Clear EMMC, далі підтвердіть вибір.
- Після закінчення очистки EMMC, перейдіть до пункту меню Install image та підтвердіть вибір розділу EMMC. Процес встановлення займає доволі багато часу.
- Після закінчення процесу вийміть картку та перезавантажте бокс.
- Для розширення розділу root до повного розміру EMMC, після перезавантаження увійдіть в систему і виконайте команди
```
sudo systemctl enable armbian-resize-filesystem
sudo reboot
```
Після перезавантаження система буде готова до використання.
Доступ до WebUI Home Assistant http://homeassistant.local:8123/

Віддячити, закинувши на каву, можна [тут](https://www.paypal.com/paypalme/kostyamat)

# rk3318_TvBox.-Home-Assistant.-Armbian-image
## What is it?
This is an Armbian 24.2.1 Bookworm image created by me with Linux 6.6.16-current-rockchip64 for Android Tvbox H96 Max, based on the Rockchip rk3318 or RK3328 processor.
Updated as of 04.04.2024.
- Installed OS-Agent 1.6.0
- Home Assistant Supervised v.17. Core 2024.4.0, Supervisor 2024.03.1
- SSH, SFTP (PuTTY, WinSCP)access enabled
  
## What works?
Everything works except the internal Bluetooth device. WiKi HA recommends using the ESP32-based Esphome Bluetooth Proxy and does not recommend using bluetooth under Linux. So I think it's not critical. But I will be glad to have any help to overcome the problem with bluetooth.
```
user: root password: root123
user: user password: user123
```
# You'll need it:
- SD card 16GB or bigger, USB keyboard.

## Download: 
- Image [armbian24_HA17_clear.7z](https://drive.google.com/file/d/1P3Tawogn7n4Tp01omC8F4UDEiAlUChNZ/view?usp=sharing)
- Image [multitool.img.xz](https://drive.google.com/file/d/1uRYtn_xQ4WmM7CCYy34FkDKEzsRG75Bz/view?usp=sharing)
- Program for burn images, for Windows [balenaEtcher](https://etcher.balena.io/)

## Installation
- Connect the box to the TV with an HDMI cable, connect the keyboard, select the correct HDMI port on the TV.
- Use balenaEtcher to write multi-tool.img.xz to the SD card.
- Boot the box from this SD card. Next [ OK ]. Select Shutdown. This is necessary to moolti-tool automatically increases the MULTI-TOOL partition to the maximum size of the SD card.
- Remove SD card from the box and insert it to PC, two new logical disks will appear, open the MOOLTI-TOOL disk.
- Extract armbian24_HA17_clear.img.XZ from the archive and copy it to Images folder. 
- Boot the box from SD card again. Next [ OK ]. In the menu that appears, select Clear EMMC, then confirm the selection.
- After cleaning EMMC, choce Install image menu item and confirm selected EMMC partition. The installation process takes quite a long time.
- At the end of the process, remove the card and restart the box.
- To extend the root partition to the full size of EMMC login linux and run the commands
```
sudo systemctl enable armbian-resize-filesystem
sudo reboot
```
After a reboot, the system will be ready for use.
Access to WebUI Home Assistant http://homeassistant.local:8123/

Buy me coffee [here]https://www.paypal.com/paypalme/kostyamat)
