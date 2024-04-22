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

https://github.com/thebrowsercompany/gha-google-bloaty/blob/a95329cc3da083f2844c9c3f21efcbf450e79397/action.yml#L7-L26