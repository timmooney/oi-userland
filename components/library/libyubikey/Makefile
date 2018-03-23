#
# CDDL HEADER START
#
# The contents of this file are subject to the terms of the
# Common Development and Distribution License (the "License").
# You may not use this file except in compliance with the License.
#
# You can obtain a copy of the license at usr/src/OPENSOLARIS.LICENSE
# or http://www.opensolaris.org/os/licensing.
# See the License for the specific language governing permissions
# and limitations under the License.
#
# When distributing Covered Code, include this CDDL HEADER in each
# file and include the License file at usr/src/OPENSOLARIS.LICENSE.
# If applicable, add the following below this CDDL HEADER, with the
# fields enclosed by brackets "[]" replaced with your own identifying
# information: Portions Copyright [yyyy] [name of copyright owner]
#
# CDDL HEADER END
#
# Copyright 2018 Tim Mooney. All rights reserved.
#
include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=		libyubikey
COMPONENT_VERSION=	1.13
COMPONENT_SUMMARY=	Development kit for the Yubico YubiKey authentication device
COMPONENT_DESCRIPTION=	This package makes up the low-level C software development kit for the Yubico YubiKey authentication device.
COMPONENT_PROJECT_URL=	https://developers.yubico.com/yubico-c/
COMPONENT_SRC=		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH= \
    sha256:04edd0eb09cb665a05d808c58e1985f25bb7c5254d2849f36a0658ffc51c3401
COMPONENT_ARCHIVE_URL=	https://developers.yubico.com/yubico-c/Releases/$(COMPONENT_ARCHIVE)
COMPONENT_FMRI=		library/security/libyubikey
COMPONENT_CLASSIFICATION=	System/Security
COMPONENT_LICENSE=	BSD-2-Clause

include $(WS_MAKE_RULES)/prep.mk
include $(WS_MAKE_RULES)/configure.mk
include $(WS_MAKE_RULES)/ips.mk

COMPONENT_PREP_ACTION = (cd $(@D) && autoreconf -fi)

CONFIGURE_OPTIONS  +=           --disable-static
CONFIGURE_OPTIONS  +=           --enable-shared

build:		$(BUILD_32_and_64)

install:	$(INSTALL_32_and_64)

test:	$(TEST_32_and_64)

REQUIRED_PACKAGES += SUNWcs
REQUIRED_PACKAGES += system/library
