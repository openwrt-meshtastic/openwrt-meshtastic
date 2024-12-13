# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python-pexpect
PKG_VERSION:=4.9.0
PKG_RELEASE:=1

PYPI_NAME:=pexpect
PKG_HASH:=ee7d41123f3c9911050ea2c2dac107568dc43b2d3b0c7557a33212c398ead30f

PKG_MAINTAINER:=Austin Lane <vidplace7@gmail.com>
PKG_LICENSE:=ISC
PKG_LICENSE_FILES:=LICENSE

include $(TOPDIR)/feeds/packages/lang/python/pypi.mk
include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

define Package/python3-pexpect
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=Allows easy control of interactive console applications.
  URL:=https://pypi.org/project/pexpect
  DEPENDS:=+python3-light +python3-asyncio +python3-readline
endef

define Package/python3-pexpect/description
Pexpect is a pure Python module for spawning child applications;
controlling them; and responding to expected patterns in their output.
endef

$(eval $(call Py3Package,python3-pexpect))
$(eval $(call BuildPackage,python3-pexpect))
