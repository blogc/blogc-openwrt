#
# Copyright (C) 2015 Rafael G. Martins
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=make
PKG_VERSION:=4.1
PKG_RELEASE:=1
PKG_LICENSE:=GPL-3+
PKG_LICENSE_FILES:=COPYING

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://ftp.gnu.org/gnu/make
PKG_MD5SUM:=654f9117957e6fa6a1c49a8f08270ec9

PKG_INSTALL:=1
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/make
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Standard tool to compile source trees
  URL:=https://www.gnu.org/software/make/make.html
  MAINTAINER:=Rafael G. Martins <rafael@rafaelmartins.eng.br>
endef

define Package/make/description
  GNU Make is a tool which controls the generation of executables and
  other non-source files of a program from the program's source files.
endef

CONFIGURE_ARGS += \
	--program-prefix=g \
	--without-guile

define Package/make/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/g$(PKG_NAME) $(1)/usr/bin/
endef

$(eval $(call BuildPackage,make))

