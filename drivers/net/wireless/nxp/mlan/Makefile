ccflags-y += -DSTA_SUPPORT
ccflags-y += -DUAP_SUPPORT
ccflags-y += -DDEBUG_LEVEL1
ccflags-y += -DSDIO
ccflags-y += -DSD8978

MLANOBJS = mlan_shim.o mlan_init.o \
    mlan_txrx.o \
    mlan_cmdevt.o mlan_misc.o \
    mlan_cfp.o \
    mlan_module.o
 
MLANOBJS += mlan_wmm.o
MLANOBJS += mlan_sdio.o
MLANOBJS += mlan_11n_aggr.o
MLANOBJS += mlan_11n_rxreorder.o
MLANOBJS += mlan_11n.o
MLANOBJS += mlan_11ac.o
MLANOBJS += mlan_11ax.o
MLANOBJS += mlan_11d.o
MLANOBJS += mlan_11h.o
MLANOBJS += mlan_meas.o
MLANOBJS += mlan_scan.o \
      mlan_sta_ioctl.o \
      mlan_sta_rx.o \
      mlan_sta_tx.o \
      mlan_sta_event.o \
      mlan_sta_cmd.o \
      mlan_sta_cmdresp.o \
      mlan_join.o

MLANOBJS += mlan_uap_ioctl.o
MLANOBJS += mlan_uap_cmdevent.o
MLANOBJS += mlan_uap_txrx.o

obj-$(CONFIG_NXP_8978) += mlan.o
mlan-y := $(MLANOBJS)
