
#all: patched.bin
clean:
	rm -f *~ *.bin *.img *.pyc

unwrapped.img:
	cd ../../firmware && "${MAKE}" unwrapped/FW_2017_nonGPS.img
	cp ../../firmware/unwrapped/FW_2017_nonGPS.img $@

.PHONY: patched.img
patched.img: unwrapped.img
	python ./patch.py
	#../../md380-gfx --firmware=patched.img --gfx=replacement-font-big-latin.pbm fontreplace
	#../../md380-gfx --firmware=patched.img --gfx=replacement-font-small-latin.pbm fontreplace
	#../../md380-gfx --firmware=patched.img --dir ./rsrc2017 extract 
	
	#../../md380-gfx --firmware=patched.img --gfx ./extrsc4/0x80df3bc_mod.ppm write
	#../../md380-gfx --firmware=patched.img --gfx ./extrsc4/0x80df3e4_mod.ppm write
##### md380-gfx "relocate" and "write"  doun't work with d13.020
#	../../md380-gfx --firmware=patched.img --gfx=0x80f9ca8-troopers-color.ppm relocate
#	../../md380-gfx --firmware=patched.img --gfx=../2.032/0x80f9ca8-poc.ppm write
                          
#patched.bin: patched.img
#	../../md380-fw --wrap patched.img patched.bin

#flash: patched.bin
#	../../md380-dfu upgrade patched.bin

