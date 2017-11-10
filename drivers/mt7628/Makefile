include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/version.mk

PKG_NAME:=mt7628
PKG_RELEASE:=1
PKG_BUILD_DEPENDS:=base-files
PKG_FILE_DEPENDS:=
PKG_LICENSE:=GPL-2.0

PKG_MAINTAINER:=Hua Shao <nossiac@163.com>

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/kernel.mk

HTDOCS = /www
LUA_LIBRARYDIR = /usr/lib/lua
LUCI_LIBRARYDIR = $(LUA_LIBRARYDIR)/luci


define Package/mt7628
  CATEGORY:=MTK Properties
  SUBMENU:=Drivers
  TITLE:=MTK MT7628 WiFi AP driver
  AUTOLOAD:=$(call AutoProbe,mt7628)
endef


define Package/mt7628/config-notyet
	config MT7628_USING_LUA_SCRIPT
	bool "use lua script to init/config driver"
	depends on PACKAGE_mt7628
	default y
endef

define Build/Compile

endef

define Package/mt7628/install
	$(INSTALL_DIR) $(1)/lib/modules/$(LINUX_VERSION)
	$(CP) ./modules/mt7628-linux-$(LINUX_VERSION).ko $(1)/lib/modules/$(LINUX_VERSION)/mt7628.ko
	$(CP) ./files/* $(1)/
endef

$(eval $(call BuildPackage,mt7628))
