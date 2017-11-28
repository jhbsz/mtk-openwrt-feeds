include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/version.mk

PKG_NAME:=mt7615
PKG_RELEASE:=1
PKG_BUILD_DEPENDS:=base-files
PKG_FILE_DEPENDS:=
PKG_LICENSE:=GPL-2.0

PKG_MAINTAINER:=Hua Shao <nossiac@163.com>

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/kernel.mk

define Package/mt7615
  CATEGORY:=MTK Properties
  SUBMENU:=Drivers
  TITLE:=MTK MT7615 WiFi AP driver
  AUTOLOAD:=$(call AutoProbe,mt7615)
  MENU:=1
endef

define Package/mt7615/config-todo
	if PACKAGE_mt7615
	source "$(SOURCE)/mt7615-config.in"
	endif
endef

define Package/mt7615/config-notyet
	config MT7615_USING_LUA_SCRIPT
	bool "use lua script to init/config driver"
	depends on PACKAGE_mt7615
	default y
endef

define Build/Compile

endef

define Package/mt7615/install
	$(INSTALL_DIR) $(1)/lib/modules/$(LINUX_VERSION)
	$(CP) ./modules/mt7615-linux-$(LINUX_VERSION).ko $(1)/lib/modules/$(LINUX_VERSION)/mt7615.ko
	$(CP) ./files/* $(1)/
endef

$(eval $(call BuildPackage,mt7615))
