#
# Copyright (C) 2011-2018 Entware
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=bindfs
PKG_VERSION:=1.13.9
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://bindfs.org/downloads
PKG_HASH:=acfa2ca9d604f4147c42758ccbb4a429855df26768dfe70521ba5d7a0596f8b5

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/bindfs
	SECTION:=utils
	CATEGORY:=Utilities
	SUBMENU:=Filesystem
	DEPENDS:=+fuse-utils +librt
	TITLE:=bindfs filesystem
	URL:=http://bindfs.org
	MAINTAINER:=Entware team, https://entware.net
endef

define Package/bindfs/description
  bindfs - mount a directory to another location and alter permission bits
endef

TARGET_CFLAGS += -I$(STAGING_DIR)/opt/include/fuse \

define Package/bindfs/install
	$(INSTALL_DIR) $(1)/opt/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/opt/bin/* $(1)/opt/bin
endef

$(eval $(call BuildPackage,bindfs))
