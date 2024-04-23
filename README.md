# gha-google-bloaty

A GitHub action that builds and runs google bloaty

## Usage

An example workflow that runs this action:

```yml
- name: Run google/bloaty
  uses: thebrowsercompany/gha-google-bloaty
  with:
    bloaty_version: main
    bloaty_args: --csv -d inputfiles,segments main.exe
```

### Inputs

```yml
bloaty-version:
  description: A Git ref specifying the version of bloaty to build.
  default: 'refs/heads/main'
  required: false

bloaty-checkout-dir:
  description: Where to clone and build google/bloaty
  default: ${{ github.workspace }}/.google-bloaty
  required: false

bloaty-args:
  description: The arguments to pass to bloaty.
  default: ''
  required: true

bloaty-output-file:
  description: A filename where bloaty output should be written.
  default: ''
  required: false

cache-bloaty:
  description: Cache the bloaty executable for faster builds. The cache key is 'bloaty-<bloaty-version>'
  default: 'false'
  required: false
```