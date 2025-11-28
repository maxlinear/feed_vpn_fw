#
# Copyright (C) 2020-2023 MaxLinear, Inc.
# Copyright (C) 2019 Intel Corporation
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
# Openwrt feed Makefile for MaxLinear vpn-firmware
#

include $(TOPDIR)/rules.mk

PKG_NAME:=vpn-firmware
PKG_VERSION:=2.13.3
PKG_SOURCE_VERSION:=$(PKG_VERSION)
PKG_SOURCE_PROTO:=git
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_PROTO).tar.gz
PKG_PROJECT:=maxlinear
PKG_SOURCE_NAME:=vpn-firmware
CONFIG_UGW_PKG_SOURCE_URL:=https://github.com
PKG_RELEASE:=1
PKG_SOURCE_URL:=$(CONFIG_UGW_PKG_SOURCE_URL)/$(PKG_PROJECT)/$(PKG_SOURCE_NAME).git
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_SOURCE_VERSION)
PKG_MIRROR_HASH:=9dafb7607413383400bb49e8952ad1a7e1d0b4045036d2740d0b0d4f111313f2
PKG_MAINTAINER:=MaxLinear
PKG_LICENSE:=MaxLinear
PKG_MXL_LICENSE:=MaxLinear/LICENSE

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)/Default
  SECTION:=firmware
  CATEGORY:=MaxLinear
  SUBMENU:=Firmware
  URL:=http://www.maxlinear.com
  MAINTAINER:=MaxLinear Inc
endef

define Package/$(PKG_NAME)-lgm
  $(call Package/$(PKG_NAME)/Default)
  TITLE:=VPN Firmware for LGM
endef

define Build/Compile
endef

define Package/$(PKG_NAME)-lgm/install
	$(INSTALL_DIR) $(1)/lib/firmware
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/vpn_fw.img \
		$(1)/lib/firmware/vpn_fw.img
endef

$(eval $(call BuildPackage,$(PKG_NAME)-lgm))
