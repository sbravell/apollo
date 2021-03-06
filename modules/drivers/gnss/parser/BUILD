load("@rules_cc//cc:defs.bzl", "cc_library")
load("//tools:cpplint.bzl", "cpplint")

package(default_visibility = ["//visibility:public"])

cc_library(
    name = "gnss_parser",
    deps = [
        ":data_parser",
        ":newtonm2_parser",
        ":novatel_parser",
        ":rtcm_parsers",
    ],
)

cc_library(
    name = "data_parser",
    srcs = ["data_parser.cc"],
    hdrs = [
        "data_parser.h",
        "parser.h",
    ],
    copts = ["-Ithird_party/rtklib"],
    deps = [
        ":newtonm2_parser",
        ":novatel_parser",
        "//cyber",
        "//modules/common/adapters:adapter_gflags",
        "//modules/common/util:message_util",
        "//modules/drivers/gnss/proto:gnss_best_pose_cc_proto",
        "//modules/drivers/gnss/proto:gnss_cc_proto",
        "//modules/drivers/gnss/proto:gnss_status_cc_proto",
        "//modules/drivers/gnss/util:gnss_util",
        "//modules/localization/proto:gps_cc_proto",
        "//modules/localization/proto:imu_cc_proto",
        "//modules/transform:transform_broadcaster",
        "@eigen",
        "@proj",
    ],
)

cc_library(
    name = "novatel_parser",
    srcs = ["novatel_parser.cc"],
    hdrs = [
        "novatel_messages.h",
        "parser.h",
        "rtcm_decode.h",
    ],
    copts = ["-Ithird_party/rtklib"],
    deps = [
        "//cyber",
        "//modules/common/adapters:adapter_gflags",
        "//modules/common/proto:error_code_cc_proto",
        "//modules/common/proto:geometry_cc_proto",
        "//modules/common/proto:header_cc_proto",
        "//modules/drivers/gnss/proto:config_cc_proto",
        "//modules/drivers/gnss/proto:gnss_best_pose_cc_proto",
        "//modules/drivers/gnss/proto:gnss_cc_proto",
        "//modules/drivers/gnss/proto:gnss_raw_observation_cc_proto",
        "//modules/drivers/gnss/proto:heading_cc_proto",
        "//modules/drivers/gnss/proto:imu_cc_proto",
        "//modules/drivers/gnss/proto:ins_cc_proto",
        "//modules/drivers/gnss/util:gnss_util",
        "//third_party/rtklib",
    ],
)

cc_library(
    name = "newtonm2_parser",
    srcs = ["newtonm2_parser.cc"],
    hdrs = [
        "newtonm2_parser.h",
        "novatel_messages.h",
        "parser.h",
        "rtcm_decode.h",
    ],
    copts = ["-Ithird_party/rtklib"],
    deps = [
        "//cyber",
        "//modules/common/monitor_log",
        "//modules/drivers/gnss/proto:config_cc_proto",
        "//modules/drivers/gnss/proto:gnss_best_pose_cc_proto",
        "//modules/drivers/gnss/proto:gnss_cc_proto",
        "//modules/drivers/gnss/proto:gnss_raw_observation_cc_proto",
        "//modules/drivers/gnss/proto:heading_cc_proto",
        "//modules/drivers/gnss/proto:imu_cc_proto",
        "//modules/drivers/gnss/proto:ins_cc_proto",
        "//modules/drivers/gnss/util:gnss_util",
        "//third_party/rtklib",
        "@com_github_gflags_gflags//:gflags",
    ],
)

cc_library(
    name = "rtcm_parsers",
    srcs = [
        "rtcm3_parser.cc",
        "rtcm_parser.cc",
    ],
    hdrs = [
        "parser.h",
        "rtcm3_parser.h",
        "rtcm_decode.h",
        "rtcm_parser.h",
    ],
    copts = ["-Ithird_party/rtklib"],
    deps = [
        "//cyber",
        "//modules/common/adapters:adapter_gflags",
        "//modules/drivers/gnss/proto:config_cc_proto",
        "//modules/drivers/gnss/proto:gnss_raw_observation_cc_proto",
        "//modules/drivers/gnss/util:gnss_util",
        "//third_party/rtklib",
    ],
)

cpplint()
