Bienvenido a FeelAndroid
========================

Preparando el entorno
---------------------

Instalamos los paquetes necesarios.

	sudo apt-get install git ccache gnupg flex bison gperf build-essential \
	zip curl libc6-dev libncurses5-dev:i386 x11proto-core-dev \
	libx11-dev:i386 libreadline6-dev:i386 libgl1-mesa-glx:i386 \
	libgl1-mesa-dev g++-multilib mingw32 tofrodos schedtool \
	python-markdown libxml2-utils xsltproc zlib1g-dev:i386 dpkg-dev

Crear enlace a las librerias.

	sudo ln -s /usr/lib/i386-linux-gnu/mesa/libGL.so.1 /usr/lib/i386-linux-gnu/libGL.so

Instalar Java7.

	sudo apt-get install openjdk-7-jdk

Crear directorio para binarios.

	mkdir ~/bin
	PATH=~/bin:$PATH

Instalar repo.

	curl http://commondatastorage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
	chmod a+x ~/bin/repo

Crear directorio de trabajo.

	mkdir ~/FeelAndroid
	cd ~/FeelAndroid

Iniciar repositorio.

	repo init -u https://github.com/FeelAndroid/manifest.git

Comenzar a descargar!

	repo sync -j4

Activar y configurar caché

	export USE_CCACHE=1
	export CCACHE_DIR=~/.ccache
	prebuilts/misc/linux-x86/ccache/ccache -M 100G

Compilando
----------

Estando en el directorio de trabajo.

	cd ~/FeelAndroid

Ejecuta el script y selecciona tu dispositivo.
	
	sh build/compile.sh

