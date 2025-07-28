# Setup Strace

This composite GitHub Action wraps every `run:` command in your workflows using `strace`, without modifying the commands themselves.

## How to Use

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    defaults:
      run:
        shell: bash -l {0}
    steps:
      - uses: actions/checkout@v3
      - uses: your-org/setup-strace@v1
      - run: ./gradlew build
      - uses: actions/upload-artifact@v3
        with:
          name: strace-logs
          path: strace_logs
