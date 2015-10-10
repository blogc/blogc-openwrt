#
# Copyright (C) 2015 Rafael G. Martins
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=blogc-git-receiver
PKG_VERSION:=0.1
PKG_RELEASE:=1
PKG_LICENSE:=BSD-3-Clause
PKG_LICENSE_FILES:=LICENSE

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=https://github.com/blogc/$(PKG_NAME)/releases/download/v$(PKG_VERSION)
PKG_MD5SUM:=994caa16e554aff9ab89daf0507b6a84

PKG_INSTALL:=1
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/blogc-git-receiver
  SECTION:=net
  CATEGORY:=Network
  TITLE:=A simple login shell/git hook to deploy blogc websites
  URL:=http://blogc.org/
  MAINTAINER:=Rafael G. Martins <rafael@rafaelmartins.eng.br>
  DEPENDS:=+git +make
endef

define Package/blogc-git-receiver/description
  A simple login shell/git hook to deploy blogc websites.
endef

MAKE_FLAGS += \
	CFLAGS="$(TARGET_CFLAGS) -std=gnu99"

define Package/blogc-git-receiver/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/$(PKG_NAME) $(1)/usr/bin/
endef

$(eval $(call BuildPackage,blogc-git-receiver))

