ARCHS = arm64 arm64e
TARGET = iphone:clang:latest:11.0
include $(THEOS)/makefiles/common.mk

TOOL_NAME = shadowd

shadowd_FILES = Shadow.m main.m
# shadowd_LIBRARIES = rocketbootstrap
shadowd_PRIVATE_FRAMEWORKS = AppSupport
shadowd_INSTALL_PATH = /usr/libexec
shadowd_CFLAGS = -fobjc-arc -DROCKETBOOTSTRAP_LOAD_DYNAMIC

include $(THEOS_MAKE_PATH)/tool.mk

after-shadowd-stage::
	$(ECHO_NOTHING)$(FAKEROOT) chown root:wheel $(THEOS_STAGING_DIR)/Library/LaunchDaemons/me.jjolano.shadow.daemon.plist$(ECHO_END)
