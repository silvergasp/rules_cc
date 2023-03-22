workspace(name = "rules_cc")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "rules_pkg",
    sha256 = "352c090cc3d3f9a6b4e676cf42a6047c16824959b438895a76c2989c6d7c246a",
    urls = [
        "https://github.com/bazelbuild/rules_pkg/releases/download/0.2.5/rules_pkg-0.2.5.tar.gz",
        "https://mirror.bazel.build/github.com/bazelbuild/rules_pkg/releases/download/0.2.5/rules_pkg-0.2.5.tar.gz",
    ],
)

load("@rules_pkg//:deps.bzl", "rules_pkg_dependencies")

rules_pkg_dependencies()

http_archive(
    name = "bazel_federation",
    sha256 = "d7a9b12474c772b389b3e24dde281f0332d7ef8645df47c80d122e9d446b883c",
    strip_prefix = "bazel-federation-8ce885a3a89da83228cd845c6ab13bb0175ca105",
    type = "zip",
    url = "https://github.com/bazelbuild/bazel-federation/archive/8ce885a3a89da83228cd845c6ab13bb0175ca105.zip",  # 2019-09-30
)

load("@bazel_federation//:repositories.bzl", "rules_cc_deps")

rules_cc_deps()

load("@bazel_federation//setup:rules_cc.bzl", "rules_cc_setup")

rules_cc_setup()

#
# Dependencies for development of rules_cc itself.
#
load("//:internal_deps.bzl", "rules_cc_internal_deps")

rules_cc_internal_deps()

load("//:internal_setup.bzl", "rules_cc_internal_setup")

rules_cc_internal_setup()

http_archive(
    name = "com_google_googletest",
    sha256 = "9dc9157a9a1551ec7a7e43daea9a694a0bb5fb8bec81235d8a1e6ef64c716dcb",
    strip_prefix = "googletest-release-1.10.0",
    urls = [
        "https://mirror.bazel.build/github.com/google/googletest/archive/release-1.10.0.tar.gz",
        "https://github.com/google/googletest/archive/release-1.10.0.tar.gz",
    ],
)

http_archive(
    name = "rules_proto",
    sha256 = "1357c68ef1c3644cafad6ae1822d99c06b94ef2cd8e01c783968703f61373d18",
    strip_prefix = "rules_proto-71c4fc69900946093ac5c82d81efd19fa522d060",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_proto/archive/71c4fc69900946093ac5c82d81efd19fa522d060.tar.gz",
        "https://github.com/bazelbuild/rules_proto/archive/71c4fc69900946093ac5c82d81efd19fa522d060.tar.gz",
    ],
)

load("@rules_proto//proto:repositories.bzl", "rules_proto_dependencies", "rules_proto_toolchains")

rules_proto_dependencies()

rules_proto_toolchains()

load("//cc:repositories.bzl", "rules_cc_toolchains")

rules_cc_toolchains()

local_repository(
    name = "test_repo",
    path = "examples/test_cc_shared_library2",
)
