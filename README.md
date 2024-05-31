# micromamba-vscode-compat
Make vscode-python extension compatible with micromamba.

## Features

Enables VSCode Python Extension to: 
1. recognize micromamba environments and list them as interpreters.
2. automatically activate the selected conda environment in the Terminal.

## Dependencies

- `sed`
- `jq`

## Usage

1. First, copy some files to the micromamba directory.

```bash
# Make sure your shell is at the root of this project

# Copy activation script
mkdir -p ~/micromamba/bin
cp src/bin/activate ~/micromamba/bin/activate
chmod +x ~/micromamba/bin/activate

# Copy micromamba wrapper
cp src/conda.sh ~/micromamba/conda.sh
chmod +x ~/micromamba/conda.sh

```

2. Modify the user level `settings.json` of VSCode.
Remember to replace `$HOME` with the absolute path.

```json
{
  "python.condaPath": "$HOME/micromamba/conda.sh",
}
```

Done.
