# SPDX-License-Identifier: GPL-2.0-only
#
# Copyright (C) 2025 YourName

include $(TOPDIR)/rules.mk

PKG_NAME:=dns2socks-rust
PKG_VERSION:=0.2.0
PKG_RELEASE:=1

include $(INCLUDE_DIR)/package.mk

define Package/dns2socks-rust
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=IP Addresses and Names
  TITLE:=DNS forwards to SOCKS5 server
  URL:=https://github.com/tun2proxy/dns2socks
endef

define Package/dns2socks-rust/description
  This is a DNS server that forwards DNS requests to a SOCKS5 server.
  Prebuilt binary packaged for OpenWrt.
endef

# 这里不需要 Build/Prepare / Build/Compile
define Build/Prepare
endef
define Build/Compile
endef

# 根据架构选择对应二进制
define Package/dns2socks-rust/install
	$(INSTALL_DIR) $(1)/usr/bin
ifeq ($(ARCH),x86_64)
	$(INSTALL_BIN) ./files/prebuilt/x86_64/dns2socks $(1)/usr/bin/dns2socks-rust
endif
ifeq ($(ARCH),aarch64)
	$(INSTALL_BIN) ./files/prebuilt/aarch64/dns2socks $(1)/usr/bin/dns2socks-rust
endif
endef

$(eval $(call BuildPackage,dns2socks-rust))
