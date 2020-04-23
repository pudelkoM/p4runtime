load("@rules_proto//proto:defs.bzl", "proto_library")
load("@com_github_grpc_grpc//bazel:python_rules.bzl", "py_grpc_library", "py_proto_library")
load("@com_github_grpc_grpc//bazel:cc_grpc_library.bzl", "cc_grpc_library")

package(default_visibility = ["//visibility:public"])

# p4types rules
proto_library(
    name = "p4types_proto",
    srcs = ["p4types.proto"],
)

py_proto_library(
    name = "p4types_py_proto",
    deps = [":p4types_proto"],
)

cc_proto_library(
    name = "p4types_cc_proto",
    deps = [":p4types_proto"],
)

# p4info rules
proto_library(
    name = "p4info_proto",
    srcs = ["p4info.proto"],
    deps = [
        ":p4types_proto",
        "@com_google_protobuf//:descriptor_proto",
        "@com_google_protobuf//:any_proto",
    ],
)

py_proto_library(
    name = "p4info_py_proto",
    deps = [":p4info_proto"],
)

cc_proto_library(
    name = "p4info_cc_proto",
    deps = [":p4info_proto"],
)
