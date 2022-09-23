#  File: Makefile
#
#  Copyright 2008-2021 NXP
#
#  This software file (the File) is distributed by NXP
#  under the terms of the GNU General Public License Version 2, June 1991
#  (the License).  You may use, redistribute and/or modify the File in
#  accordance with the terms and conditions of the License, a copy of which
#  is available by writing to the Free Software Foundation, Inc.,
#  51 Franklin Street, Fifth Floor, Boston, MA 02110-1301 USA or on the
#  worldwide web at http://www.gnu.org/licenses/old-licenses/gpl-2.0.txt.
#
#  THE FILE IS DISTRIBUTED AS-IS, WITHOUT WARRANTY OF ANY KIND, AND THE
#  IMPLIED WARRANTIES OF MERCHANTABILITY OR FITNESS FOR A PARTICULAR PURPOSE
#  ARE EXPRESSLY DISCLAIMED.  The License provides additional details about
#  this warranty disclaimer.
#

$(info Running Makefile)

# Debug Option
# DEBUG LEVEL n/1/2:
# n: NO DEBUG
# 1: Only PRINTM(MMSG,...), PRINTM(MFATAL,...), ...
# 2: All PRINTM()
#CONFIG_DEBUG=1

# Enable STA mode support
#CONFIG_STA_SUPPORT=y

# Enable uAP mode support
#CONFIG_UAP_SUPPORT=y

# Enable WIFIDIRECT support
#CONFIG_WIFI_DIRECT_SUPPORT=y


# Re-association in driver
#CONFIG_REASSOCIATION=y


# Manufacturing firmware support
#CONFIG_MFG_CMD_SUPPORT=y

# OpenWrt support
#CONFIG_OPENWRT_SUPPORT=n

# Big-endian platform
#CONFIG_BIG_ENDIAN=n

#ifeq ($(CONFIG_DRV_EMBEDDED_SUPPLICANT), y)
#CONFIG_EMBEDDED_SUPP_AUTH=y
#else
#ifeq ($(CONFIG_DRV_EMBEDDED_AUTHENTICATOR), y)
#CONFIG_EMBEDDED_SUPP_AUTH=y
#endif
#endif

#ifdef SDIO_MMC
# SDIO suspend/resume
#CONFIG_SDIO_SUSPEND_RESUME=y
#endif

# DFS testing support
#CONFIG_DFS_TESTING_SUPPORT=y

#############################################################################
# Select Platform Tools
#############################################################################

#ccflags-y += -I$(PWD)/mlan
#ccflags-y += -DLINUX

#CONFIG_IMX_SUPPORT=y
#ifeq ($(CONFIG_IMX_SUPPORT),y)
#ccflags-y += -DIMX_SUPPORT
#endif

#LD += -S

#############################################################################
# Compiler Flags
#############################################################################

#	ccflags-y += -I$(KERNELDIR)/include

	ccflags-y += -DFPNUM='"92"'

#ifeq ($(CONFIG_DEBUG),1)
#	ccflags-y += -DDEBUG_LEVEL1
#endif

#ifeq ($(CONFIG_DEBUG),2)
#	ccflags-y += -DDEBUG_LEVEL1
#	ccflags-y += -DDEBUG_LEVEL2
#	DBG=	-dbg
#endif

# config 64BIT is bool
#ifeq ($(CONFIG_64BIT), y)
#	ccflags-y += -DMLAN_64BIT
#endif

#ifeq ($(CONFIG_STA_SUPPORT),y)
#	ccflags-y += -DSTA_SUPPORT
#ifeq ($(CONFIG_REASSOCIATION),y)
#	ccflags-y += -DREASSOCIATION
#endif
#else
#CONFIG_WIFI_DIRECT_SUPPORT=n
#CONFIG_STA_WEXT=n
#CONFIG_STA_CFG80211=n
#endif

#ifeq ($(CONFIG_UAP_SUPPORT),y)
#	ccflags-y += -DUAP_SUPPORT
#else
#CONFIG_WIFI_DIRECT_SUPPORT=n
#CONFIG_UAP_WEXT=n
#CONFIG_UAP_CFG80211=n
#endif

#ifeq ($(CONFIG_WIFI_DIRECT_SUPPORT),y)
#	ccflags-y += -DWIFI_DIRECT_SUPPORT
#endif

#ifeq ($(CONFIG_MFG_CMD_SUPPORT),y)
#	ccflags-y += -DMFG_CMD_SUPPORT
#endif

#ifeq ($(CONFIG_BIG_ENDIAN),y)
#	ccflags-y += -DBIG_ENDIAN_SUPPORT
#endif

#ifeq ($(CONFIG_USERSPACE_32BIT_OVER_KERNEL_64BIT),y)
#	ccflags-y += -DUSERSPACE_32BIT_OVER_KERNEL_64BIT
#endif

#ifdef SDIO_MMC
#ifeq ($(CONFIG_SDIO_SUSPEND_RESUME),y)
#	ccflags-y += -DSDIO_SUSPEND_RESUME
#endif
#endif

#ifeq ($(CONFIG_DFS_TESTING_SUPPORT),y)
#	ccflags-y += -DDFS_TESTING_SUPPORT
#endif

#ifeq ($(CONFIG_ANDROID_KERNEL), y)
#	ccflags-y += -DANDROID_KERNEL
#endif

#ifdef CONFIG_SDIO_8978
#	CONFIG_SDIO=y
	ccflags-y += -DSD8978
#endif

#ifdef CONFIG_USB_8978
#	CONFIG_MUSB=y
#	ccflags-y += -DUSB8978
#endif

#ifeq ($(CONFIG_SDIO),y)
#	ccflags-y += -DSDIO
#	ccflags-y += -DSDIO_MMC
#endif
#ifeq ($(CONFIG_MUSB),y)
#	ccflags-y += -DUSB
#endif

#ifeq ($(CONFIG_MAC80211_SUPPORT),y)
#	ccflags-y += -DMAC80211_SUPPORT
#endif
#ifeq ($(CONFIG_MAC80211_SUPPORT_UAP),y)
#	ccflags-y += -DMAC80211_SUPPORT_UAP
#endif
#ifeq ($(CONFIG_MAC80211_SUPPORT_MESH),y)
#	ccflags-y += -DMAC80211_SUPPORT_MESH
#endif

ccflags-y := $(call cc-ifversion, -ge, 0404, -Wno-packed-bitfield-compat)
ccflags-y := $(call cc-ifversion, -lt, 0700, -Wimplicit-fallthrough=3)

#############################################################################
# Make Targets
#############################################################################

#ifeq ($(CONFIG_WIRELESS_EXT),y)
#ifeq ($(CONFIG_WEXT_PRIV),y)
	# Enable WEXT for STA
#	CONFIG_STA_WEXT=y
	# Enable WEXT for uAP
#	CONFIG_UAP_WEXT=y
#else
# Disable WEXT for STA
#	CONFIG_STA_WEXT=n
# Disable WEXT for uAP
#	CONFIG_UAP_WEXT=n
#endif
#endif

# Enable CFG80211 for STA
#ifeq ($(CONFIG_CFG80211),y)
#	CONFIG_STA_CFG80211=y
#else
#ifeq ($(CONFIG_CFG80211),m)
#	CONFIG_STA_CFG80211=y
#else
#	CONFIG_STA_CFG80211=n
#endif
#endif

# Enable CFG80211 for uAP
#ifeq ($(CONFIG_CFG80211),y)
#	CONFIG_UAP_CFG80211=y
#else
#ifeq ($(CONFIG_CFG80211),m)
#	CONFIG_UAP_CFG80211=y
#else
#	CONFIG_UAP_CFG80211=n
#endif
#endif

#ifneq ($(CONFIG_STA_SUPPORT),y)
#	CONFIG_WIFI_DIRECT_SUPPORT=n
#	CONFIG_STA_WEXT=n
#	CONFIG_STA_CFG80211=n
#endif

#ifneq ($(CONFIG_UAP_SUPPORT),y)
#	CONFIG_WIFI_DIRECT_SUPPORT=n
#	CONFIG_UAP_WEXT=n
#	CONFIG_UAP_CFG80211=n
#endif

#ifeq ($(CONFIG_STA_SUPPORT),y)
#ifeq ($(CONFIG_STA_WEXT),y)
#	ccflags-y += -DSTA_WEXT
#endif
#ifeq ($(CONFIG_STA_CFG80211),y)
#	ccflags-y += -DSTA_CFG80211
#endif
#endif
#ifeq ($(CONFIG_UAP_SUPPORT),y)
#ifeq ($(CONFIG_UAP_WEXT),y)
#	ccflags-y += -DUAP_WEXT
#endif
#ifeq ($(CONFIG_UAP_CFG80211),y)
#	ccflags-y += -DUAP_CFG80211
#endif
#endif

#MOALOBJS =	mlinux/moal_main.o \
		mlinux/moal_ioctl.o \
		mlinux/moal_shim.o \
		mlinux/moal_eth_ioctl.o \
		mlinux/moal_init.o

#MLANOBJS =	mlan/mlan_shim.o mlan/mlan_init.o \
		mlan/mlan_txrx.o \
		mlan/mlan_cmdevt.o mlan/mlan_misc.o \
		mlan/mlan_cfp.o \
		mlan/mlan_module.o

#MLANOBJS += mlan/mlan_wmm.o
#ifeq ($(CONFIG_MUSB),y)
#MLANOBJS += mlan/mlan_usb.o
#endif
#ifeq ($(CONFIG_SDIO),y)
#MLANOBJS += mlan/mlan_sdio.o
#endif
#MLANOBJS += mlan/mlan_11n_aggr.o
#MLANOBJS += mlan/mlan_11n_rxreorder.o
#MLANOBJS += mlan/mlan_11n.o
#MLANOBJS += mlan/mlan_11ac.o
#MLANOBJS += mlan/mlan_11ax.o
#MLANOBJS += mlan/mlan_11d.o
#MLANOBJS += mlan/mlan_11h.o
#$(info $(MLANOBJS))
#ifeq ($(CONFIG_STA_SUPPORT),y)
#MLANOBJS += mlan/mlan_meas.o
#MLANOBJS += mlan/mlan_scan.o \
			mlan/mlan_sta_ioctl.o \
			mlan/mlan_sta_rx.o \
			mlan/mlan_sta_tx.o \
			mlan/mlan_sta_event.o \
			mlan/mlan_sta_cmd.o \
			mlan/mlan_sta_cmdresp.o \
			mlan/mlan_join.o
#ifeq ($(CONFIG_STA_WEXT),y)
#MOALOBJS += mlinux/moal_priv.o \
            mlinux/moal_wext.o
#endif
#endif
#ifeq ($(CONFIG_UAP_SUPPORT),y)
#MLANOBJS += mlan/mlan_uap_ioctl.o
#MLANOBJS += mlan/mlan_uap_cmdevent.o
#MLANOBJS += mlan/mlan_uap_txrx.o
#MOALOBJS += mlinux/moal_uap.o
#ifeq ($(CONFIG_UAP_WEXT),y)
#MOALOBJS += mlinux/moal_uap_priv.o
#MOALOBJS += mlinux/moal_uap_wext.o
#endif
#endif
#ifeq ($(CONFIG_STA_CFG80211),y)
#MOALOBJS += mlinux/moal_cfg80211.o
#MOALOBJS += mlinux/moal_cfg80211_util.o
#MOALOBJS += mlinux/moal_sta_cfg80211.o
#endif
#ifeq ($(CONFIG_UAP_CFG80211),y)
#MOALOBJS += mlinux/moal_cfg80211.o
#MOALOBJS += mlinux/moal_cfg80211_util.o
#MOALOBJS += mlinux/moal_uap_cfg80211.o
#endif

#ifdef CONFIG_PROC_FS
#MOALOBJS += mlinux/moal_proc.o
#MOALOBJS += mlinux/moal_debug.o
#endif

#ifeq ($(CONFIG_MAC80211_SUPPORT),y)
#MOALOBJS += mlinux/moal_mac80211.o
#MLANOBJS += mlan/mlan_mac80211.o
#endif

#obj-$(CONFIG_NXP_8978) := mlan.o
#mlan-y := $(MLANOBJS)

#ifeq ($(CONFIG_MUSB),y)
#MOALOBJS += mlinux/moal_usb.o
#endif
#ifeq ($(CONFIG_SDIO_8978),y)
#MOALOBJS += mlinux/moal_sdio_mmc.o
#endif
#obj-$(CONFIG_NXP_8978) += moal.o
#moal-y := $(MOALOBJS)

obj-$(CONFIG_NXP_8978) += mlan/
obj-$(CONFIG_NXP_8978) += mlinux/

# End of file
