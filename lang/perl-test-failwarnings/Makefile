include $(TOPDIR)/rules.mk

PKG_NAME:=perl-test-failwarnings
PKG_VERSION:=0.008
PKG_RELEASE:=1

PKG_SOURCE:=Test-FailWarnings-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://cpan.metacpan.org/authors/id/D/DA/DAGOLDEN/
PKG_HASH:=skip

PKG_MAINTAINER:=Marcel Denia <naoir@gmx.net>
PKG_LICENSE:=GPL-1.0-or-later Artistic-1.0-Perl

HOST_BUILD_DIR:=$(BUILD_DIR_HOST)/perl/Test-FailWarnings-$(PKG_VERSION)
HOST_BUILD_DEPENDS:=perl/host perl-capture-tiny/host
PKG_BUILD_DIR:=$(BUILD_DIR)/perl/Test-FailWarnings-$(PKG_VERSION)
PKG_BUILD_DEPENDS:=perl/host perl-capture-tiny/host

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/host-build.mk
include ../perl/perlmod.mk

define Package/perl-test-failwarnings
  SUBMENU:=Perl
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=Perl inc latest
  URL:=https://metacpan.org/release/Test-FailWarnings
  DEPENDS:=perl +perlbase-base +perl-capture-tiny
endef

define Host/Configure
        $(call perlmod/host/Configure,,,)
endef

define Host/Compile
        $(call perlmod/host/Compile,,)
endef

define Host/Install
        $(call perlmod/host/Install,$(1),)
endef

define Build/Configure
	$(call perlmod/Configure,,)
endef

define Build/Compile
	$(call perlmod/Compile,,)
endef

define Package/perl-test-failwarnings/install
	$(call perlmod/Install,$(1),Test)
endef

$(eval $(call BuildPackage,perl-test-failwarnings))
$(eval $(call HostBuild))
