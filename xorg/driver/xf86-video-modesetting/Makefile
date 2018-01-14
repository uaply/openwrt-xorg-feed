#
# Copyright (C) 2007-2009 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=xf86-video-modesetting
PKG_VERSION:=0.9.0
PKG_RELEASE:=1

PKG_SOURCE_URL:=http://xorg.freedesktop.org/releases/individual/driver
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_BUILD_DIR:=$(BUILD_DIR)/Xorg/$(PKG_NAME)-$(PKG_VERSION)/
PKG_MD5SUM=cd7d062b83e6bba74da4e56d62b92b1e

PKG_FIXUP:=autoreconf
PKG_REMOVE_FILES:=autogen.sh aclocal.m4

include $(INCLUDE_DIR)/package.mk
$(call include_mk, xorg-driver.mk)

define Package/xf86-video-modesetting
  SECTION:=xorg-driver
  CATEGORY:=Xorg
  SUBMENU:=driver
  DEPENDS:=+xserver-xorg +libdrm +udev
  TITLE:=xf86-video-modesetting
  URL:=http://cgit.freedesktop.org/xorg/driver/xf86-video-modesetting/
endef

#define Build/Configure
#	$(call Build/Configure/Default, \
#		--enable-pciaccess \
#	)
#endef

define Package/xf86-video-modesetting/install
	$(INSTALL_DIR) $(1)/usr/lib/xorg/modules/drivers
	$(INSTALL_DATA) \
		$(PKG_BUILD_DIR)/src/.libs/*.so \
		$(1)/usr/lib/xorg/modules/drivers
endef

$(eval $(call BuildPackage,xf86-video-modesetting))
