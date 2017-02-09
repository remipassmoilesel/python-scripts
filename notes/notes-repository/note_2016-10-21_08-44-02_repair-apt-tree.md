# Réparer une arborescence perdue avec APT

Exemple du cas ou le dossier /etc/apt a été supprimé.

Récréer un fichier de sources:

	$ mkdir -p /etc/apt
	$ vim /etc/apt/sources.list

	# Ajouter les sources en bas de fichier

Puis lister les paqeuets qui ont des fichiers installés dans ce dossier:

	$ dpkg -S /etc/apt
	update-notifier-common, debian-archive-keyring, aptdaemon, postgresql-common, apt, apt-file, debconf: /etc/apt

Enfin réinstaller les paquets:

	$ sudo apt-get update
	$ sudo apt-get install --reinstall debian-archive-keyring postgresql-common apt-file update-notifier-common debconf aptdaemon apt  

## Sources.list Xenial 

	# deb cdrom:[Ubuntu 16.04.1 LTS _Xenial Xerus_ - Release amd64 (20160719)]/ xenial main restricted

	# See http://help.ubuntu.com/community/UpgradeNotes for how to upgrade to
	# newer versions of the distribution.
	deb http://fr.archive.ubuntu.com/ubuntu/ xenial main restricted
	# deb-src http://fr.archive.ubuntu.com/ubuntu/ xenial main restricted

	## Major bug fix updates produced after the final release of the
	## distribution.
	deb http://fr.archive.ubuntu.com/ubuntu/ xenial-updates main restricted
	# deb-src http://fr.archive.ubuntu.com/ubuntu/ xenial-updates main restricted

	## N.B. software from this repository is ENTIRELY UNSUPPORTED by the Ubuntu
	## team, and may not be under a free licence. Please satisfy yourself as to
	## your rights to use the software. Also, please note that software in
	## universe WILL NOT receive any review or updates from the Ubuntu security
	## team.
	deb http://fr.archive.ubuntu.com/ubuntu/ xenial universe
	# deb-src http://fr.archive.ubuntu.com/ubuntu/ xenial universe
	deb http://fr.archive.ubuntu.com/ubuntu/ xenial-updates universe
	# deb-src http://fr.archive.ubuntu.com/ubuntu/ xenial-updates universe

	## N.B. software from this repository is ENTIRELY UNSUPPORTED by the Ubuntu 
	## team, and may not be under a free licence. Please satisfy yourself as to 
	## your rights to use the software. Also, please note that software in 
	## multiverse WILL NOT receive any review or updates from the Ubuntu
	## security team.
	deb http://fr.archive.ubuntu.com/ubuntu/ xenial multiverse
	# deb-src http://fr.archive.ubuntu.com/ubuntu/ xenial multiverse
	deb http://fr.archive.ubuntu.com/ubuntu/ xenial-updates multiverse
	# deb-src http://fr.archive.ubuntu.com/ubuntu/ xenial-updates multiverse

	## N.B. software from this repository may not have been tested as
	## extensively as that contained in the main release, although it includes
	## newer versions of some applications which may provide useful features.
	## Also, please note that software in backports WILL NOT receive any review
	## or updates from the Ubuntu security team.
	deb http://fr.archive.ubuntu.com/ubuntu/ xenial-backports main restricted universe multiverse
	# deb-src http://fr.archive.ubuntu.com/ubuntu/ xenial-backports main restricted universe multiverse

	## Uncomment the following two lines to add software from Canonical's
	## 'partner' repository.
	## This software is not part of Ubuntu, but is offered by Canonical and the
	## respective vendors as a service to Ubuntu users.
	deb http://archive.canonical.com/ubuntu xenial partner
	deb-src http://archive.canonical.com/ubuntu xenial partner

	deb http://security.ubuntu.com/ubuntu xenial-security main restricted
	# deb-src http://security.ubuntu.com/ubuntu xenial-security main restricted
	deb http://security.ubuntu.com/ubuntu xenial-security universe
	# deb-src http://security.ubuntu.com/ubuntu xenial-security universe
	deb http://security.ubuntu.com/ubuntu xenial-security multiverse
	# deb-src http://security.ubuntu.com/ubuntu xenial-security multiverse