# Macro Template
Template repository to create a DeepSource Macro.

Use this template to create custom analyzers (Macros) on DeepSource.

## Points to note
### In `.deepsource/analyzer/analyzer.toml`
- Ensure that you provide the correct entrypoint to the Macro by setting the `analyzer.command` field.
- The `version` is the version of the TOML config. It's always "1".

### In `.deepsource/analyzer/issues/<issue-code>.toml`
- For every unique issue that your Macro detects, add a corresponding issue description, with the format specified in the `issues/DM-W1001.toml` file.

### In `.deepsource/analyzer/Makefile`
- Copy the analysis code to `/app` directory. If the code is compiled, copy the binary to `/app`.
- If you are using `alpine`, ensure that you install `shadow`, which enables us to use `useradd` commands at the end of the build.
