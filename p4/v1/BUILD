load("@rules_proto//proto:defs.bzl", "proto_library")
load("@com_github_grpc_grpc//bazel:python_rules.bzl", "py_grpc_library", "py_proto_library")
load("@com_github_grpc_grpc//bazel:cc_grpc_library.bzl", "cc_grpc_library")

package(default_visibility = ["//visibility:public"])

# p4data rules
proto_library(
    name = "p4data_proto",
    srcs = ["p4data.proto"],
)

py_proto_library(
    name = "p4data_py_proto",
    deps = [":p4data_proto"],
)

py_grpc_library(
    name = "p4data_py_grpc",
    srcs = [":p4data_proto"],
    deps = [":p4data_py_proto"],
)

cc_proto_library(
    name = "p4data_cc_proto",
    deps = [":p4data_proto"],
)

#p4runtime rules
proto_library(
    name = "p4runtime_proto",
    srcs = ["p4runtime.proto"],
    deps = [
        ":p4data_proto",
        "//p4/config/v1:p4info_proto",
        "@com_google_protobuf//:any_proto",
        "@com_google_googleapis//google/rpc:status_proto"
    ],
)

py_proto_library(
    name = "p4runtime_py_proto",
    deps = [":p4runtime_proto"],
)

py_grpc_library(
    name = "p4runtime_py_grpc",
    srcs = [":p4runtime_proto"],
    deps = [":p4runtime_py_proto"],
)

cc_proto_library(
    name = "p4runtime_cc_proto",
    deps = [":p4runtime_proto"],
)

cc_grpc_library(
    name = "p4runtime_cc_grpc",
    srcs = [":p4runtime_proto"],
    deps = [":p4runtime_cc_proto"],
    grpc_only = True,
)
