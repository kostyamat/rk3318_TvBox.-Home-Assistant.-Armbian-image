# rk3318_TvBox.-Home-Assistant.-Armbian-image
## Зкачати: 
Образ [armbian24_HA17_clear.7z] (https://drive.google.com/file/d/1P3Tawogn7n4Tp01omC8F4UDEiAlUChNZ/view?usp=sharing)
Образ [multitool.img.xz] (https://drive.google.com/file/d/1uRYtn_xQ4WmM7CCYy34FkDKEzsRG75Bz/view?usp=sharing)
Програма для запису образів для Windows [balenaEtcher] (https://etcher.balena.io/)

## Встановити
- За допомогою balenaEtcher запишіть на SD картку, розміром не менше 16ГБ, multi-tool.img.xz
- Загрузіть бокс з цієї картки. Далі [ OK ]. Виберіть пункт Shutdown. Це потрібно для того, щоб moolti-tool автоматично збільшив свій розділ MOOLTI-TOOL до максимального розміру картки SD.
- Вийміть з боксу та вставте картку в ПК, в системі з'являться два нових логічні диски, відкрийте диск MOOLTI-TOOL, дістаньте з архіву та скопіюйте образ armbian24_HA17_clear.img.xz в теку Images. 
- Знову загрузіть бокс з картки. Далі [ OK ]. В меню виберіть Clear EMMC, далі підтвердіть вибір. Після закінчення очистки EMMC, перейдіть до пункту меню Install image та підтвердіть вибір розділу EMMC. 
- Після закінчення процесу вийміть картку та перезагрузіть бокс.
- Після загрузки ввійдіть в систему і виконайте команди
```
sudo systemctl enable armbian-resize-filesystem
sudo reboot
```
Після перезагрузки система буде готова до використання.
Доступ до WebUI Home Assistant http://homeassistant.local:8123/
