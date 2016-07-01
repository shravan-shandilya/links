Bulk rename of arm cross compiler's bin folder:
I was trying to rename "arm-linux-gnueabihf-gcc" to "arm-linux-uclibceabi-gcc" and similarly for all the files which starts with "arm-linux-gnueabihf-"

for file in $(ls -1 arm-linux-gnueabihf-*);do mv $file arm-linux-uclibceabi-$(echo $file | rev | cut -d- -f1 | rev) ;done
