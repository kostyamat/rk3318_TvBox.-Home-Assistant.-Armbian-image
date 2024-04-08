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

## Завантажити: 
- Образ [armbian24_HA17_clear.7z](https://drive.google.com/file/d/1P3Tawogn7n4Tp01omC8F4UDEiAlUChNZ/view?usp=sharing)
- Образ [multitool.img.xz](https://drive.google.com/file/d/1uRYtn_xQ4WmM7CCYy34FkDKEzsRG75Bz/view?usp=sharing)
- Програма для запису образів для Windows [balenaEtcher](https://etcher.balena.io/)

## Встановити
- За допомогою balenaEtcher запишіть на SD картку, розміром не менше 16ГБ, multi-tool.img.xz
- Загрузіть бокс з цієї картки. Далі [ OK ]. Виберіть пункт Shutdown. Це потрібно для того, щоб moolti-tool автоматично збільшив свій розділ MOOLTI-TOOL до максимального розміру картки SD.
- Вийміть з боксу та вставте картку в ПК, в системі з'являться два нових логічні диски, відкрийте диск MOOLTI-TOOL, дістаньте з архіву та скопіюйте образ armbian24_HA17_clear.img.xz в теку Images. 
- Знову загрузіть бокс з картки. Далі [ OK ]. В меню виберіть Clear EMMC, далі підтвердіть вибір. Після закінчення очистки EMMC, перейдіть до пункту меню Install image та підтвердіть вибір розділу EMMC. 
- Після закінчення процесу вийміть картку та перезагрузіть бокс.
- Для розширення розділу root до повного розміру EMMC, після загрузки увійдіть в систему і виконайте команди
```
sudo systemctl enable armbian-resize-filesystem
sudo reboot
```
Після перезагрузки система буде готова до використання.
Доступ до WebUI Home Assistant http://homeassistant.local:8123/
