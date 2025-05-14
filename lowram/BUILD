# Copyright lowRISC contributors (OpenTitan project).
# Licensed under the Apache License, Version 2.0, see LICENSE for details.
# SPDX-License-Identifier: Apache-2.0
package(default_visibility = ["//visibility:public"])

# Headers libraries
cc_library(
    name = "config",
    hdrs = ["config.h"],
)

cc_library(
    name = "params",
    hdrs = ["params.h"],
    deps = [
      ":config",
    ]
)

# C libraries
cc_library(
    name = "fips202",
    srcs = ["fips202.c"],
    copts = [
        "-Wno-error",
        "-Wall",
        "-Wextra",
        "-Wpedantic",
        "-Wmissing-prototypes",
        "-Wredundant-decls",
        "-Wshadow",
        "-Wvla",
        "-Wpointer-arith",
        "-Os",
        "-fomit-frame-pointer",
    ],
    hdrs = ["fips202.h"],
)

cc_library(
    name = "lowram",
    srcs = ["lowram.c"],
    copts = [
        "-Wno-error",
        "-Wall",
        "-Wextra",
        "-Wpedantic",
        "-Wmissing-prototypes",
        "-Wredundant-decls",
        "-Wshadow",
        "-Wvla",
        "-Wpointer-arith",
        "-Os",
        "-fomit-frame-pointer",
    ],
    hdrs = ["lowram.h"],
    deps = [
        ":fips202",
        ":symmetric",
        ":reduce",
        ":rounding",
        ":poly",
        ":smallpoly",
    ],
)

cc_library(
    name = "ntt",
    srcs = ["ntt.c"],
    copts = [
        "-Wno-error",
        "-Wall",
        "-Wextra",
        "-Wpedantic",
        "-Wmissing-prototypes",
        "-Wredundant-decls",
        "-Wshadow",
        "-Wvla",
        "-Wpointer-arith",
        "-Os",
        "-fomit-frame-pointer",
    ],
    hdrs = ["ntt.h"],
    deps = [
        ":params",
        ":reduce",
    ],
)

cc_library(
    name = "packing",
    srcs = ["packing.c"],
    copts = [
        "-Wno-error",
        "-Wall",
        "-Wextra",
        "-Wpedantic",
        "-Wmissing-prototypes",
        "-Wredundant-decls",
        "-Wshadow",
        "-Wvla",
        "-Wpointer-arith",
        "-Os",
        "-fomit-frame-pointer",
    ],
    hdrs = ["packing.h"],
    deps = [
        ":params",
        ":polyvec",
        ":poly",
    ],
)

cc_library(
    name = "poly",
    srcs = ["poly.c"],
    copts = [
        "-Wno-error",
        "-Wall",
        "-Wextra",
        "-Wpedantic",
        "-Wmissing-prototypes",
        "-Wredundant-decls",
        "-Wshadow",
        "-Wvla",
        "-Wpointer-arith",
        "-Os",
        "-fomit-frame-pointer",
    ],
    hdrs = ["poly.h"],
    deps = [
        ":ntt",
        ":reduce",
        ":rounding",
        ":symmetric",
    ],
)

cc_library(
    name = "polyvec",
    srcs = ["polyvec.c"],
    copts = [
        "-Wno-error",
        "-Wall",
        "-Wextra",
        "-Wpedantic",
        "-Wmissing-prototypes",
        "-Wredundant-decls",
        "-Wshadow",
        "-Wvla",
        "-Wpointer-arith",
        "-Os",
        "-fomit-frame-pointer",
    ],
    hdrs = ["polyvec.h"],
    deps = [
        ":poly",
    ],
)

cc_library(
    name = "randombytes",
    srcs = ["randombytes.c"],
    copts = [
        "-Wno-error",
        "-Wall",
        "-Wextra",
        "-Wpedantic",
        "-Wmissing-prototypes",
        "-Wredundant-decls",
        "-Wshadow",
        "-Wvla",
        "-Wpointer-arith",
        "-Os",
        "-fomit-frame-pointer",
    ],
    hdrs = ["randombytes.h"],
)

cc_library(
    name = "reduce",
    srcs = ["reduce.c"],
    copts = [
        "-Wno-error",
        "-Wall",
        "-Wextra",
        "-Wpedantic",
        "-Wmissing-prototypes",
        "-Wredundant-decls",
        "-Wshadow",
        "-Wvla",
        "-Wpointer-arith",
        "-Os",
        "-fomit-frame-pointer",
    ],
    hdrs = ["reduce.h"],
    deps = [
        ":params",
    ],
)

cc_library(
    name = "rounding",
    srcs = ["rounding.c"],
    copts = [
        "-Wno-error",
        "-Wall",
        "-Wextra",
        "-Wpedantic",
        "-Wmissing-prototypes",
        "-Wredundant-decls",
        "-Wshadow",
        "-Wvla",
        "-Wpointer-arith",
        "-Os",
        "-fomit-frame-pointer",
    ],
    hdrs = ["rounding.h"],
    deps = [
        ":params",
    ],
)

cc_library(
    name = "sign",
    srcs = ["sign.c"],
    copts = [
        "-Wno-error",
        "-Wall",
        "-Wextra",
        "-Wpedantic",
        "-Wmissing-prototypes",
        "-Wredundant-decls",
        "-Wshadow",
        "-Wvla",
        "-Wpointer-arith",
        "-Os",
        "-fomit-frame-pointer",
    ],
    hdrs = ["sign.h"],
    deps = [
        ":params",
        ":packing",
        ":polyvec",
        ":poly",
        ":randombytes",
        ":symmetric",
        ":fips202",
        ":smallpoly",
        ":lowram",
        ":smallntt",
    ],
)

cc_library(
    name = "smallntt",
    srcs = ["smallntt_3329.c"],
    copts = [
        "-Wno-error",
        "-Wall",
        "-Wextra",
        "-Wpedantic",
        "-Wmissing-prototypes",
        "-Wredundant-decls",
        "-Wshadow",
        "-Wvla",
        "-Wpointer-arith",
        "-Os",
        "-fomit-frame-pointer",
    ],
    hdrs = ["smallntt.h"],
    deps = [
        ":params",
        ":ntt",
        ":reduce",
        ":poly",
    ],
)

cc_library(
    name = "smallpoly",
    srcs = ["smallpoly.c"],
    copts = [
        "-Wno-error",
        "-Wall",
        "-Wextra",
        "-Wpedantic",
        "-Wmissing-prototypes",
        "-Wredundant-decls",
        "-Wshadow",
        "-Wvla",
        "-Wpointer-arith",
        "-Os",
        "-fomit-frame-pointer",
    ],
    hdrs = ["smallpoly.h"],
    deps = [
        ":smallntt",
        ":poly",
        ":polyvec",
    ],
)

cc_library(
    name = "symmetric",
    srcs = ["symmetric-shake.c"],
    copts = [
        "-Wno-error",
        "-Wall",
        "-Wextra",
        "-Wpedantic",
        "-Wmissing-prototypes",
        "-Wredundant-decls",
        "-Wshadow",
        "-Wvla",
        "-Wpointer-arith",
        "-Os",
        "-fomit-frame-pointer",
    ],
    hdrs = ["symmetric.h"],
    deps = [
        ":params",
        ":fips202",
    ],
)
