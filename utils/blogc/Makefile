#
# Copyright (C) 2015 Rafael G. Martins
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=blogc
PKG_VERSION:=0.2.1
PKG_RELEASE:=1
PKG_LICENSE:=BSD-3-Clause
PKG_LICENSE_FILES:=LICENSE

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=https://github.com/blogc/$(PKG_NAME)/releases/download/v$(PKG_VERSION)
PKG_MD5SUM:=062e7094cfb60c91416bec4823ee250b

PKG_INSTALL:=1
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/blogc
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=A blog compiler
  URL:=http://blogc.org/
  MAINTAINER:=Rafael G. Martins <rafael@rafaelmartins.eng.br>
endef

define Package/blogc/description
  blogc(1) is a blog compiler. It converts source files and templates into
  blog/website resources.
endef

CONFIGURE_ARGS += \
	--disable-ronn \
	--disable-valgrind \
	--disable-tests

MAKE_FLAGS += \
	CFLAGS="$(TARGET_CFLAGS) -std=gnu99"

define Package/blogc/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/$(PKG_NAME) $(1)/usr/bin/
endef

$(eval $(call BuildPackage,blogc))

