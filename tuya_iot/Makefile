include $(TOPDIR)/rules.mk

PKG_NAME:=tuya_iot
PKG_RELEASE:=1
PKG_VERSION:=1.0.0
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/tuya/tuya-iot-core-sdk
PKG_SOURCE_VERSION:=1ba26efe673d93da8b1e649b875f185ce0cbe09c

CMAKE_BINARY_SUBDIR:=build

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/tuya_iot
	CATEGORY:=Examples
	TITLE:=example-download-git
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/lib $(1)/usr/include
	$(CP) $(PKG_BUILD_DIR)/build/lib/*.so $(1)/usr/lib
	$(CP) $(PKG_BUILD_DIR)/utils/cJSON.h $(1)/usr/include
	$(CP) $(PKG_BUILD_DIR)/examples/subdevice_basic_demo/tuya_cacert.h $(1)/usr/include
	$(CP) $(PKG_BUILD_DIR)/utils/*.h $(1)/usr/include
	$(CP) $(PKG_BUILD_DIR)/interface/system_interface.h $(1)/usr/include
	$(CP) $(PKG_BUILD_DIR)/interface/mqtt_client_interface.h $(1)/usr/include
	$(CP) $(PKG_BUILD_DIR)/include/tuyalink_core.h $(1)/usr/include
endef

define Package/tuya_iot/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/build/lib/libplatform_port.so $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/build/lib/liblink_core.so $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/build/lib/libmiddleware_implementation.so $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/build/lib/libutils_modules.so $(1)/usr/lib
endef


$(eval $(call BuildPackage,tuya_iot))
