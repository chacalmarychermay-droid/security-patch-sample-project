# security-patch-sample-project
Summary: This security patch fixes unsafe YAML deserialization in the configuration module by replacing yaml.load() with yaml.safe_load(), preventing arbitrary code execution from untrusted YAML input.  Before:
