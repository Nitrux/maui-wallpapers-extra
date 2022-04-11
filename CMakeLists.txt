# Copyright 2018-2020 Camilo Higuita <milo.h@aol.com>
# Copyright 2018-2020 Nitrux Latinoamericana S.C.
#
# SPDX-License-Identifier: GPL-3.0-or-later

cmake_minimum_required(VERSION 3.16)

set(MAUI_WALLPAPERS_VERSION 1.0.0)

project(maui_wallpapers VERSION ${MAUI_WALLPAPERS_VERSION})

find_package(ECM ${REQUIRED_KF5_VERSION} REQUIRED NO_MODULE)
set(CMAKE_MODULE_PATH "${CMAKE_CURRENT_SOURCE_DIR}/cmake" ${ECM_MODULE_PATH})

if(UNIX AND NOT APPLE AND NOT ANDROID)
    include(KDEInstallDirs)
    include(KDECMakeSettings)
endif()

include(FeatureSummary)

#install(DIRECTORY Wallpapers/ DESTINATION $ENV{HOME}/Pictures/Wallpapers)
install(DIRECTORY Wallpapers/ DESTINATION ${KDE_INSTALL_WALLPAPERDIR}/Cask)

feature_summary(WHAT ALL FATAL_ON_MISSING_REQUIRED_PACKAGES)
