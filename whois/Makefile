#
# Copyright (C) 2011-2018 Entware
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=whois
PKG_VERSION:=5.3.2
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)_$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=http://ftp.debian.org/debian/pool/main/w/whois
PKG_HASH:=79714ba89172bca08a2443f59885daa4af0c5f8d6a49bc9e7f2a83559a286354

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
# libidn2.so: undefined reference to `libintl_gettext'
include $(INCLUDE_DIR)/nls.mk

define Package/whois
	SECTION:=net
	CATEGORY:=Network
	DEPENDS:=+libidn2
	TITLE:=intelligent WHOIS client
	URL:=http://ftp.debian.org/debian/pool/main/w/whois
	MAINTAINER:=Entware team, https://entware.net
endef

define Package/whois/description
 This package provides a commandline client for the WHOIS (RFC 3912) protocol,
 which queries online servers for information such as contact details
 for domains and IP address assignments. It can intelligently select
 the appropriate WHOIS server for most queries.
endef

define Package/whois/conffiles
/opt/etc/whois.conf
endef

define Package/whois/install
	$(INSTALL_DIR) $(1)/opt/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/whois $(1)/opt/sbin
	$(INSTALL_DIR) $(1)/opt/etc
	$(INSTALL_CONF) $(PKG_BUILD_DIR)/whois.conf $(1)/opt/etc/whois.conf
endef

$(eval $(call BuildPackage,whois))
