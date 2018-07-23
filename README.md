Easy way to build a kernel for Manjaro to fix Razer Blade 15 Touchpad issue.

To build: 
	#add permission to your user (optionnal)
	
	chown -R $USER ~/<Path to the directory package-core>
	chown -R :$USER ~/<Path to the directory package-core>

	#patch are made only for linux 4.17
	
	cd linux417

	#build with multithread (optionnal)
	sudo vim /etc/makepkg.conf
	#add MAKEFLAGS="-jN"
	#With N your number of thread + 1

	makepkg -g >> PKG-BUILD

	#make the package

	makepkg  -s

	sudo pacman -U linux417-4.17.r180602.4277e6b-1-x86_64.pkg.tar.xz
	
reboot and enjoy a working trackpad \o/
	
