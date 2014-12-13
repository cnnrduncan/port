#! /bin/tcsh
if ($1 == update) then
	cd /usr/ports/
	portsnap fetch update
else if ($1 == old) then
	pkg version -l "<"
else if ($1 == confrec) then
	cd /usr/ports/$2
	make config-recursive
else if ($1 == config) then
	cd /usr/ports/$2
	make configure
else if ($1 == rmconfig ) then
	cd /usr/ports/$2
	make rmconfig
else if ($1 == install) then
	cd /usr/ports/$2
	make install clean
else if ($1 == remove ) then
	cd /usr/ports/$2
	make deinstall clean
else if ($1 == search) then
	cd /usr/ports/	
	make search name=$2 | grep Path: | awk '{print $2}' | awk '{gsub("/usr/ports/", "");print}'
else if ($1 == detail) then
	cd /usr/ports
	make quicksearch path=/usr/ports/$2
else
	echo "Error: See man page for usage."
endif
