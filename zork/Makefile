#
# Copyright (C) 2011-2018 Entware
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
# Abandoned in 2014

include $(TOPDIR)/rules.mk

PKG_NAME:=zork
PKG_VERSION:=1.0-20140806
PKG_REV:=ba0426c1e568a35d7a8d86a1160fea24e4915885
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_URL:=https://github.com/mgius/zork.git
PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=$(PKG_REV)

include $(INCLUDE_DIR)/package.mk

define Package/zork
	SECTION:=games
	CATEGORY:=Games
	TITLE:=Zork (also named as Dungeon) is a text adventure game
	URL:=http://richelbilderbeek.nl/GameZork.htm
	MAINTAINER:=Entware team, https://entware.net
endef

define Package/zork/description
 Zork (also named as Dungeon) is a text adventure game written by
 Tim Anderson, Marc Blank, Bruce Daniels, and Dave Lebling in 1980.
endef

MAKE_FLAGS += LIBS="$(TARGET_LDFLAGS)"

define Build/Compile
	$(CP) ./files/uudecode.c  $(PKG_BUILD_DIR)
	$(HOSTCC) -o $(PKG_BUILD_DIR)/uudecode $(PKG_BUILD_DIR)/uudecode.c
	$(call Build/Compile/Default)
endef

define Package/zork/install
	$(INSTALL_DIR) $(1)/opt/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/dungeon $(1)/opt/bin
	$(INSTALL_DIR) $(1)/opt/share/zork
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/dtextc.dat $(1)/opt/share/zork
	$(INSTALL_DIR) $(1)/opt/var
endef

$(eval $(call BuildPackage,zork))
