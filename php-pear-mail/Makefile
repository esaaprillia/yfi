#
# Copyright (C) 2007-2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=php-pear-mail
PKG_VERSION:=2.0.0
PKG_RELEASE:=1

PKG_SOURCE:=Mail-$(PKG_VERSION).tgz
PKG_SOURCE_URL:=http://download.pear.php.net/package/
PKG_HASH:=skip

PKG_BUILD_DIR:=$(BUILD_DIR)/Mail-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/php-pear-mail
  SUBMENU:=PHP
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=Mail
  URL:=http://pear.php.net/package/Mail
  DEPENDS:=+php-pear +php-pear-net-smtp
endef

define Build/Configure
endef

define Build/Compile
endef

define Package/php-pear-mail/install
	$(INSTALL_DIR) $(1)/usr/lib/php
	$(CP)	$(PKG_BUILD_DIR)/Mail.php $(PKG_BUILD_DIR)/Mail \
		$(1)/usr/lib/php/
endef

$(eval $(call BuildPackage,php-pear-mail))

