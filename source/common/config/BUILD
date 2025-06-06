load(
    "//bazel:envoy_build_system.bzl",
    "envoy_cc_library",
    "envoy_package",
)

licenses(["notice"])  # Apache 2

envoy_package()

envoy_cc_library(
    name = "api_version_lib",
    hdrs = ["api_version.h"],
)

envoy_cc_library(
    name = "config_provider_lib",
    srcs = ["config_provider_impl.cc"],
    hdrs = ["config_provider_impl.h"],
    deps = [
        ":utility_lib",
        "//envoy/config:config_provider_interface",
        "//envoy/config:config_provider_manager_interface",
        "//envoy/init:manager_interface",
        "//envoy/server:admin_interface",
        "//envoy/server:config_tracker_interface",
        "//envoy/singleton:instance_interface",
        "//envoy/thread_local:thread_local_interface",
        "//source/common/init:manager_lib",
        "//source/common/init:target_lib",
        "//source/common/init:watcher_lib",
        "//source/common/protobuf",
    ],
)

envoy_cc_library(
    name = "context_provider_lib",
    hdrs = ["context_provider_impl.h"],
    deps = [
        ":xds_context_params_lib",
        "//envoy/config:context_provider_interface",
        "//source/common/common:callback_impl_lib",
        "//source/common/common:thread_lib",
    ],
)

envoy_cc_library(
    name = "datasource_lib",
    srcs = ["datasource.cc"],
    hdrs = ["datasource.h"],
    deps = [
        ":remote_data_fetcher_lib",
        ":utility_lib",
        "//envoy/api:api_interface",
        "//envoy/init:manager_interface",
        "//envoy/thread_local:thread_local_interface",
        "//envoy/upstream:cluster_manager_interface",
        "//source/common/common:backoff_lib",
        "//source/common/common:empty_string",
        "//source/common/init:target_lib",
        "//source/common/protobuf:utility_lib",
        "@envoy_api//envoy/config/core/v3:pkg_cc_proto",
    ],
)

envoy_cc_library(
    name = "decoded_resource_lib",
    hdrs = ["decoded_resource_impl.h"],
    deps = [
        "//envoy/config:subscription_interface",
        "//source/common/protobuf:utility_lib",
        "@com_github_cncf_xds//xds/core/v3:pkg_cc_proto",
        "@envoy_api//envoy/service/discovery/v3:pkg_cc_proto",
    ],
)

envoy_cc_library(
    name = "ttl_lib",
    srcs = ["ttl.cc"],
    hdrs = ["ttl.h"],
    deps = [
        "//envoy/config:subscription_interface",
        "//envoy/event:dispatcher_interface",
        "//envoy/event:timer_interface",
        "@com_google_absl//absl/container:btree",
    ],
)

envoy_cc_library(
    name = "null_grpc_mux_lib",
    hdrs = ["null_grpc_mux_impl.h"],
    deps = [
        "//envoy/config:grpc_mux_interface",
    ],
)

envoy_cc_library(
    name = "metadata_lib",
    srcs = ["metadata.cc"],
    hdrs = ["metadata.h"],
    deps = [
        "//envoy/config:typed_metadata_interface",
        "//envoy/event:dispatcher_interface",
        "//envoy/registry",
        "//envoy/singleton:manager_interface",
        "//source/common/common:assert_lib",
        "//source/common/protobuf",
        "//source/common/protobuf:utility_lib",
        "//source/common/shared_pool:shared_pool_lib",
        "@envoy_api//envoy/config/core/v3:pkg_cc_proto",
        "@envoy_api//envoy/type/metadata/v3:pkg_cc_proto",
    ],
)

envoy_cc_library(
    name = "opaque_resource_decoder_lib",
    hdrs = ["opaque_resource_decoder_impl.h"],
    deps = [
        "//envoy/config:subscription_interface",
        "//source/common/protobuf:utility_lib",
    ],
)

envoy_cc_library(
    name = "protobuf_link_hacks",
    hdrs = ["protobuf_link_hacks.h"],
    deps = [
        "@envoy_api//envoy/service/cluster/v3:pkg_cc_proto",
        "@envoy_api//envoy/service/discovery/v3:pkg_cc_proto",
        "@envoy_api//envoy/service/endpoint/v3:pkg_cc_proto",
        "@envoy_api//envoy/service/extension/v3:pkg_cc_proto",
        "@envoy_api//envoy/service/health/v3:pkg_cc_proto",
        "@envoy_api//envoy/service/listener/v3:pkg_cc_proto",
        "@envoy_api//envoy/service/ratelimit/v3:pkg_cc_proto",
        "@envoy_api//envoy/service/route/v3:pkg_cc_proto",
        "@envoy_api//envoy/service/runtime/v3:pkg_cc_proto",
        "@envoy_api//envoy/service/secret/v3:pkg_cc_proto",
    ],
)

envoy_cc_library(
    name = "remote_data_fetcher_lib",
    srcs = ["remote_data_fetcher.cc"],
    hdrs = ["remote_data_fetcher.h"],
    deps = [
        "//envoy/upstream:cluster_manager_interface",
        "//source/common/common:hex_lib",
        "//source/common/crypto:utility_lib",
        "//source/common/http:utility_lib",
        "@envoy_api//envoy/config/core/v3:pkg_cc_proto",
    ],
)

envoy_cc_library(
    name = "resource_name_lib",
    hdrs = ["resource_name.h"],
    deps = [
        "//source/common/common:assert_lib",
        "//source/common/protobuf",
    ],
)

envoy_cc_library(
    name = "runtime_utility_lib",
    srcs = ["runtime_utility.cc"],
    hdrs = ["runtime_utility.h"],
    deps = ["@envoy_api//envoy/config/bootstrap/v3:pkg_cc_proto"],
)

envoy_cc_library(
    name = "subscription_factory_lib",
    srcs = ["subscription_factory_impl.cc"],
    hdrs = ["subscription_factory_impl.h"],
    deps = [
        ":custom_config_validators_lib",
        ":type_to_endpoint_lib",
        ":utility_lib",
        ":xds_resource_lib",
        "//envoy/config:subscription_factory_interface",
        "//envoy/config:subscription_interface",
        "//envoy/config:xds_config_tracker_interface",
        "//envoy/config:xds_resources_delegate_interface",
        "//envoy/server:instance_interface",
        "//envoy/upstream:cluster_manager_interface",
        "//source/common/common:minimal_logger_lib",
        "//source/common/http:utility_lib",
        "//source/common/protobuf",
        "@envoy_api//envoy/config/core/v3:pkg_cc_proto",
    ],
)

envoy_cc_library(
    name = "type_to_endpoint_lib",
    srcs = ["type_to_endpoint.cc"],
    hdrs = ["type_to_endpoint.h"],
    deps = [
        "//source/common/grpc:common_lib",
        "//source/common/protobuf",
        "@envoy_api//envoy/annotations:pkg_cc_proto",
        "@envoy_api//envoy/config/core/v3:pkg_cc_proto",
    ],
)

envoy_cc_library(
    name = "xds_resource_lib",
    srcs = ["xds_resource.cc"],
    hdrs = ["xds_resource.h"],
    deps = [
        "//source/common/http:utility_lib",
        "//source/common/runtime:runtime_features_lib",
        "@com_github_cncf_xds//xds/core/v3:pkg_cc_proto",
    ],
)

envoy_cc_library(
    name = "utility_lib",
    srcs = ["utility.cc"],
    hdrs = ["utility.h"],
    deps = [
        "//envoy/config:grpc_mux_interface",
        "//envoy/config:subscription_interface",
        "//envoy/local_info:local_info_interface",
        "//envoy/registry",
        "//envoy/server:filter_config_interface",
        "//envoy/upstream:cluster_manager_interface",
        "//source/common/common:assert_lib",
        "//source/common/common:backoff_lib",
        "//source/common/common:hash_lib",
        "//source/common/common:hex_lib",
        "//source/common/protobuf",
        "//source/common/protobuf:utility_lib",
        "//source/common/runtime:runtime_features_lib",
        "//source/common/singleton:const_singleton",
        "//source/common/version:api_version_lib",
        "@com_github_cncf_xds//udpa/type/v1:pkg_cc_proto",
        "@com_github_cncf_xds//xds/type/v3:pkg_cc_proto",
        "@com_google_absl//absl/types:optional",
        "@envoy_api//envoy/config/bootstrap/v3:pkg_cc_proto",
        "@envoy_api//envoy/config/cluster/v3:pkg_cc_proto",
        "@envoy_api//envoy/config/core/v3:pkg_cc_proto",
        "@envoy_api//envoy/config/endpoint/v3:pkg_cc_proto",
    ],
)

envoy_cc_library(
    name = "subscription_base_interface",
    hdrs = ["subscription_base.h"],
    deps = [
        ":opaque_resource_decoder_lib",
        ":resource_name_lib",
        "//envoy/config:subscription_interface",
    ],
)

envoy_cc_library(
    name = "custom_config_validators_lib",
    srcs = ["custom_config_validators_impl.cc"],
    hdrs = ["custom_config_validators_impl.h"],
    deps = [
        ":opaque_resource_decoder_lib",
        ":resource_name_lib",
        "//envoy/config:config_validator_interface",
        "//envoy/config:custom_config_validators_interface",
        "//envoy/server:instance_interface",
        "//source/common/config:utility_lib",
    ],
)

envoy_cc_library(
    name = "watched_directory_lib",
    srcs = ["watched_directory.cc"],
    hdrs = ["watched_directory.h"],
    deps = [
        "//envoy/event:dispatcher_interface",
        "//envoy/filesystem:watcher_interface",
        "@envoy_api//envoy/config/core/v3:pkg_cc_proto",
    ],
)

envoy_cc_library(
    name = "xds_context_params_lib",
    srcs = ["xds_context_params.cc"],
    hdrs = ["xds_context_params.h"],
    deps = [
        "//source/common/common:macros",
        "//source/common/protobuf:utility_lib",
        "@com_github_cncf_xds//xds/core/v3:pkg_cc_proto",
        "@envoy_api//envoy/config/core/v3:pkg_cc_proto",
    ],
)

envoy_cc_library(
    name = "well_known_names",
    srcs = ["well_known_names.cc"],
    hdrs = ["well_known_names.h"],
    deps = [
        "//source/common/common:assert_lib",
        "//source/common/common:regex_lib",
        "//source/common/singleton:const_singleton",
    ],
)

envoy_cc_library(
    name = "xds_manager_lib",
    srcs = ["xds_manager_impl.cc"],
    hdrs = ["xds_manager_impl.h"],
    deps = [
        ":null_grpc_mux_lib",
        ":subscription_factory_lib",
        ":utility_lib",
        "//envoy/config:xds_manager_interface",
        "//envoy/upstream:cluster_manager_interface",
        "//source/common/common:thread_lib",
        "@envoy_api//envoy/config/core/v3:pkg_cc_proto",
    ],
)
