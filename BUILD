load("@rules_java//java:defs.bzl", "java_binary")

java_binary(
    # name is the name of the target
    name = "ProjectRunner",
    # srcs specifies the source files that Bazel uses to build the target
    # uses glob to pass a set of source files to Bazel instead of listing them one by one
    srcs = glob(["src/com/*.java"]),
    # main_class specifies the class that contains the main method.
    main_class = "com.ProjectRunner",
    # When referencing targets within the same BUILD file,
    # you can even skip the // workspace root identifier and
    # just use :target-name.  So, :greeter here.
    deps = [":greeter"],
)
# Build: bazel build //:ProjectRunner or bazel build :ProjectRunner, skip // bc
# its at the workspace root
# bazel build //:ProjectRunner.  This will the project with two targets.
# The ProjectRunner target builds two source files and depends on one other
# target (:greeter), which builds one additional source file.
# We would use bazel-bin/src/com/cmdline/runner to call the runner binary

java_library(
    name = "greeter",
    srcs = ["src/com/Greeting.java"],
    # open up to the build file under src/com/cmdline
    visibility = ["//src/com/cmdline:__pkg__"],
)