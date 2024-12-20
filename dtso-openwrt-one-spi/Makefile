include $(TOPDIR)/rules.mk

PKG_NAME:=dtso-openwrt-one-spi
PKG_RELEASE:=1

include $(INCLUDE_DIR)/package.mk

define Package/dtso-openwrt-one-spi
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=SPI Device Tree Overlay for OpenWRT One Mikrobus
endef

define Build/Compile
endef

define Package/dtso-openwrt-one-spi/install
	$(INSTALL_DIR) $(1)/lib/firmware
	$(INSTALL_DATA) ./files/mt7981b-openwrt-one-mikrobus-spi.dtso $(1)/lib/firmware/
endef

$(eval $(call BuildPackage,dtso-openwrt-one-spi))
