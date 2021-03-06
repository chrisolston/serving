# Description: Tensorflow Serving core test utils.

package(
    default_visibility = [
        "//tensorflow_serving:internal",
    ],
    features = [
        "-layering_check",
        "-parse_headers",
    ],
)

licenses(["notice"])  # Apache 2.0

exports_files(["LICENSE"])

filegroup(
    name = "all_files",
    srcs = glob(
        ["**/*"],
        exclude = [
            "**/METADATA",
            "**/OWNERS",
        ],
    ),
)

# Main program for tests
cc_library(
    name = "test_main",
    testonly = 1,
    srcs = ["test_main.cc"],
    linkopts = ["-lm"],
    deps = [
        "//external:gtest",
        "@org_tensorflow//tensorflow/core:testlib",
    ],
)

cc_library(
    name = "mock_loader",
    testonly = 1,
    hdrs = ["mock_loader.h"],
    deps = [
        "//external:gtest",
        "//tensorflow_serving/core:loader",
        "//tensorflow_serving/util:any_ptr",
        "@org_tensorflow//tensorflow/core:lib",
    ],
)

cc_library(
    name = "fake_loader",
    testonly = 1,
    srcs = ["fake_loader.cc"],
    hdrs = ["fake_loader.h"],
    deps = [
        "//tensorflow_serving/core:loader",
        "//tensorflow_serving/util:any_ptr",
        "@org_tensorflow//tensorflow/core:lib",
    ],
)

cc_library(
    name = "mock_storage_path_target",
    testonly = 1,
    hdrs = ["mock_storage_path_target.h"],
    deps = [
        "//external:gtest",
        "//tensorflow_serving/core:storage_path",
        "//tensorflow_serving/core:target",
        "@org_tensorflow//tensorflow/core:lib",
    ],
)

cc_library(
    name = "source_adapter_test_util",
    testonly = 1,
    hdrs = ["source_adapter_test_util.h"],
    visibility = ["//visibility:public"],
    deps = [
        "//external:gtest",
        "//tensorflow_serving/core:loader",
        "//tensorflow_serving/core:servable_data",
        "//tensorflow_serving/core:servable_id",
        "@org_tensorflow//tensorflow/core:lib",
    ],
)

cc_library(
    name = "availability_test_util",
    testonly = 1,
    srcs = ["availability_test_util.cc"],
    hdrs = ["availability_test_util.h"],
    visibility = ["//visibility:public"],
    deps = [
        "//external:gtest",
        "//tensorflow_serving/core:servable_state_monitor",
        "@org_tensorflow//tensorflow/core:lib",
    ],
)

cc_library(
    name = "manager_test_util",
    testonly = 1,
    srcs = ["manager_test_util.cc"],
    hdrs = ["manager_test_util.h"],
    deps = [
        "//tensorflow_serving/core:aspired_versions_manager",
        "//tensorflow_serving/core:caching_manager",
    ],
)
