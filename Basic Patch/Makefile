TARGET = bas9511.dsk
BINFILE = BAS9511.BIN

all: clean $(TARGET)

clean:
	rm -f $(TARGET) $(BINFILE)

$(TARGET): diskgen $(BINFILE)
	decb copy $(BINFILE) $(TARGET),$(BINFILE) -2 -b
	decb copy ../COPYING $(TARGET),COPYING -1 -a
	decb copy -t FPBENCH.BAS $(TARGET),FPBENCH.BAS -0 -b
	decb copy -t ERRTEST.BAS $(TARGET),ERRTEST.BAS -0 -b
	decb copy -t PWRTEST.BAS $(TARGET),PWRTEST.BAS -0 -b

diskgen:
	decb dskini $(TARGET)

BAS9511.BIN: bas9511.asm
	lwasm -9 --decb -o $@ $<

