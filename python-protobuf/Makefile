# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python-protobuf
PKG_VERSION:=3.17.3
PKG_RELEASE:=1

PYPI_NAME:=protobuf
PKG_HASH:=72804ea5eaa9c22a090d2803813e280fb273b62d5ae497aaf3553d141c4fdd7b

PKG_MAINTAINER:=Austin Lane <vidplace7@gmail.com>
PKG_LICENSE:=BSD-3-Clause
PKG_LICENSE_FILES:=LICENSE
PKG_CPE_ID:=cpe:/a:google:protobuf

include $(TOPDIR)/feeds/packages/lang/python/pypi.mk
include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

define Package/python3-protobuf
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=Protobuf support for Python
  URL:=https://pypi.org/project/protobuf
  DEPENDS:=+protobuf +python3-light +python3-ctypes
endef

define Package/python3-protobuf/description
Protocol Buffers - Google's data interchange format, for Python
endef

$(eval $(call Py3Package,python3-protobuf))
$(eval $(call BuildPackage,python3-protobuf))
