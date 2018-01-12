#
# Copyright (C) 2007-2009 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
# blogic@openwrt.org

include $(TOPDIR)/rules.mk

PKG_NAME:=mkfontscale
PKG_RELEASE:=1
PKG_VERSION:=1.1.2

PKG_SOURCE_URL:=http://www.x.org/releases/individual/app/
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_BUILD_DIR:=$(BUILD_DIR)/Xorg/$(PKG_NAME)-$(PKG_VERSION)/
PKG_MD5SUM:=9bdd6ebfa62b1bbd474906ac86a40fd8
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

TARGET_LDFLAGS+=-Wl,-rpath-link=$(STAGING_DIR)/usr/lib

define Package/mkfontscale
  SECTION:=xorg-app
  CATEGORY:=Xorg
  SUBMENU:=app
  DEPENDS:=+libX11 +libfontenc +libfreetype +libz
  TITLE:=mkfontscale
  URL:=http://www.x.org/
endef

define Package/mkfontscale/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) \
		$(PKG_INSTALL_DIR)/usr/bin/* \
		$(1)/usr/bin
endef

$(eval $(call BuildPackage,mkfontscale))
