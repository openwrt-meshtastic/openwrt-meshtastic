include $(TOPDIR)/rules.mk

PKG_NAME:=meshtasticd
PKG_VERSION:=2.5.14.f2ee0df
PKG_RELEASE:=1

PKG_BUILD_DIR:=$(BUILD_DIR)/meshtasticd-$(PKG_VERSION)
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/meshtastic/firmware.git
PKG_SOURCE_VERSION:=v$(PKG_VERSION)
PKG_BUILD_DEPENDS:= \
  python-platformio/host \
  python-pip/host \
  !USE_GLIBC:argp-standalone \
  libgpiod \
  libyaml-cpp \
  zlib \
  bluez

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/nls.mk

define Package/meshtasticd
  SECTION:=meshtastic
  CATEGORY:=Meshtastic
  TITLE:=Meshtastic Daemon
  URL:=http://github.com/meshtastic/firmware
  DEPENDS:=+libgpiod +libyaml-cpp +zlib +bluez-libs $(INTL_DEPENDS)
endef

define Package/meshtasticd/description
  Meshtastic Daemon
endef

PLATFORMIO_BUILD_FLAGS = \
  -std=c++17 \
  $(if $(INTL_FULL),-lintl) \
  $(if $(CONFIG_USE_GLIBC),,-largp)

PLATFORMIO_CFLAGS = \
  $(TARGET_CFLAGS) \
  -I$(STAGING_DIR)/usr/include

PLATFORMIO_CXXFLAGS = \
  $(TARGET_CXXFLAGS) \
  -std=c++17 \
  -I$(STAGING_DIR)/usr/include

PLATFORMIO_LDFLAGS = \
  $(TARGET_LDFLAGS) \
  -L$(STAGING_DIR)/usr/lib

define Build/Prepare
endef

define Build/Configure
endef

define Build/Compile
  TARGET_AR="$(TARGET_AR)" \
  TARGET_AS="$(TARGET_CC) -c $(TARGET_ASFLAGS)" \
  TARGET_CC="$(TARGET_CC)" \
  TARGET_CXX="$(TARGET_CXX)" \
  TARGET_LDFLAGS="$(PLATFORMIO_LDFLAGS)" \
  TARGET_CFLAGS="$(PLATFORMIO_CFLAGS)" \
  TARGET_CXXFLAGS="$(PLATFORMIO_CXXFLAGS)" \
  TARGET_LD="$(TARGET_LD)" \
  TARGET_OBJCOPY="$(TARGET_CROSS)objcopy" \
  TARGET_RANLIB="$(TARGET_RANLIB)" \
  PLATFORMIO_BUILD_FLAGS="$(PLATFORMIO_BUILD_FLAGS)" \
  PLATFORMIO_CACHE_DIR="$(DL_DIR)/.platformio_cache" \
  PLATFORMIO_BUILD_CACHE_DIR="$(BUILD_DIR)/.platformio_build_cache" \
  $(HOST_PYTHON3_BIN) -m platformio run --environment native --project-dir $(PKG_BUILD_DIR)
endef

define Package/meshtasticd/install
  $(INSTALL_DIR) $(1)/usr/sbin
  $(INSTALL_BIN) $(PKG_BUILD_DIR)/.pio/build/native/program $(1)/usr/sbin/meshtasticd
endef

$(eval $(call BuildPackage,meshtasticd))
