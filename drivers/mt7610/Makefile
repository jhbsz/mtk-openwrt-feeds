include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/version.mk

PKG_NAME:=mt7610
PKG_RELEASE:=1
PKG_BUILD_DEPENDS:=base-files
PKG_FILE_DEPENDS:=
PKG_LICENSE:=GPL-2.0

PKG_MAINTAINER:=Hua Shao <nossiac@163.com>

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/kernel.mk

define Package/mt7610
  CATEGORY:=MTK Properties
  SUBMENU:=Drivers
  TITLE:=MTK MT7610 WiFi AP driver
  AUTOLOAD:=$(call AutoProbe,mt7610)
endef


define Package/mt7610/config-notyet
	config MT7610_USING_LUA_SCRIPT
	bool "use lua script to init/config driver"
	depends on PACKAGE_mt7610
	default y
endef

define Build/Compile

endef

define Package/mt7610/install
	$(INSTALL_DIR) $(1)/lib/modules/$(LINUX_VERSION)
	$(CP) ./modules/mt7610-linux-$(LINUX_VERSION).ko $(1)/lib/modules/$(LINUX_VERSION)/mt7610.ko
	$(CP) ./files/* $(1)/
endef

$(eval $(call BuildPackage,mt7610))
