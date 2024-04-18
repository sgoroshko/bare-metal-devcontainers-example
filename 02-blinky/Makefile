SOURCES = main.c

LDFLAGS ?= -Tlink.ld -nostartfiles -nostdlib --specs nano.specs -lc -lgcc -Wl,--gc-sections -Wl,-Map=$@.map
CFLAGS  ?= -W -Wall -Wextra -Werror -Wundef -Wshadow \
			-Wdouble-promotion \
			-Wformat-truncation \
			-Wconversion \
			-fno-common \
			-ffunction-sections \
			-fdata-sections \
			-g3 \
			-Os \
			-I. \
			-mthumb \
			-mcpu=cortex-m4 \
			-mfloat-abi=hard \
			-mfpu=fpv4-sp-d16


build: firmware.bin


firmware.elf: $(SOURCES)
	arm-none-eabi-gcc $(SOURCES) $(CFLAGS) $(LDFLAGS) -o $@


firmware.bin: firmware.elf
	arm-none-eabi-objcopy -O binary $< $@


clean:
	rm -rf firmware.*
