load("//tensorboard/defs:defs.bzl", "tf_ng_module", "tf_ts_library")

package(default_visibility = ["//tensorboard:internal"])

licenses(["notice"])

tf_ng_module(
    name = "data_source",
    srcs = [
        "runs_data_source.ts",
        "runs_data_source_module.ts",
        "runs_data_source_types.ts",
    ],
    deps = [
        ":backend_types",
        "//tensorboard/webapp/webapp_data_source:http_client",
        "@npm//@angular/core",
        "@npm//rxjs",
    ],
)

tf_ts_library(
    name = "backend_types",
    srcs = [
        "runs_backend_types.ts",
    ],
    visibility = ["//visibility:private"],
)

tf_ng_module(
    name = "testing",
    testonly = True,
    srcs = [
        "testing.ts",
    ],
    deps = [
        ":backend_types",
        ":data_source",
        "@npm//@angular/core",
        "@npm//rxjs",
    ],
)

tf_ts_library(
    name = "runs_data_source_test",
    testonly = True,
    srcs = [
        "runs_data_source_test.ts",
    ],
    deps = [
        ":data_source",
        "//tensorboard/webapp/angular:expect_angular_core_testing",
        "//tensorboard/webapp/webapp_data_source:http_client_testing",
        "@npm//@types/jasmine",
    ],
)
