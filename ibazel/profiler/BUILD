# Copyright 2017 The Bazel Authors. All rights reserved.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#    http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

load("@io_bazel_rules_go//go:def.bzl", "go_embed_data", "go_library")

go_embed_data(
    name = "js",
    src = "profiler.js",
    package = "profiler",
    var = "js",
)

go_library(
    name = "go_default_library",
    srcs = [
        "profiler.go",
        ":js",  # keep
    ],
    importpath = "github.com/bazelbuild/bazel-watcher/ibazel/profiler",
    visibility = ["//ibazel:__subpackages__"],
    deps = [
        "//ibazel/log:go_default_library",
        "//third_party/bazel/master/src/main/protobuf/blaze_query:go_default_library",
    ],
)
