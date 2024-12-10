# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=meshtasticd
PKG_VERSION:=2.5.17
PKG_RELEASE:=1
PKG_SOURCE_VERSION:=7dd362950111fbf6ca134b678ec1975d3b6eb1fd

PKG_BUILD_DIR:=$(BUILD_DIR)/meshtasticd-$(PKG_VERSION)
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/meshtastic/firmware.git
PKG_MIRROR_HASH:=skip
PKG_BUILD_DEPENDS:= \
	python3/host \
	python-platformio/host \
	!USE_GLIBC:argp-standalone \
	libusb \
	libgpiod \
	libyaml-cpp \
	zlib \
	bluez \
	openssl \
	liborcania \
	libyder \
	libulfius

PKG_MAINTAINER:=Austin Lane <vidplace7@gmail.com>

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-host.mk
include $(INCLUDE_DIR)/nls.mk

define Package/meshtasticd
  SECTION:=meshtastic
  CATEGORY:=Meshtastic
  TITLE:=Meshtastic Daemon
  URL:=http://github.com/meshtastic/firmware
  DEPENDS:= \
	+kmod-spi-dev +libgpiod +libusb-1.0 +libyaml-cpp +zlib +bluez-libs \
	+libopenssl +liborcania +libyder +libulfius-gnutls \
	$(INTL_DEPENDS)
endef

define Package/meshtasticd/description
  Meshtastic Daemon
endef

PLATFORMIO_BUILD_FLAGS = \
	$(if $(INTL_FULL),-lintl) \
	$(if $(CONFIG_USE_GLIBC),,-largp)

define Build/Compile
	TARGET_AR="$(TARGET_AR)" \
	TARGET_AS="$(TARGET_CC) -c $(TARGET_ASFLAGS)" \
	TARGET_CC="$(TARGET_CC)" \
	TARGET_CXX="$(TARGET_CXX)" \
	TARGET_LDFLAGS="$(TARGET_LDFLAGS)" \
	TARGET_CFLAGS="$(TARGET_CFLAGS)" \
	TARGET_CXXFLAGS="$(TARGET_CXXFLAGS)" \
	TARGET_LD="$(TARGET_LD)" \
	TARGET_OBJCOPY="$(TARGET_CROSS)objcopy" \
	TARGET_RANLIB="$(TARGET_RANLIB)" \
	PLATFORMIO_BUILD_FLAGS="$(PLATFORMIO_BUILD_FLAGS)" \
	PLATFORMIO_CACHE_DIR="$(DL_DIR)/.platformio_cache" \
	PLATFORMIO_BUILD_CACHE_DIR="$(PKG_BUILD_DIR)/.pio_build_cache" \
	$(HOST_PYTHON3_BIN) -m platformio run --environment buildroot --project-dir $(PKG_BUILD_DIR)
endef

define Package/meshtasticd/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/.pio/build/buildroot/program $(1)/usr/sbin/meshtasticd
endef

$(eval $(call BuildPackage,meshtasticd))
