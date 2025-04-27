#
# Copyright (C) 2007-2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=php-pear-net-smtp
PKG_VERSION:=1.12.1
PKG_RELEASE:=1

PKG_SOURCE:=Net_SMTP-$(PKG_VERSION).tgz
PKG_SOURCE_URL:=http://download.pear.php.net/package/
PKG_HASH:=skip

PKG_BUILD_DIR:=$(BUILD_DIR)/Net_SMTP-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/php-pear-net-smtp
  SUBMENU:=PHP
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=Net_SMTP
  URL:=http://pear.php.net/package/Net_SMTP
  DEPENDS:=+php-pear +php-pear-net-socket +php-pear-auth-sasl
endef

define Build/Configure
endef

define Build/Compile
endef

define Package/php-pear-net-smtp/install
	$(INSTALL_DIR) $(1)/usr/lib/php
	$(CP)	$(PKG_BUILD_DIR)/Net \
		$(1)/usr/lib/php/
endef

$(eval $(call BuildPackage,php-pear-net-smtp))

