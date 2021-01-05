load("@rules_java//java:defs.bzl", "java_binary")

java_binary(
    name = "runner",
    srcs = ["Runner.java"],
    # main_class specifies the class that contains the main method.
    main_class = "com.cmdline.Runner",
    # Depnd on the root library target.  We put //:greeter
    deps = ["//:greeter"],
)

# Build: bazel build //src/com/cmdline:runner
# We would use bazel-bin/src/com/cmdline/runner to call the runner binary