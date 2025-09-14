include $(TOPDIR)/rules.mk

PKG_NAME:=autosub
PKG_VERSION:=0.1.0
PKG_RELEASE:=1

PKG_SOURCE_URL:=https://github.com/vx32/autosub/archive/refs/tags/
PKG_SOURCE_URL_FILE:=v$(PKG_VERSION).tar.gz
PKG_SOURCE:=${PKG_NAME}-$(PKG_VERSION).tar.gz
PKG_HASH:=2f652405b2f2a55ce13513ef323a9e8dabf3ba9372654255b142122288559c1f

CMAKE_INSTALL:=1
PKG_BUILD_PARALLEL:=1

PKG_BUILD_DEPENDS:=curl

PKG_LICENSE:=Apache-2.0
PKG_MAINTAINER:=vx32

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/autosub
	SECTION:=utils
	CATEGORY:=Utilities
	TITLE:=Auto subscription
	URL:=https://github.com/vx32/autosub
	DEPENDS:=+libcurl +libstdcpp
endef

define Package/autosub/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/autosub $(1)/usr/bin/autosub
	$(INSTALL_DIR) $(1)/etc/autosub
	$(CP) $(PKG_INSTALL_DIR)/usr/etc/autosub $(1)/etc/
endef

define Package/trojan/conffiles
/etc/autosub/feeds.conf
/etc/autosub/push.conf
/etc/autosub/TrojanGFW160.conf
endef

$(eval $(call BuildPackage,autosub))
