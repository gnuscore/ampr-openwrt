include $(TOPDIR)/rules.mk

PKG_NAME:=amprd
PKG_VERSION:=2.1
PKG_RELEASE:=1
PKG_SOURCE_URL:=http://www.yo2loj.ro/hamprojects
PKG_MD5SUM:=a7afe52dc8cc32727b3340b4cfe0b2a1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tgz
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)    
	SECTION:=net
	CATEGORY:=Network
	SUBMENU:=Routing and Redirection
	TITLE:=IPIP encapsulation daemon for the AMPR network
	MAINTAINER:=Bill Hill <bugs@wbh.org>
endef

define Package/$(PKG_NAME)/description
	A user-space IPIP encapsulation daemon with automatic RIPv2 multicast processing and multiple tunnel support for the ampr network.
endef

CONFIGURE_VARS+= \
	CC="$(TOOLCHAIN_DIR)/bin/$(TARGET_CC)"

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(CP) $(PKG_BUILD_DIR)/$(PKG_NAME) $(1)/usr/sbin
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
