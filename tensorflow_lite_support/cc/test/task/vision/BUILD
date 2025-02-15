load(
    "@org_tensorflow//tensorflow/lite/core/shims:cc_library_with_tflite.bzl",
    "cc_test_with_tflite",
)

package(
    default_visibility = [
        "//tensorflow_lite_support:users",
    ],
    licenses = ["notice"],  # Apache 2.0
)

cc_test_with_tflite(
    name = "image_classifier_test",
    srcs = ["image_classifier_test.cc"],
    data = [
        "//tensorflow_lite_support/cc/test/testdata/task/vision:test_images",
        "//tensorflow_lite_support/cc/test/testdata/task/vision:test_models",
    ],
    tflite_deps = [
        "@org_tensorflow//tensorflow/lite/core/shims:cc_shims_test_util",
        "//tensorflow_lite_support/cc/task/core:task_api_factory",
        "//tensorflow_lite_support/cc/task/core:tflite_engine",
        "//tensorflow_lite_support/cc/task/vision:image_classifier",
    ],
    deps = [
        "//tensorflow_lite_support/cc:common",
        "//tensorflow_lite_support/cc/port:gtest_main",
        "//tensorflow_lite_support/cc/port:status_macros",
        "//tensorflow_lite_support/cc/task/core:task_utils",
        "//tensorflow_lite_support/cc/task/vision/core:frame_buffer",
        "//tensorflow_lite_support/cc/task/vision/proto:bounding_box_proto_inc",
        "//tensorflow_lite_support/cc/task/vision/proto:classifications_proto_inc",
        "//tensorflow_lite_support/cc/task/vision/proto:image_classifier_options_proto_inc",
        "//tensorflow_lite_support/cc/task/vision/utils:frame_buffer_common_utils",
        "//tensorflow_lite_support/cc/task/vision/utils:frame_buffer_utils",
        "//tensorflow_lite_support/cc/test:test_utils",
        "//tensorflow_lite_support/examples/task/vision/desktop/utils:image_utils",
        "@com_google_absl//absl/flags:flag",
        "@com_google_absl//absl/status",
        "@com_google_absl//absl/strings:cord",
        "@org_tensorflow//tensorflow/lite:framework",
        "@org_tensorflow//tensorflow/lite/c:common",
        "@org_tensorflow//tensorflow/lite/kernels:builtin_ops",
    ],
)

# To test it with Bazel, plugin a Coral device, and run the following command:
# bazel test tensorflow_lite_support/cc/test/task/vision:image_classifier_coral_test \
# --define darwinn_portable=1 --linkopt=-lusb-1.0
cc_test(
    name = "image_classifier_coral_test",
    srcs = ["image_classifier_coral_test.cc"],
    data = [
        "//tensorflow_lite_support/acceleration/configuration/testdata:test_files",
    ],
    tags = [
        "manual",
        "notap",  # Requires edge TPU device.
    ],
    deps = [
        "//tensorflow_lite_support/acceleration/configuration:edgetpu_coral_plugin",
        "//tensorflow_lite_support/cc/port:configuration_proto_inc",
        "//tensorflow_lite_support/cc/port:gtest_main",
        "//tensorflow_lite_support/cc/port:status_macros",
        "//tensorflow_lite_support/cc/task/vision:image_classifier",
        "//tensorflow_lite_support/cc/task/vision/core:frame_buffer",
        "//tensorflow_lite_support/cc/task/vision/proto:classifications_proto_inc",
        "//tensorflow_lite_support/cc/task/vision/proto:image_classifier_options_proto_inc",
        "//tensorflow_lite_support/cc/task/vision/utils:frame_buffer_common_utils",
        "//tensorflow_lite_support/examples/task/vision/desktop/utils:image_utils",
        "@com_google_absl//absl/status",
    ],
)

cc_test_with_tflite(
    name = "object_detector_test",
    srcs = ["object_detector_test.cc"],
    data = [
        "//tensorflow_lite_support/cc/test/testdata/task/vision:test_images",
        "//tensorflow_lite_support/cc/test/testdata/task/vision:test_models",
    ],
    tflite_deps = [
        "@org_tensorflow//tensorflow/lite/core/shims:cc_shims_test_util",
        "//tensorflow_lite_support/cc/task/core:task_api_factory",
        "//tensorflow_lite_support/cc/task/core:tflite_engine",
        "//tensorflow_lite_support/cc/task/vision:object_detector",
    ],
    deps = [
        "//tensorflow_lite_support/cc:common",
        "//tensorflow_lite_support/cc/port:gtest_main",
        "//tensorflow_lite_support/cc/port:status_macros",
        "//tensorflow_lite_support/cc/task/core:task_utils",
        "//tensorflow_lite_support/cc/task/vision/core:frame_buffer",
        "//tensorflow_lite_support/cc/task/vision/proto:bounding_box_proto_inc",
        "//tensorflow_lite_support/cc/task/vision/proto:classifications_proto_inc",
        "//tensorflow_lite_support/cc/task/vision/proto:detections_proto_inc",
        "//tensorflow_lite_support/cc/task/vision/proto:object_detector_options_proto_inc",
        "//tensorflow_lite_support/cc/task/vision/utils:frame_buffer_common_utils",
        "//tensorflow_lite_support/cc/task/vision/utils:frame_buffer_utils",
        "//tensorflow_lite_support/cc/test:test_utils",
        "//tensorflow_lite_support/examples/task/vision/desktop/utils:image_utils",
        "@com_google_absl//absl/flags:flag",
        "@com_google_absl//absl/status",
        "@com_google_absl//absl/strings:cord",
        "@org_tensorflow//tensorflow/lite:framework",
        "@org_tensorflow//tensorflow/lite/c:common",
        "@org_tensorflow//tensorflow/lite/kernels:builtin_ops",
    ],
)

cc_test_with_tflite(
    name = "image_segmenter_test",
    srcs = ["image_segmenter_test.cc"],
    data = [
        "//tensorflow_lite_support/cc/test/testdata/task/vision:test_images",
        "//tensorflow_lite_support/cc/test/testdata/task/vision:test_models",
    ],
    tflite_deps = [
        "@org_tensorflow//tensorflow/lite/core/shims:cc_shims_test_util",
        "//tensorflow_lite_support/cc/task/core:task_api_factory",
        "//tensorflow_lite_support/cc/task/core:tflite_engine",
        "//tensorflow_lite_support/cc/task/vision:image_segmenter",
    ],
    deps = [
        "//tensorflow_lite_support/cc:common",
        "//tensorflow_lite_support/cc/port:gtest_main",
        "//tensorflow_lite_support/cc/port:status_macros",
        "//tensorflow_lite_support/cc/task/core:task_utils",
        "//tensorflow_lite_support/cc/task/vision/core:frame_buffer",
        "//tensorflow_lite_support/cc/task/vision/proto:image_segmenter_options_proto_inc",
        "//tensorflow_lite_support/cc/task/vision/proto:segmentations_proto_inc",
        "//tensorflow_lite_support/cc/task/vision/utils:frame_buffer_common_utils",
        "//tensorflow_lite_support/cc/task/vision/utils:frame_buffer_utils",
        "//tensorflow_lite_support/cc/test:test_utils",
        "//tensorflow_lite_support/examples/task/vision/desktop/utils:image_utils",
        "@com_google_absl//absl/flags:flag",
        "@com_google_absl//absl/status",
        "@com_google_absl//absl/strings:cord",
        "@org_tensorflow//tensorflow/lite:framework",
        "@org_tensorflow//tensorflow/lite/c:common",
        "@org_tensorflow//tensorflow/lite/kernels:builtin_ops",
    ],
)

cc_test_with_tflite(
    name = "image_embedder_test",
    srcs = ["image_embedder_test.cc"],
    data = [
        "//tensorflow_lite_support/cc/test/testdata/task/vision:test_images",
        "//tensorflow_lite_support/cc/test/testdata/task/vision:test_models",
    ],
    tflite_deps = [
        "//tensorflow_lite_support/cc/task/vision:image_embedder",
        "@org_tensorflow//tensorflow/lite/core/shims:cc_shims_test_util",
    ],
    deps = [
        "//tensorflow_lite_support/cc:common",
        "//tensorflow_lite_support/cc/port:gtest_main",
        "//tensorflow_lite_support/cc/port:status_macros",
        "//tensorflow_lite_support/cc/task/vision/core:frame_buffer",
        "//tensorflow_lite_support/cc/task/vision/proto:bounding_box_proto_inc",
        "//tensorflow_lite_support/cc/task/vision/proto:embeddings_proto_inc",
        "//tensorflow_lite_support/cc/task/vision/proto:image_embedder_options_proto_inc",
        "//tensorflow_lite_support/cc/task/vision/utils:frame_buffer_common_utils",
        "//tensorflow_lite_support/cc/task/vision/utils:frame_buffer_utils",
        "//tensorflow_lite_support/cc/test:test_utils",
        "//tensorflow_lite_support/examples/task/vision/desktop/utils:image_utils",
        "@com_google_absl//absl/flags:flag",
        "@com_google_absl//absl/status",
        "@org_tensorflow//tensorflow/lite:framework",
        "@org_tensorflow//tensorflow/lite/c:common",
        "@org_tensorflow//tensorflow/lite/kernels:builtin_ops",
    ],
)
