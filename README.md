# security-patch-sample-project
Summary: This security patch fixes unsafe YAML deserialization in the configuration module by replacing yaml.load() with yaml.safe_load(), preventing arbitrary code execution from untrusted YAML input.  Before:

Before:

yaml.load() could deserialize arbitrary Python objects from untrusted YAML.

Potential remote code execution if malicious YAML is processed.

After:

Replaced yaml.load() with yaml.safe_load().

Only safe types (str, list, dict, etc.) are deserialized.

Added pytest unit tests to validate expected return types.
Impact:
Prevents potential code execution from malicious YAML input, improving security in all modules that use PyYAML. Low-risk change with high security impact.

Verification:
Clone repository and checkout branch
git checkout fix/yaml-safe-load
Install dependencies
pip install pyyaml pytest
Run tests
pytest -q
pytest -q
All tests should pass successfully.

Files Modified:

config_loader.py (replaced yaml.load() with yaml.safe_load())

tests/test_config_loader.py (added pytest unit tests)

Patch Link / PR:
example security patch project
Notes:

No exploit PoC included; only automated tests demonstrating safe behavior.

Low-risk, high-security impact in preventing unsafe YAML deserialization.

Contact:
MCG Chacal – chacalmarychermay@gmail.com

