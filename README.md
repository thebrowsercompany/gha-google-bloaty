# gha-google-bloaty

A GitHub action that builds and runs google bloaty

## Usage

An example workflow that runs this action:

```yml
- name: Run google/bloaty
  uses: thebrowsercompany/gha-google-bloaty@v1
  with:
    bloaty-args: --csv -d inputfiles,segments main.exe
    bloaty-output-file: ${{ github.workspace }}/bloaty-main-exe.csv
```

An example workflow that runs this action and attempts to cache bloaty
for subsequent runs:

```yml
- name: Run google/bloaty
  uses: thebrowsercompany/gha-google-bloaty@v1
  with:
    bloaty-args: --csv -d inputfiles,segments main.exe
    bloaty-output-file: ${{ github.workspace }}/bloaty-main-exe.csv
    cache-bloaty: 'true'
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
  description: The arguments to pass to bloaty. Input filenames must use absolute paths.
  default: ''
  required: true

bloaty-output-file:
  description: A filename where bloaty output should be written.
  default: 'bloaty-output'
  required: true

cache-bloaty:
  description: Cache the bloaty executable for faster builds.
  default: 'false'
  required: false

cache-bloaty-key:
  description: The key to use when caching bloaty. Only used if 'cache-bloaty' is true. Defaults to bloaty-<bloaty-version>
  default: ''
  required: false
```