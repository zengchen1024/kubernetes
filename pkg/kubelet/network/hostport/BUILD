package(default_visibility = ["//visibility:public"])

licenses(["notice"])

load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_library",
    "go_test",
)

go_library(
    name = "go_default_library",
    srcs = [
        "fake_iptables.go",
        "hostport.go",
        "hostport_manager.go",
        "hostport_syncer.go",
    ],
    tags = ["automanaged"],
    deps = [
        "//pkg/proxy/iptables:go_default_library",
        "//pkg/util/dbus:go_default_library",
        "//pkg/util/exec:go_default_library",
        "//pkg/util/iptables:go_default_library",
        "//vendor/github.com/golang/glog:go_default_library",
        "//vendor/k8s.io/api/core/v1:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/util/errors:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = [
        "hostport_manager_test.go",
        "hostport_syncer_test.go",
        "hostport_test.go",
    ],
    library = ":go_default_library",
    tags = ["automanaged"],
    deps = [
        "//pkg/util/iptables:go_default_library",
        "//vendor/github.com/stretchr/testify/assert:go_default_library",
        "//vendor/k8s.io/api/core/v1:go_default_library",
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
    srcs = [
        ":package-srcs",
        "//pkg/kubelet/network/hostport/testing:all-srcs",
    ],
    tags = ["automanaged"],
)
