package(
    default_visibility = [
        "//visibility:public",
    ],
)

py_library(
    name = "timer",
    srcs = ["timer.py"],
)

py_test(
    name = "timer_test",
    size = "small",
    srcs = ["timer_test.py"],
    deps = [
        ":timer",
        "@com_google_absl_py//absl/testing:absltest",
    ],
)

cc_library(
    name = "statusor",
    hdrs = [
        "statusor.h",
    ],
    deps = [
        "@org_tensorflow//tensorflow/core:lib",
    ],
)

cc_library(
    name = "status_matchers",
    testonly = True,
    hdrs = ["status_matchers.h"],
    deps = [
        ":statusor",
        "@com_google_googletest//:gtest_main",
        "@org_tensorflow//tensorflow/core:lib",
        "@org_tensorflow//tensorflow/core:test",
    ],
)

cc_test(
    name = "statusor_test",
    size = "small",
    srcs = ["statusor_test.cc"],
    deps = [
        ":status_matchers",
        ":statusor",
        "@com_google_googletest//:gtest_main",
        "@org_tensorflow//tensorflow/core:lib",
        "@org_tensorflow//tensorflow/core:test",
    ],
)

cc_library(
    name = "statusor_clif_converters",
    srcs = ["statusor_clif_converters.cc"],
    hdrs = ["statusor_clif_converters.h"],
    deps = [
        ":statusor",
        "@clif//:cpp_runtime",
        "@local_config_python//:python_headers",
    ],
)

cc_library(
    name = "statusor_examples",
    hdrs = ["statusor_examples.h"],
    deps = [
        ":statusor",
    ],
)
