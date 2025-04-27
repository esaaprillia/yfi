#
# Copyright (C) 2007-2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=php-pear-mail-mime
PKG_VERSION:=1.10.12
PKG_RELEASE:=1

PKG_SOURCE:=Mail_Mime-$(PKG_VERSION).tgz
PKG_SOURCE_URL:=http://download.pear.php.net/package/
PKG_MD5SUM:=skip

PKG_BUILD_DIR:=$(BUILD_DIR)/Mail_Mime-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/php-pear-mail-mime
  SUBMENU:=PHP
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=Mail_Mime
  URL:=http://pear.php.net/package/Mail_Mime
  DEPENDS:=+php-pear
endef

define Build/Configure
endef

define Build/Compile
endef

define Package/php-pear-mail-mime/install
	$(INSTALL_DIR) $(1)/usr/lib/php
	$(CP)	$(PKG_BUILD_DIR)/Mail \
		$(1)/usr/lib/php/
endef

$(eval $(call BuildPackage,php-pear-mail-mime))

