# Location of your Doom][ IWAD file
DOOM2WAD=/usr/local/games/xdoom/doom2.wad
#DOOM2WAD=//h/doom/doom2/doom2.wad

trandemo.wad: trandemo.lwad trandemo.gwad trandemo.rwad
	rm -f trandemo.wad
	wadcat -o trandemo.wad trandemo.lwad trandemo.gwad trandemo.rwad

trandemo.lwad: trandemo.map
	wadlc trandemo.map tmp.wad
	bsp -noprog tmp.wad -o trandemo.lwad
	wreject trandemo.lwad MAP01 600
	rm tmp.wad

trandemo.gwad: trandemo.wgc glass1.ppm glass2.ppm glass3f.ppm glass3b.ppm \
	umgr1.ppm umcomp1.ppm umcomp2.ppm umcomp3.ppm
	wadext $(DOOM2WAD) PNAMES pnames.raw
	wadext $(DOOM2WAD) TEXTURE1 texture1.raw
	wadgc trandemo.wgc trandemo.gwad
	rm temp.* pnames.raw texture1.raw

trandemo.rwad: comtxt.txt switches.lmp animated.lmp
	mkwad -p trandemo.rwad @trandemo.res

switches.lmp:
	swantbls swantbls.dat

animated.lmp:
	swantbls swantbls.dat

clean:
	rm -f *.bak temp.* *.raw trandemo.gwad trandemo.lwad trandemo.rwad \
	switches.lmp animated.lmp
