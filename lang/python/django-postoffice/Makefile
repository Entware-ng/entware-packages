#
# Copyright (C) 2007-2017 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=django-postoffice
PKG_VERSION:=3.0.3
PKG_RELEASE:=1
PKG_LICENSE:=MIT

PKG_SOURCE:=django-post_office-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/0f/8c/8c7e1d8998741fd195f7df947c509bc31a03d505aca03488c39e59da11f0/
PKG_BUILD_DIR:=$(BUILD_DIR)/django-post_office-$(PKG_VERSION)/
PKG_HASH:=8d691b2e53ba8121d770ce448f05568874cf78a3cf63215918ad49536db5e76a
PKG_BUILD_DEPENDS:=python python-setuptools

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/django-postoffice
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  MAINTAINER:=Gergely Kiss <mail.gery@gmail.com>
  TITLE:=A Django app to monitor and send mail asynchronously, complete with template support.
  URL:=https://github.com/ui/django-postoffice
  DEPENDS:=+python +django +django-jsonfield
endef

define Package/django-postoffice/description
  A Django app to monitor and send mail asynchronously, complete with template support.
endef

define Build/Compile
	$(call Build/Compile/PyMod,,install --prefix=/opt --root=$(PKG_INSTALL_DIR))
endef

define Package/django-postoffice/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
	$(CP) \
	    $(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
	    $(1)$(PYTHON_PKG_DIR)
endef

$(eval $(call BuildPackage,django-postoffice))
