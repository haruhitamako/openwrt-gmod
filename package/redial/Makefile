#
# Copyright (C) 2015 OpenWrt-dist
#
# This is free software, licensed under the GNU General Public License v3.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=redial
PKG_VERSION:=1.0
PKG_RELEASE:=1

PKG_LICENSE:=GPLv3
PKG_LICENSE_FILES:=LICENSE
PKG_MAINTAINER:=ghostry <ghostry@ghostry.cn>

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk

define Package/redial
	SECTION:=net
	CATEGORY:=Gmod
	SUBMENU:=Network
	TITLE:=Get the public network ip
	PKGARCH:=all
	DEPENDS:=
endef

define Package/redial/description
	Get the public network ip
endef

define Build/Prepare
endef

define Build/Configure
endef

define Build/Compile
endef

define Package/redial/postinst
#!/bin/sh
if [ -z "$${IPKG_INSTROOT}" ]; then
	chmod 755 /etc/hotplug.d/iface/59-redial >/dev/null 2>&1
fi
exit 0
endef

define Package/redial/install
	$(INSTALL_DIR) $(1)/etc/hotplug.d/iface
	$(INSTALL_BIN) ./files/root/etc/hotplug.d/iface/59-redial $(1)/etc/hotplug.d/iface/59-redial
endef


$(eval $(call BuildPackage,redial))
