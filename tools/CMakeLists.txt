#
# Copyright (C) 2016 Search Solution Corporation. All rights reserved.
#
#   This program is free software; you can redistribute it and/or modify
#   it under the terms of the GNU General Public License as published by
#   the Free Software Foundation; either version 2 of the License, or
#   (at your option) any later version.
#
#  This program is distributed in the hope that it will be useful,
#  but WITHOUT ANY WARRANTY; without even the implied warranty of
#  MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
#  GNU General Public License for more details.
#
#  You should have received a copy of the GNU General Public License
#  along with this program; if not, write to the Free Software
#  Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston, MA 02110-1301 USA
#

if(UNIX)
  set(CCI_APPLIER_SOURCES
    ${TOOLS_DIR}/cci_applier.c
    ${BASE_DIR}/cubrid_getopt_long.c
    )
  SET_SOURCE_FILES_PROPERTIES(
    ${CCI_APPLIER_SOURCES}
    PROPERTIES LANGUAGE CXX
    )
  add_executable(cci_applier ${CCI_APPLIER_SOURCES})
  target_link_libraries(cci_applier cascci)

  install(TARGETS cci_applier
    RUNTIME DESTINATION ${CUBRID_BINDIR} COMPONENT Application)
endif(UNIX)
