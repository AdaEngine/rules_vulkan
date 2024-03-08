load("@rules_cc//cc:defs.bzl", "cc_library")

VULKAN_LINKOPTS = select({
    "@rules_vulkan//:android": [],
    "@rules_vulkan//:windows": [],
    "@platforms//os:macos": [],
    "@platforms//os:ios": [],
    "@platforms//os:tvos": [],
    "@platforms//os:visionos": [],
    "//conditions:default": ["-lvulkan"],
})

VULKAN_LIBRARIES = select(
    {
        "@rules_vulkan//:windows": ["@vulkan_windows//:vulkan_cc_library"],
        "@rules_vulkan//:android": ["@vulkan_android//:vulkan_cc_library"],
        "@platforms//os:macos": ["@vulkan_darwin//:vulkan_cc_library"],
        "@platforms//os:ios": ["@vulkan_darwin//:vulkan_cc_library"],
        "@platforms//os:tvos": ["@vulkan_darwin//:vulkan_cc_library"],
        "@platforms//os:visionos": ["@vulkan_darwin//:vulkan_cc_library"],
        "//conditions:default": ["@vulkan_linux//:vulkan_cc_library"],
    },
    no_match_error = "No configuration matches the supported platforms",
)

cc_library(
    name = "vulkan_cc_library",
    linkopts = VULKAN_LINKOPTS,
    visibility = ["//visibility:public"],
    deps = VULKAN_LIBRARIES,
)
