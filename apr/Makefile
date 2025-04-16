#
# Copyright (C) 2007-2011 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=apr
PKG_VERSION:=1.6.2
PKG_RELEASE:=2

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_URL:=@APACHE/apr/
PKG_HASH:=09109cea377bab0028bba19a92b5b0e89603df9eab05c0f7dbd4dd83d48dcebd
PKG_MAINTAINER:=Thomas Heil <heil@terminal-consulting.de>
PKG_LICENSE:=Apache License

PKG_FIXUP:=autoreconf
PKG_REMOVE_FILES:=aclocal.m4 build/ltmain.sh

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/libapr
  SECTION:=libs
  CATEGORY:=Libraries
  DEPENDS:=+libpthread +librt +libuuid
  TITLE:=Apache Portable Runtime Library
  URL:=http://apr.apache.org/
endef

TARGET_CFLAGS += $(FPIC)
TARGET_CPPFLAGS += -D_LARGEFILE64_SOURCE -D_FILE_OFFSET_BITS=64 -D_GNU_SOURCE

CONFIGURE_ARGS += \
	--with-devrandom=/dev/urandom \
	$(call autoconf_bool,CONFIG_IPV6,ipv6)

# XXX: ac_cv_sizeof_struct_iovec=1 is just to trick configure
CONFIGURE_VARS += \
	ac_cv_sizeof_struct_iovec=1 \
	ac_cv_struct_rlimit=yes \
	apr_cv_process_shared_works=yes \
	apr_cv_mutex_robust_shared=no \
	apr_cv_tcp_nodelay_with_cork=yes \
	apr_cv_use_lfs64=yes \
	LDFLAGS="$$$$LDFLAGS -lpthread" \

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/bin $(1)/usr/include/apr-1 $(1)/usr/lib $(1)/usr/lib/pkgconfig $(1)/usr/share/build-1
	$(CP)   $(PKG_INSTALL_DIR)/usr/bin/apr-1-config \
		$(1)/usr/bin/
	$(CP)   $(PKG_INSTALL_DIR)/usr/include/apr-1/* \
		$(1)/usr/include/apr-1/
	$(CP)   $(PKG_INSTALL_DIR)/usr/lib/libapr-1.{la,a,so*} \
		$(1)/usr/lib/
	$(CP)   $(PKG_INSTALL_DIR)/usr/lib/pkgconfig/apr-1.pc \
		$(1)/usr/lib/pkgconfig/
	$(CP)   $(PKG_INSTALL_DIR)/usr/share/build-1/* \
		$(1)/usr/share/build-1/
	$(SED) '/^prefix=\|^exec_prefix=/s|/usr|$(STAGING_DIR)/usr|' \
					$(1)/usr/bin/apr-1-config
	$(SED) '/^bindir=/s|/usr|$$$${prefix}|' $(1)/usr/bin/apr-1-config
	$(SED) '/^datadir=/s|/usr|$$$${prefix}|' $(1)/usr/bin/apr-1-config
	$(SED) '/^datarootdir=/s|/usr|$$$${prefix}|' $(1)/usr/bin/apr-1-config
	$(SED) '/^installbuilddir=/s|/usr|$$$${prefix}|' $(1)/usr/bin/apr-1-config
	$(SED) '/^includedir=/s|/usr|$$$${prefix}|' $(1)/usr/bin/apr-1-config
	$(SED) 's,/usr/share/build-1,$(STAGING_DIR)/usr/share/build-1,g' \
				$(1)/usr/share/build-1/apr_rules.mk
	$(INSTALL_DIR) $(2)/bin
	$(LN) ../../usr/bin/apr-1-config $(2)/bin/apr-1-config
endef

define Package/libapr/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libapr-1.so.* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libapr))
