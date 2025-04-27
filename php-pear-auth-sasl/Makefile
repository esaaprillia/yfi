#
# Copyright (C) 2007-2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=php-pear-auth-sasl
PKG_VERSION:=1.2.0
PKG_RELEASE:=1

PKG_SOURCE:=Auth_SASL-$(PKG_VERSION).tgz
PKG_SOURCE_URL:=http://download.pear.php.net/package/
PKG_MD5SUM:=skip

PKG_BUILD_DIR:=$(BUILD_DIR)/Auth_SASL-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/php-pear-auth-sasl
  SUBMENU:=PHP
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=Auth_SASL
  URL:=http://pear.php.net/package/Auth_SASL
  DEPENDS:=+php-pear
endef

define Build/Configure
endef

define Build/Compile
endef

define Package/php-pear-auth-sasl/install
	$(INSTALL_DIR) $(1)/usr/lib/php
	$(CP)	$(PKG_BUILD_DIR)/Auth \
		$(1)/usr/lib/php/
endef

$(eval $(call BuildPackage,php-pear-auth-sasl))

