licenses(["notice"])  # Apache 2.0

exports_files(["LICENSE"])

py_library(
    name = "app",
    srcs = ["app.py"],
    srcs_version = "PY2AND3",
    visibility = ["//visibility:public"],
    deps = [
        ":command_name",
        "//absl/flags",
        "//absl/logging",
    ],
)

py_library(
    name = "command_name",
    srcs = ["command_name.py"],
    srcs_version = "PY2AND3",
    visibility = ["//visibility:public"],
)

py_library(
    name = "_enum_module",
    srcs = ["_enum_module.py"],
    visibility = ["//absl:__subpackages__"],
    deps = [
        "@enum34_archive//:enum",
        "@six_archive//:six",
    ],
)

py_library(
    name = "tests/app_test_helper",
    testonly = 1,
    srcs = ["tests/app_test_helper.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":app",
        "//absl/flags",
    ],
)

py_binary(
    name = "tests/app_test_helper_pure_python",
    testonly = 1,
    srcs = ["tests/app_test_helper.py"],
    main = "tests/app_test_helper.py",
    srcs_version = "PY2AND3",
    deps = [
        ":app",
        "//absl/flags",
    ],
)

py_test(
    name = "tests/app_test",
    srcs = ["tests/app_test.py"],
    data = [":tests/app_test_helper_pure_python"],
    srcs_version = "PY2AND3",
    deps = [
        ":app",
        ":tests/app_test_helper",
        "//absl/flags",
        "//absl/testing:_bazelize_command",
        "//absl/testing:absltest",
        "//absl/testing:flagsaver",
        "@mock_archive//:mock",
        "@six_archive//:six",
    ],
)

py_test(
    name = "tests/command_name_test",
    srcs = ["tests/command_name_test.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":command_name",
        "//absl/testing:absltest",
        "@mock_archive//:mock",
    ],
)
