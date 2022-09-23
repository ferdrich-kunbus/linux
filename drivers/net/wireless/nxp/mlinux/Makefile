ccflags-y += -DSTA_CFG80211
ccflags-y += -DSTA_SUPPORT
ccflags-y += -DSTA_WEXT
ccflags-y += -DUAP_SUPPORT
ccflags-y += -DUAP_CFG80211
ccflags-y += -DUAP_WEXT
ccflags-y += -DDEBUG_LEVEL1
ccflags-y += -DREASSOCIATION
ccflags-y += -DSDIO
ccflags-y += -DSDIO_MMC
ccflags-y += -DFPNUM='"92"'
ccflags-y += -DSD8978

MOALOBJS =	moal_main.o \
		moal_ioctl.o \
		moal_shim.o \
		moal_eth_ioctl.o \
		moal_init.o

MOALOBJS += moal_cfg80211.o
MOALOBJS += moal_cfg80211_util.o
MOALOBJS += moal_sta_cfg80211.o
MOALOBJS += moal_uap_cfg80211.o

MOALOBJS += moal_uap.o
MOALOBJS += moal_uap_priv.o
MOALOBJS += moal_uap_wext.o
MOALOBJS += moal_priv.o
MOALOBJS += moal_wext.o

ifdef CONFIG_PROC_FS
MOALOBJS += moal_proc.o
MOALOBJS += moal_debug.o
endif

MOALOBJS += moal_sdio_mmc.o

obj-$(CONFIG_NXP_8978) += moal.o
moal-y := $(MOALOBJS)
