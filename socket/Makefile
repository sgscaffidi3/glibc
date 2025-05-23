# Copyright (C) 1991-2025 Free Software Foundation, Inc.
# This file is part of the GNU C Library.

# The GNU C Library is free software; you can redistribute it and/or
# modify it under the terms of the GNU Lesser General Public
# License as published by the Free Software Foundation; either
# version 2.1 of the License, or (at your option) any later version.

# The GNU C Library is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
# Lesser General Public License for more details.

# You should have received a copy of the GNU Lesser General Public
# License along with the GNU C Library; if not, see
# <https://www.gnu.org/licenses/>.

#
#	Sub-makefile for socket portion of the library.
#
subdir	:= socket

include ../Makeconfig

headers := \
  bits/sockaddr.h \
  bits/socket.h \
  bits/socket2.h \
  bits/types/struct_osockaddr.h \
  net/if.h \
  sys/socket.h \
  sys/socketvar.h \
  sys/un.h \
  # headers

routines := \
  accept \
  accept4 \
  bind \
  connect \
  getpeername \
  getsockname \
  getsockopt \
  isfdtype \
  listen \
  opensock \
  recv \
  recvfrom \
  recvmmsg \
  recvmsg \
  send \
  sendmmsg \
  sendmsg \
  sendto \
  setsockopt \
  shutdown \
  sockaddr_un_set \
  sockatmark \
  socket \
  socketpair \
  # routines

# Exclude fortified routines from being built with _FORTIFY_SOURCE
routines_no_fortify += \
  recv \
  recvfrom \
  # routines_no_fortify

tests := \
  tst-accept4 \
  tst-cmsg_cloexec \
  tst-cmsghdr \
  tst-connect \
  tst-shutdown \
  tst-sockopt \
  # tests

tests-internal := \
  tst-sockaddr_un_set \
  # tests-internal

tests-time64 := \
  tst-sockopt-time64 \
  # tests

aux	 := sa_len

include ../Rules

CFLAGS-recv.c += -fexceptions -fasynchronous-unwind-tables $(config-cflags-wno-ignored-attributes)
CFLAGS-recvfrom.c += -fexceptions -fasynchronous-unwind-tables
CFLAGS-sendto.c += -fexceptions -fasynchronous-unwind-tables
CFLAGS-recvmsg.c += -fexceptions -fasynchronous-unwind-tables
CFLAGS-sendmsg.c += -fexceptions -fasynchronous-unwind-tables $(config-cflags-wno-ignored-attributes)
CFLAGS-send.c += -fexceptions -fasynchronous-unwind-tables $(config-cflags-wno-ignored-attributes)
CFLAGS-connect.c += -fexceptions -fasynchronous-unwind-tables $(config-cflags-wno-ignored-attributes)
CFLAGS-accept.c += -fexceptions -fasynchronous-unwind-tables $(config-cflags-wno-ignored-attributes)
