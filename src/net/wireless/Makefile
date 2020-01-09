obj-$(CONFIG_CFG80211) += cfg80211_dup.o
obj-$(CONFIG_LIB80211) += lib80211_dup.o
obj-$(CONFIG_LIB80211_CRYPT_WEP) += lib80211_crypt_wep_dup.o
obj-$(CONFIG_LIB80211_CRYPT_CCMP) += lib80211_crypt_ccmp_dup.o
obj-$(CONFIG_LIB80211_CRYPT_TKIP) += lib80211_crypt_tkip_dup.o
obj-m += wext.o

cfg80211_dup-objs := core.o sysfs.o radiotap.o util.o reg.o scan.o nl80211.o \
                     mlme.o ibss.o sme.o chan.o ethtool.o mesh.o ap.o trace.o \
                     ocb.o wext-compat.o wext-sme.o genetlink-compat.o
lib80211_dup-objs := lib80211.o
lib80211_crypt_wep_dup-objs := lib80211_crypt_wep.o
lib80211_crypt_ccmp_dup-objs := lib80211_crypt_ccmp.o
lib80211_crypt_tkip_dup-objs := lib80211_crypt_tkip.o

wext-objs := wext-core.o wext-proc.o wext-spy.o wext-priv.o
cfg80211-$(CONFIG_CFG80211_INTERNAL_REGDB) += regdb.o

CFLAGS_trace.o := -I$(src)

ccflags-y += -D__CHECK_ENDIAN__

$(obj)/regdb.c: $(src)/db.txt $(src)/genregdb.awk
	@$(AWK) -f $(srctree)/$(src)/genregdb.awk < $< > $@

clean-files := regdb.c

