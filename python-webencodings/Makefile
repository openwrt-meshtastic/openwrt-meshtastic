# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python-webencodings
PKG_VERSION:=0.5.1
PKG_RELEASE:=1

PYPI_NAME:=webencodings
PKG_HASH:=b36a1c245f2d304965eb4e0a82848379241dc04b865afcc4aab16748587e1923

PKG_MAINTAINER:=Austin Lane <vidplace7@gmail.com>
PKG_LICENSE:=BSD-3-Clause

include $(TOPDIR)/feeds/packages/lang/python/pypi.mk
include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

define Package/python3-webencodings
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=WHATWG Encoding for Python
  URL:=https://pypi.org/project/webencodings
  DEPENDS:=+python3-light +python3-urllib
endef

define Package/python3-webencodings/description
A Python implementation of the WHATWG Encoding standard.
endef

$(eval $(call Py3Package,python3-webencodings))
$(eval $(call BuildPackage,python3-webencodings))
