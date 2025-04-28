#
# Copyright (C) 2007-2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=php-pear-mdb2
PKG_VERSION:=2.5.0b5
PKG_RELEASE:=1

PKG_SOURCE:=MDB2-$(PKG_VERSION).tgz
PKG_SOURCE_URL:=http://download.pear.php.net/package/
PKG_HASH:=skip

PKG_BUILD_DIR:=$(BUILD_DIR)/MDB2-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/php-pear-mdb2
  SUBMENU:=PHP
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=PEAR MDB2 module
  URL:=https://pear.php.net/package/MDB2
  DEPENDS:=+pear
endef

define Build/Configure
endef

define Build/Compile
endef

define Package/php-pear-mdb2/install
	$(INSTALL_DIR) $(1)/usr/lib/php
	$(CP)	$(PKG_BUILD_DIR)/MDB2.php $(PKG_BUILD_DIR)/MDB2 \
		$(1)/usr/lib/php/
endef

$(eval $(call BuildPackage,php-pear-mdb2))
