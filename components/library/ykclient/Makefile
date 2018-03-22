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

COMPONENT_NAME=		ykclient
COMPONENT_VERSION=	2.15
COMPONENT_SUMMARY=	YubiKey C Client library
COMPONENT_PROJECT_URL=	https://developers.yubico.com/yubico-c-client/
COMPONENT_SRC=		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH= \
    sha256:f461cdefe7955d58bbd09d0eb7a15b36cb3576b88adbd68008f40ea978ea5016
COMPONENT_ARCHIVE_URL=	https://developers.yubico.com/yubico-c-client/Releases/$(COMPONENT_ARCHIVE)
COMPONENT_FMRI=		library/security/ykclient
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
REQUIRED_PACKAGES += web/curl
