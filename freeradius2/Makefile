#
# Copyright (C) 2008-2020 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=freeradius2
PKG_VERSION:=2.2.10
PKG_RELEASE:=1

PKG_SOURCE:=freeradius-server-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://www.freeradius.org/ftp/pub/freeradius/
PKG_HASH:=skip

PKG_MAINTAINER:=
PKG_LICENSE:=GPL-2.0
PKG_LICENSE_FILES:=COPYRIGHT LICENSE
PKG_CPE_ID:=cpe:/a:freeradius:freeradius

PKG_BUILD_DIR:=$(BUILD_DIR)/freeradius-server-$(PKG_VERSION)
PKG_FIXUP:=autoreconf

PKG_CONFIG_DEPENDS := \
  FREERADIUS2_OPENSSL \
  FREERADIUS2_NOSSL

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/perl/perlver.mk

define Package/freeradius2/config
  source "$(SOURCE)/Config.in"
endef

define Package/freeradius2/Default
  SECTION:=net
  CATEGORY:=Network
  URL:=https://freeradius.org/
  SUBMENU:=FreeRADIUS (version 2)
endef

define Package/freeradius2
  $(call Package/freeradius2/Default)
  DEPENDS:=+freeradius2-common
  TITLE:=A flexible RADIUS server (version 2)
endef

define Package/freeradius2/conffiles
/etc/freeradius2/clients.conf
/etc/freeradius2/radiusd.conf
/etc/freeradius2/policy.conf
/etc/freeradius2/proxy.conf
/etc/freeradius2/sites-available/default
/etc/freeradius2/sites-enabled/default
endef

define Package/freeradius2-common
  $(call Package/freeradius2/Default)
  TITLE:=common files
  DEPENDS:=+libpthread +libltdl +libreadline +libpcap +FREERADIUS2_OPENSSL:libopenssl
endef

define Package/freeradius2-default
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2 \
+freeradius2-democerts \
+freeradius2-mod-always \
+freeradius2-mod-attr-filter \
+freeradius2-mod-attr-rewrite \
+freeradius2-mod-chap \
+freeradius2-mod-detail \
+freeradius2-mod-digest \
+freeradius2-mod-eap \
+freeradius2-mod-eap-gtc \
+freeradius2-mod-eap-leap \
+freeradius2-mod-eap-md5 \
+freeradius2-mod-eap-mschapv2 \
+freeradius2-mod-eap-peap \
+freeradius2-mod-eap-tls \
+freeradius2-mod-eap-ttls \
+freeradius2-mod-exec \
+freeradius2-mod-expiration \
+freeradius2-mod-expr \
+freeradius2-mod-files \
+freeradius2-mod-logintime \
+freeradius2-mod-mschap \
+freeradius2-mod-pap \
+freeradius2-mod-preprocess \
+freeradius2-mod-radutmp \
+freeradius2-mod-realm \
+freeradius2-mod-unix
  TITLE:=Modules needed for Radius default configuration
endef

define Package/freeradius2-default/description
 This meta-package contains only dependencies for modules needed in
 FreeRADIUS default configuration.
endef

define Package/freeradius2-democerts
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=Demo certificates to test the server
endef

define Package/freeradius2-mod-acct-unique
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=Acct-unique module
endef

define Package/freeradius2-mod-acct-unique/conffiles
/etc/freeradius2/modules/acct_unique
endef

define Package/freeradius2-mod-acctlog
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=Acctlog module
endef

define Package/freeradius2-mod-always
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=Always module
endef

define Package/freeradius2-mod-always/conffiles
/etc/freeradius2/modules/always
endef

define Package/freeradius2-mod-attr-filter
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=ATTR filter module
endef

define Package/freeradius2-mod-attr-filter/conffiles
/etc/freeradius2/modules/attr_filter
/etc/freeradius2/attrs
/etc/freeradius2/attrs.access_challenge
/etc/freeradius2/attrs.access_reject
/etc/freeradius2/attrs.accounting_response
/etc/freeradius2/attrs.pre-proxy
endef

define Package/freeradius2-mod-attr-rewrite
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=ATTR rewrite module
endef

define Package/freeradius2-mod-attr-rewrite/conffiles
/etc/freeradius2/modules/attr_rewrite
endef

define Package/freeradius2-mod-cache
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=DATASTORE CACHE
endef

define Package/freeradius2-mod-cache/conffiles
/etc/freeradius2/modules/cache
endef

define Package/freeradius2-mod-chap
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=CHAP module
endef

define Package/freeradius2-mod-chap/conffiles
/etc/freeradius2/modules/chap
endef

define Package/freeradius2-mod-checkval
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=Module checkval
endef

define Package/freeradius2-mod-checkval/conffiles
/etc/freeradius2/modules/checkval
endef

define Package/freeradius2-mod-copy-packet
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=Module copy-packet
endef

define Package/freeradius2-mod-counter
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2 +libgdbm
  TITLE:=Module counter
endef

define Package/freeradius2-mod-counter/conffiles
/etc/freeradius2/modules/counter
endef

define Package/freeradius2-mod-dbm
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2 +libgdbm
  TITLE:=Module dbm
endef

define Package/freeradius2-mod-detail
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=Detailed accounting module
endef

define Package/freeradius2-mod-detail/conffiles
/etc/freeradius2/modules/detail
endef

define Package/freeradius2-mod-digest
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=HTTP Digest Authentication
endef

define Package/freeradius2-mod-digest/conffiles
/etc/freeradius2/modules/digest
endef

define Package/freeradius2-mod-dynamic-clients
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=Dynamic Clients Authentication
endef

define Package/freeradius2-mod-dynamic-clients/conffiles
/etc/freeradius2/modules/dynamic_clients
endef

define Package/freeradius2-mod-eap
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=Base EAP module
endef

define Package/freeradius2-mod-eap/conffiles
/etc/freeradius2/eap.conf
/etc/freeradius2/modules/inner-eap
/etc/freeradius2/sites-available/inner-tunnel
/etc/freeradius2/sites-available/proxy-inner-tunnel
endef

define Package/freeradius2-mod-eap-gtc
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2-mod-eap
  TITLE:=EAP/GTC module
endef

define Package/freeradius2-mod-eap-leap
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2-mod-eap
  TITLE:=EAP/LEAP module
endef

define Package/freeradius2-mod-eap-md5
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2-mod-eap
  TITLE:=EAP/MD5 module
endef

define Package/freeradius2-mod-eap-mschapv2
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2-mod-eap +freeradius2-mod-mschap
  TITLE:=EAP/MS-CHAPv2 module
endef

define Package/freeradius2-mod-eap-peap
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2-mod-eap @FREERADIUS2_OPENSSL
  TITLE:=EAP/PEAP module
endef

define Package/freeradius2-mod-eap-sim
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2-mod-eap
  TITLE:=EAP/SIM module
endef

define Package/freeradius2-mod-eap-tls
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2-mod-eap @FREERADIUS2_OPENSSL
  TITLE:=EAP/TLS module
endef

define Package/freeradius2-mod-eap-ttls
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2-mod-eap-tls
  TITLE:=EAP/TTLS module
endef

define Package/freeradius2-mod-exec
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=EXEC module
endef

define Package/freeradius2-mod-exec/conffiles
/etc/freeradius2/modules/exec
endef

define Package/freeradius2-mod-expiration
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=Expiration module
endef

define Package/freeradius2-mod-expiration/conffiles
/etc/freeradius2/modules/expiration
endef

define Package/freeradius2-mod-expr
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=EXPR module
endef

define Package/freeradius2-mod-expr/conffiles
/etc/freeradius2/modules/expr
endef

define Package/freeradius2-mod-fastusers
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=Fastusers module
endef

define Package/freeradius2-mod-files
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=Module using local files for authorization
endef

define Package/freeradius2-mod-files/conffiles
/etc/freeradius2/users
/etc/freeradius2/acct_users
/etc/freeradius2/preproxy_users
/etc/freeradius2/modules/files
endef

define Package/freeradius2-mod-ippool
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2 +libgdbm
  TITLE:=Radius IP Pool module
endef

define Package/freeradius2-mod-ippool/conffiles
/etc/freeradius2/modules/ippool
endef

define Package/freeradius2-mod-krb5
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2 +krb5-libs
  TITLE:=Krb5 module
endef

define Package/freeradius2-mod-krb5/conffiles
/etc/freeradius2/modules/krb5
endef

define Package/freeradius2-mod-ldap
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2 +libopenldap @FREERADIUS2_OPENSSL
  TITLE:=LDAP Authentication
endef

define Package/freeradius2-mod-ldap/conffiles
/etc/freeradius2/modules/ldap
endef

define Package/freeradius2-mod-linelog
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=Linelog module
endef

define Package/freeradius2-mod-linelog/conffiles
/etc/freeradius2/modules/linelog
endef

define Package/freeradius2-mod-logintime
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=Logintime module
endef

define Package/freeradius2-mod-logintime/conffiles
/etc/freeradius2/modules/logintime
endef

define Package/freeradius2-mod-mschap
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=MS-CHAP and MS-CHAPv2 module
endef

define Package/freeradius2-mod-mschap/conffiles
/etc/freeradius2/modules/mschap
endef

define Package/freeradius2-mod-otp
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=Otp module
endef

define Package/freeradius2-mod-otp/conffiles
/etc/freeradius2/modules/otp
endef

define Package/freeradius2-mod-pam
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2 +libpam
  TITLE:=PAM module
endef

define Package/freeradius2-mod-pam/conffiles
/etc/freeradius2/modules/pam
endef

define Package/freeradius2-mod-pap
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=PAP module
endef

define Package/freeradius2-mod-pap/conffiles
/etc/freeradius2/modules/pap
endef

define Package/freeradius2-mod-passwd
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=Rlm passwd module
endef

define Package/freeradius2-mod-passwd/conffiles
/etc/freeradius2/modules/passwd
endef

define Package/freeradius2-mod-perl
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2 +perl +perlbase-essential +perlbase-data
  TITLE:=Perl module
endef

define Package/freeradius2-mod-perl/conffiles
/etc/freeradius2/modules/perl
endef

define Package/freeradius2-mod-policy
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=Policy module
endef

define Package/freeradius2-mod-policy/conffiles
/etc/freeradius2/modules/policy
/etc/freeradius2/policy.txt
endef

define Package/freeradius2-mod-preprocess
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=Request pre-processing module
endef

define Package/freeradius2-mod-preprocess/conffiles
/etc/freeradius2/hints
/etc/freeradius2/huntgroups
/etc/freeradius2/modules/preprocess
endef

define Package/freeradius2-mod-radutmp
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=Radius UTMP module
endef

define Package/freeradius2-mod-radutmp/conffiles
/etc/freeradius2/modules/radutmp
/etc/freeradius2/modules/sradutmp
endef

define Package/freeradius2-mod-realm
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=Realms handling module
endef

define Package/freeradius2-mod-realm/conffiles
/etc/freeradius2/modules/realm
endef

define Package/freeradius2-mod-replicate
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=Replicate module
endef

define Package/freeradius2-mod-replicate/conffiles
/etc/freeradius2/modules/replicate
endef

define Package/freeradius2-mod-soh
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=SoH module
endef

define Package/freeradius2-mod-soh/conffiles
/etc/freeradius2/modules/soh
endef

define Package/freeradius2-mod-sql
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=Radius generic SQL front-end
endef

define Package/freeradius2-mod-sql/conffiles
/etc/freeradius2/sql.conf
endef

define Package/freeradius2-mod-sql-mysql
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2-mod-sql +libmysqlclient-r
  TITLE:=Radius MySQL back-end drivers
endef

define Package/freeradius2-mod-sql-mysql/conffiles
/etc/freeradius2/sql/mysql
endef

define Package/freeradius2-mod-sql-postgresql
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2-mod-sql +libpq
  TITLE:=Radius PostgreSQL back-end drivers
endef

define Package/freeradius2-mod-sql-postgresql/conffiles
/etc/freeradius2/sql/postgresql
endef

define Package/freeradius2-mod-sql-sqlite
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2-mod-sql +libsqlite3
  TITLE:=Radius SQLite back-end drivers
endef

define Package/freeradius2-mod-sql-unixodbc
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2-mod-sql +unixodbc
  TITLE:=Radius unixODBC back-end drivers
endef

define Package/freeradius2-mod-sql-log
  $(call Package/freeradius2/Default)
  DEPENDS:=+freeradius2-mod-sql
  TITLE:=Module sql-log
endef

define Package/freeradius2-mod-sql-log/conffiles
/etc/freeradius2/modules/sql_log
endef

define Package/freeradius2-mod-sqlcounter
  $(call Package/freeradius2/Default)
  DEPENDS:=+freeradius2-mod-sql
  TITLE:=Module sqlcounter
endef

define Package/freeradius2-mod-sqlippool
  $(call Package/freeradius2/Default)
  DEPENDS:=+freeradius2-mod-sql
  TITLE:=Radius SQL Based IP Pool module
endef

define Package/freeradius2-mod-sqlippool/conffiles
/etc/freeradius2/sqlippool.conf
/etc/freeradius2/modules/dhcp_sqlippool
endef

define Package/freeradius2-mod-unix
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=System Authentication
endef

define Package/freeradius2-mod-unix/conffiles
/etc/freeradius2/modules/unix
endef

define Package/freeradius2-mod-wimax
  $(call Package/freeradius2/Default)
  DEPENDS:=freeradius2
  TITLE:=Wimax Authentication
endef

define Package/freeradius2-mod-wimax/conffiles
/etc/freeradius2/modules/wimax
endef

define Package/freeradius2-utils
  $(call Package/freeradius2/Default)
  DEPENDS:=+freeradius2-common
  TITLE:=Misc. client utilities
endef

CONFIGURE_ARGS+= \
	--libdir=/usr/lib/freeradius2 \
	--libexecdir=/usr/lib/freeradius2 \
	--disable-developer \
	--with-threads \
	$(if $(CONFIG_FREERADIUS2_OPENSSL),--with,--without)-openssl \
	$(if $(CONFIG_FREERADIUS2_OPENSSL),--with-openssl-includes="$(STAGING_DIR)/usr/include",) \
	$(if $(CONFIG_FREERADIUS2_OPENSSL),--with-openssl-libraries="$(STAGING_DIR)/usr/lib",) \
	$(if $(CONFIG_FREERADIUS2_OPENSSL),--disable-openssl-version-check,) \
	--with-system-libtool \
	--with-system-libltdl \
	--enable-strict-dependencies \
	--with-dictdir=/usr/share/freeradius2 \
	--with-raddbdir=/etc/freeradius2 \
	--with-radacctdir=/var/db/radacct \
	--with-logdir=/var/log \
	--without-rlm_eap_ikev2 \
	--without-rlm_eap_tnc \
	--without-rlm_python \
	--without-rlm_sql_db2 \
	--without-rlm_sql_firebird \
	--without-rlm_sql_freetds \
	--without-rlm_sql_iodbc \
	--without-rlm_sql_oracle \
	--without-rlm_sql_sybase

PKG_DICTIONARIES:= \
	compat \
	freeradius freeradius.internal \
	rfc2865 rfc2866 rfc2867 rfc2868 rfc2869 rfc3162 rfc3576 rfc3580 \
	rfc4372 rfc4675 rfc4679 \
	microsoft \
	wispr \

ifneq ($(SDK)$(CONFIG_PACKAGE_freeradius2-mod-dbm),)
  CONFIGURE_ARGS+= \
		--with-rlm_dbm \
		--with-rlm_dbm-include-dir="$(STAGING_DIR)/usr/include" \
		--with-rlm_dbm-lib-dir="$(STAGING_DIR)/usr/lib"
else
  CONFIGURE_ARGS+= --without-rlm_dbm
endif

ifneq ($(SDK)$(CONFIG_PACKAGE_freeradius2-mod-eap-peap),)
  CONFIGURE_ARGS+= \
		--with-rlm_eap_peap \
		--with-rlm_eap_peap-include-dir="$(STAGING_DIR)/usr/include" \
		--with-rlm_eap_peap-lib-dir="$(STAGING_DIR)/usr/lib"
  CONFIGURE_LIBS+= -lcrypto -lssl
else
  CONFIGURE_ARGS+= --without-rlm_eap_peap
endif

ifneq ($(SDK)$(CONFIG_PACKAGE_freeradius2-mod-eap-tls),)
  CONFIGURE_ARGS+= \
		--with-rlm_eap_tls \
		--with-rlm_eap_tls-include-dir="$(STAGING_DIR)/usr/include" \
		--with-rlm_eap_tls-lib-dir="$(STAGING_DIR)/usr/lib"
  CONFIGURE_LIBS+= -lcrypto -lssl
else
  CONFIGURE_ARGS+= --without-rlm_eap_tls
endif

ifneq ($(SDK)$(CONFIG_PACKAGE_freeradius2-mod-eap-ttls),)
  CONFIGURE_ARGS+= \
		--with-rlm_eap_ttls \
		--with-rlm_eap_ttls-include-dir="$(STAGING_DIR)/usr/include" \
		--with-rlm_eap_ttls-lib-dir="$(STAGING_DIR)/usr/lib"
  CONFIGURE_LIBS+= -lcrypto -lssl
else
  CONFIGURE_ARGS+= --without-rlm_eap_ttls
endif

ifneq ($(SDK)$(CONFIG_PACKAGE_freeradius2-mod-ippool),)
  CONFIGURE_ARGS+= --with-rlm_ippool \
		--with-rlm_ippool-include-dir="$(STAGING_DIR)/usr/include" \
		--with-rlm_ippool-lib-dir="$(STAGING_DIR)/usr/lib"
else
  CONFIGURE_ARGS+= --without-rlm_ippool
endif

ifneq ($(SDK)$(CONFIG_PACKAGE_freeradius2-mod-krb5),)
  CONFIGURE_ARGS+= \
		--with-rlm_krb5 \
		--with-rlm_krb5-include-dir="$(STAGING_DIR)/usr/include" \
		--with-rlm_krb5-lib-dir="$(STAGING_DIR)/usr/lib"
else
  CONFIGURE_ARGS+= --without-rlm_krb5
endif

ifneq ($(SDK)$(CONFIG_PACKAGE_freeradius2-mod-ldap),)
  CONFIGURE_ARGS+= --with-rlm_ldap \
		--with-rlm_ldap-include-dir="$(STAGING_DIR)/usr/include" \
		--with-rlm_ldap-lib-dir="$(STAGING_DIR)/usr/lib"
else
  CONFIGURE_ARGS+= --without-rlm_ldap
endif

ifneq ($(SDK)$(CONFIG_PACKAGE_freeradius2-mod-perl),)
  PERL_SITELIB:=/usr/lib/perl$(PERL_MAJOR)/$(PERL_VERSION2)
  CONFIGURE_ARGS+= \
		--with-rlm_perl
  CONFIGURE_VARS+= \
	PERL="$(STAGING_DIR_HOSTPKG)/usr/bin/perl$(PERL_VERSION)" \
	CFLAGS="-D_LARGEFILE_SOURCE $(if $(CONFIG_USE_MUSL),-D_LARGEFILE64_SOURCE) -D_FILE_OFFSET_BITS=64 -D_REENTRANT -D_GNU_SOURCE -I$(STAGING_DIR)$(PERL_SITELIB)/CORE" \
	LDFLAGS="-Wl,-rpath,$(PERL_SITELIB)/CORE -L$(STAGING_DIR)$(PERL_SITELIB)/CORE"
else
  CONFIGURE_ARGS+= --without-rlm_perl
endif

ifneq ($(SDK)$(CONFIG_PACKAGE_freeradius2-mod-attr-rewrite),)
  CONFIGURE_ARGS+= --with-rlm_attr_rewrite
else
  CONFIGURE_ARGS+= --without-rlm_attr_rewrite
endif

ifneq ($(SDK)$(CONFIG_PACKAGE_freeradius2-mod-radutmp),)
  CONFIGURE_ARGS+= --with-rlm_radutmp
else
  CONFIGURE_ARGS+= --without-rlm_radutmp
endif

ifneq ($(SDK)$(CONFIG_PACKAGE_freeradius2-mod-sql),)
  CONFIGURE_ARGS+= --with-rlm_sql
else
  CONFIGURE_ARGS+= --without-rlm_sql
endif

ifneq ($(SDK)$(CONFIG_PACKAGE_freeradius2-mod-sql-mysql),)
  CONFIGURE_ARGS+= \
		--with-rlm_sql_mysql \
		--with-mysql-include-dir="$(STAGING_DIR)/usr/include" \
		--with-mysql-lib-dir="$(STAGING_DIR)/usr/lib/mysql"
else
  CONFIGURE_ARGS+= --without-rlm_sql_mysql
endif

ifneq ($(SDK)$(CONFIG_PACKAGE_freeradius2-mod-sql-postgresql),)
  CONFIGURE_ARGS+= --with-rlm_sql_postgresql
else
  CONFIGURE_ARGS+= --without-rlm_sql_postgresql
endif

ifneq ($(SDK)$(CONFIG_PACKAGE_freeradius2-mod-sql-sqlite),)
  CONFIGURE_ARGS+= --with-rlm_sql_sqlite
else
  CONFIGURE_ARGS+= --without-rlm_sql_sqlite
endif

ifneq ($(SDK)$(CONFIG_PACKAGE_freeradius2-mod-sql-unixodbc),)
  CONFIGURE_ARGS+= \
		--with-rlm_sql_unixodbc \
		--with-rlm_sql_unixodbc-include-dir="$(STAGING_DIR)/usr/include" \
		--with-rlm_sql_unixodbc-lib-dir="$(STAGING_DIR)/usr/lib"
else
  CONFIGURE_ARGS+= --without-rlm_sql_unixodbc
endif

ifneq ($(SDK)$(CONFIG_PACKAGE_freeradius2-mod-sqlcounter),)
  CONFIGURE_ARGS+= --with-rlm_sqlcounter
else
  CONFIGURE_ARGS+= --without-rlm_sqlcounter
endif

ifneq ($(SDK)$(CONFIG_PACKAGE_freeradius2-mod-sqlippool),)
  CONFIGURE_ARGS+= --with-rlm_sqlippool
else
  CONFIGURE_ARGS+= --without-rlm_sqlippool
endif

ifneq ($(SDK)$(CONFIG_PACKAGE_freeradius2-mod-unix),)
  CONFIGURE_ARGS+= --with-rlm_unix
else
  CONFIGURE_ARGS+= --without-rlm_unix
endif

CONFIGURE_VARS+= \
	LDFLAGS="$$$$LDFLAGS" \
	LIBS="$(CONFIGURE_LIBS)" \
	MYSQL_CONFIG="no" \
	ac_cv_lib_readline=no \

define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR) \
		R="$(PKG_INSTALL_DIR)" \
		INSTALLSTRIP="" \
		LIBTOOL="$(STAGING_DIR)/host/libltdl/bin/libtool" \
		all certs install
endef

define Package/freeradius2-common/install
	$(INSTALL_DIR) $(1)/etc/freeradius2
	chmod 771 $(1)/etc/freeradius2
	$(CP) $(PKG_INSTALL_DIR)/etc/freeradius2/dictionary $(1)/etc/freeradius2/ ; \
	$(INSTALL_DIR) $(1)/usr/lib/freeradius2
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/freeradius2/libfreeradius-{dhcp,eap,radius,server}.so $(1)/usr/lib/freeradius2
	$(INSTALL_DIR) $(1)/usr/share/freeradius2
	$(CP) $(PKG_INSTALL_DIR)/usr/share/freeradius2/dictionary $(1)/usr/share/freeradius2/
	$(SED) "s,^\(\$$$$INCLUDE\),#\1,g" $(1)/usr/share/freeradius2/dictionary
	for f in $(PKG_DICTIONARIES); do \
		$(CP) $(PKG_INSTALL_DIR)/usr/share/freeradius2/dictionary.$$$${f} $(1)/usr/share/freeradius2/ ; \
		$(SED) "s,^#\(\$$$$INCLUDE dictionary\.$$$${f}\)$$$$,\1,g" $(1)/usr/share/freeradius2/dictionary ; \
	done
endef

define Package/freeradius2/install
	$(INSTALL_DIR) $(1)/etc/freeradius2
	$(INSTALL_DIR) $(1)/etc/freeradius2/modules
	$(INSTALL_DIR) $(1)/etc/freeradius2/sites-available
	$(INSTALL_DIR) $(1)/etc/freeradius2/sites-enabled
	for f in clients.conf radiusd.conf policy.conf proxy.conf; do \
		$(CP) $(PKG_INSTALL_DIR)/etc/freeradius2/$$$${f} $(1)/etc/freeradius2/ ; \
	done
	for f in default; do \
		$(CP) $(PKG_INSTALL_DIR)/etc/freeradius2/sites-available/$$$${f} $(1)/etc/freeradius2/sites-available/ ; \
		$(CP) $(PKG_INSTALL_DIR)/etc/freeradius2/sites-enabled/$$$${f} $(1)/etc/freeradius2/sites-enabled/ ; \
	done

	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/radiusd $(1)/usr/sbin/
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/radiusd.init $(1)/etc/init.d/radiusd
endef

define Package/freeradius2-default/install
	true
endef

define Package/freeradius2-democerts/install
	$(INSTALL_DIR) $(1)/etc/freeradius2/certs
	$(CP) \
		$(PKG_INSTALL_DIR)/etc/freeradius2/certs/ca.pem \
		$(PKG_INSTALL_DIR)/etc/freeradius2/certs/dh \
		$(PKG_INSTALL_DIR)/etc/freeradius2/certs/random \
		$(PKG_INSTALL_DIR)/etc/freeradius2/certs/server.pem \
		$(1)/etc/freeradius2/certs/
endef

define Package/freeradius2-utils/install
	$(INSTALL_DIR) $(1)/usr/bin
	for f in radclient radeapclient radtest radwho; do \
		$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/$$$${f} $(1)/usr/bin/ ; \
	done
endef

define BuildPlugin
  define Package/$(1)/install
	[ -z "$(2)" ] || $(INSTALL_DIR) $$(1)/usr/lib/freeradius2
	for m in $(2); do \
		$(CP) $(PKG_INSTALL_DIR)/usr/lib/freeradius2/$$$$$$$${m}.so $$(1)/usr/lib/freeradius2 ; \
	done
	# Install configuration files
	for f in $(strip $(call Package/$(1)/conffiles)); do \
		$(INSTALL_DIR) $$(1)/$$$$$$$${f%/*} ; \
		$(CP) $(PKG_INSTALL_DIR)/$$$$$$$${f} $$(1)/$$$$$$$${f}; \
	done
  endef

  $$(eval $$(call BuildPackage,$(1)))
endef


$(eval $(call BuildPackage,freeradius2))
$(eval $(call BuildPackage,freeradius2-common))
$(eval $(call BuildPackage,freeradius2-default))
$(eval $(call BuildPackage,freeradius2-democerts))
$(eval $(call BuildPlugin,freeradius2-mod-acct-unique,rlm_acct_unique,))
$(eval $(call BuildPlugin,freeradius2-mod-acctlog,rlm_acctlog,))
$(eval $(call BuildPlugin,freeradius2-mod-always,rlm_always,))
$(eval $(call BuildPlugin,freeradius2-mod-attr-filter,rlm_attr_filter,))
$(eval $(call BuildPlugin,freeradius2-mod-attr-rewrite,rlm_attr_rewrite,))
$(eval $(call BuildPlugin,freeradius2-mod-cache,rlm_cache,))
$(eval $(call BuildPlugin,freeradius2-mod-chap,rlm_chap,))
$(eval $(call BuildPlugin,freeradius2-mod-checkval,rlm_checkval,))
$(eval $(call BuildPlugin,freeradius2-mod-copy-packet,rlm_copy_packet,))
$(eval $(call BuildPlugin,freeradius2-mod-counter,rlm_counter,))
$(eval $(call BuildPlugin,freeradius2-mod-dbm,rlm_dbm,))
$(eval $(call BuildPlugin,freeradius2-mod-detail,rlm_detail,))
$(eval $(call BuildPlugin,freeradius2-mod-digest,rlm_digest,))
$(eval $(call BuildPlugin,freeradius2-mod-dynamic-clients,rlm_dynamic_clients,))
$(eval $(call BuildPlugin,freeradius2-mod-eap,rlm_eap,))
$(eval $(call BuildPlugin,freeradius2-mod-eap-gtc,rlm_eap_gtc,))
$(eval $(call BuildPlugin,freeradius2-mod-eap-leap,rlm_eap_leap,))
$(eval $(call BuildPlugin,freeradius2-mod-eap-md5,rlm_eap_md5,))
$(eval $(call BuildPlugin,freeradius2-mod-eap-mschapv2,rlm_eap_mschapv2,))
$(eval $(call BuildPlugin,freeradius2-mod-eap-peap,rlm_eap_peap,))
$(eval $(call BuildPlugin,freeradius2-mod-eap-sim,rlm_eap_sim,))
$(eval $(call BuildPlugin,freeradius2-mod-eap-tls,rlm_eap_tls,))
$(eval $(call BuildPlugin,freeradius2-mod-eap-ttls,rlm_eap_ttls,))
$(eval $(call BuildPlugin,freeradius2-mod-exec,rlm_exec,))
$(eval $(call BuildPlugin,freeradius2-mod-expiration,rlm_expiration,))
$(eval $(call BuildPlugin,freeradius2-mod-expr,rlm_expr,))
$(eval $(call BuildPlugin,freeradius2-mod-fastusers,rlm_fastusers,))
$(eval $(call BuildPlugin,freeradius2-mod-files,rlm_files,))
$(eval $(call BuildPlugin,freeradius2-mod-ippool,rlm_ippool,))
$(eval $(call BuildPlugin,freeradius2-mod-krb5,rlm_krb5,))
$(eval $(call BuildPlugin,freeradius2-mod-ldap,rlm_ldap,))
$(eval $(call BuildPlugin,freeradius2-mod-linelog,rlm_linelog,))
$(eval $(call BuildPlugin,freeradius2-mod-logintime,rlm_logintime,))
$(eval $(call BuildPlugin,freeradius2-mod-mschap,rlm_mschap,))
$(eval $(call BuildPlugin,freeradius2-mod-otp,rlm_otp,))
$(eval $(call BuildPlugin,freeradius2-mod-pam,rlm_pam,))
$(eval $(call BuildPlugin,freeradius2-mod-pap,rlm_pap,))
$(eval $(call BuildPlugin,freeradius2-mod-passwd,rlm_passwd,))
$(eval $(call BuildPlugin,freeradius2-mod-perl,rlm_perl,))
$(eval $(call BuildPlugin,freeradius2-mod-policy,rlm_policy,))
$(eval $(call BuildPlugin,freeradius2-mod-preprocess,rlm_preprocess,))
$(eval $(call BuildPlugin,freeradius2-mod-radutmp,rlm_radutmp,))
$(eval $(call BuildPlugin,freeradius2-mod-realm,rlm_realm,))
$(eval $(call BuildPlugin,freeradius2-mod-replicate,rlm_replicate,))
$(eval $(call BuildPlugin,freeradius2-mod-soh,rlm_soh,))
$(eval $(call BuildPlugin,freeradius2-mod-sql,rlm_sql,))
$(eval $(call BuildPlugin,freeradius2-mod-sql-mysql,rlm_sql_mysql,))
$(eval $(call BuildPlugin,freeradius2-mod-sql-postgresql,rlm_sql_postgresql,))
$(eval $(call BuildPlugin,freeradius2-mod-sql-sqlite,rlm_sql_sqlite,))
$(eval $(call BuildPlugin,freeradius2-mod-sql-unixodbc,rlm_sql_unixodbc,))
$(eval $(call BuildPlugin,freeradius2-mod-sql-log,rlm_sql_log,))
$(eval $(call BuildPlugin,freeradius2-mod-sqlcounter,rlm_sqlcounter,))
$(eval $(call BuildPlugin,freeradius2-mod-sqlippool,rlm_sqlippool,))
$(eval $(call BuildPlugin,freeradius2-mod-unix,rlm_unix,))
$(eval $(call BuildPlugin,freeradius2-mod-wimax,rlm_wimax,))
$(eval $(call BuildPackage,freeradius2-utils))
