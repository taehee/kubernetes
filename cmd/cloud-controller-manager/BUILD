package(default_visibility = ["//visibility:public"])

load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_binary",
    "go_library",
)
load("//staging/src/k8s.io/component-base/version:def.bzl", "version_x_defs")

go_binary(
    name = "cloud-controller-manager",
    embed = [":go_default_library"],
    pure = "on",
    x_defs = version_x_defs(),
)

go_library(
    name = "go_default_library",
    srcs = [
        "controller-manager.go",
        "providers.go",
    ],
    importpath = "k8s.io/kubernetes/cmd/cloud-controller-manager",
    deps = [
        "//staging/src/k8s.io/cloud-provider/app:go_default_library",
        "//staging/src/k8s.io/component-base/logs:go_default_library",
        "//staging/src/k8s.io/component-base/metrics/prometheus/clientgo:go_default_library",
        "//staging/src/k8s.io/component-base/metrics/prometheus/version:go_default_library",
        "//staging/src/k8s.io/legacy-cloud-providers/aws:go_default_library",
        "//staging/src/k8s.io/legacy-cloud-providers/azure:go_default_library",
        "//staging/src/k8s.io/legacy-cloud-providers/gce:go_default_library",
        "//staging/src/k8s.io/legacy-cloud-providers/openstack:go_default_library",
        "//staging/src/k8s.io/legacy-cloud-providers/vsphere:go_default_library",
    ],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [":package-srcs"],
    tags = ["automanaged"],
)
