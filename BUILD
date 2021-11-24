load("@bazel_gazelle//:def.bzl", "gazelle")

# gazelle:prefix literate-markdown-lightning-talk
# gazelle:proto disable_global
gazelle(name = "gazelle")

genrule(
  name="generate_from_example_md",
  tools=["//vendor/lmt:lmt"],
  srcs=["example.md"],
  outs=["foo.hpp", "foo.cpp"],
  cmd="pwd ; $(location //vendor/lmt:lmt) $(location example.md) 2>&1 | { ! grep '[^[:blank:]]'; } && mv foo.hpp $(location foo.hpp) && mv foo.cpp $(location foo.cpp)",
)

cc_library(
  name="foo",
  srcs=["foo.cpp"],
  hdrs=["foo.hpp"],
)

