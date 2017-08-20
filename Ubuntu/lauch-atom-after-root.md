# Sử dụng Atom trên Ubuntu 16.04

* **Tổng hợp:** Thi Minh Nhựt - **Email:** thiminhnhut@gmail.com

* **Thời gian:** Ngày 10 tháng 08 năm 2017

## Tài liệu tham khảo

1. [markovone](https://github.com/markovone) on [Atom does not launch unless done by `sudo atom` in terminal - Ubuntu 14.04 #9822](https://github.com/atom/atom/issues/9822)

## Khắc phục lỗi không mở được Atom sau khi mở Atom với quyền root

* Gặp lỗi như bên dưới:

	```bash
	$ atom
	$ /usr/bin/atom: line 123: /home/minhnhut/.atom/nohup.out: Permission denied
	(atom:9076): IBUS-WARNING **: The owner of /home/minhnhut/.config/ibus/bus is not root!
	Object has been destroyed
	Error: Object has been destroyed
		at Error (native)
		at AtomWindow.module.exports.AtomWindow.isFocused (/opt/atom/resources/app/src/main-process/atom-window.js:434:33)
		at /opt/atom/resources/app/src/main-process/atom-application.js:797:27
		at /opt/atom/resources/app/node_modules/underscore/underscore.js:159:21
		at Array.some (native)
		at _.some._.any (/opt/atom/resources/app/node_modules/underscore/underscore.js:208:59)
		at Object._.find._.detect (/opt/atom/resources/app/node_modules/underscore/underscore.js:158:5)
		at AtomApplication.module.exports.AtomApplication.focusedWindow (/opt/atom/resources/app/src/main-process/atom-application.js:796:16)
		at AtomApplication.module.exports.AtomApplication.getDimensionsForNewWindow (/opt/atom/resources/app/src/main-process/atom-application.js:812:32)
		at AtomApplication.module.exports.AtomApplication.openPaths (/opt/atom/resources/app/src/main-process/atom-application.js:918:35)
		at AtomApplication.module.exports.AtomApplication.openPath (/opt/atom/resources/app/src/main-process/atom-application.js:827:19)
		at AtomApplication.module.exports.AtomApplication.openWithOptions (/opt/atom/resources/app/src/main-process/atom-application.js:221:21)
		at Socket.<anonymous> (/opt/atom/resources/app/src/main-process/atom-application.js:310:26)
		at emitNone (events.js:91:20)
		at Socket.emit (events.js:185:7)
		at endReadableNT (_stream_readable.js:974:12)
		at _combinedTickCallback (internal/process/next_tick.js:74:11)
		at process._tickCallback (internal/process/next_tick.js:98:9)
	```

* Khắc phục:

	```bash
	$ sudo rm ~/.atom/nohup.out
	$ sudo chown -R $USER:$USER /home/$USER/.atom
	```
