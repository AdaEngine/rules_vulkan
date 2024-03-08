# See https://github.com/bazelbuild/bazel/blob/master/src/conditions/BUILD for standard conditions.
# Unfortunately, there is no one for android at the moment.
# Linux is the default platform.

config_setting(
    name = "android",
    values = {
        # same as that of mediapipe
        "crosstool_top": "//external:android/crosstool",
    },
    visibility = ["//visibility:public"],
)

config_setting(
    name = "windows",
    constraint_values = ["@platforms//os:windows"],
    visibility = ["//visibility:public"],
)

filegroup(
    name = "readme_file",
    srcs = [
        "README.md",
    ],
    visibility = ["//visibility:public"],
)
