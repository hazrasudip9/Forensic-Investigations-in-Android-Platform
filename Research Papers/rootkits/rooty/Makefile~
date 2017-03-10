KERNELDIR := /lib/modules/$(shell uname -r)/build
CLEANFILE := *.dis *.o *.ko *.mod.* *.symvers *.*.old
obj-m := rooty.o
default:
	make -C $(KERNELDIR)  M=$(CURDIR) modules
clean:
	rm -f $(CLEANFILE) 
