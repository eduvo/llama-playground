# llama-playground

## Requirements

If Nix and direnv are installed in your computer, packages are installed automatically.

Otherwise, install them manually:
- [llama.cpp](https://github.com/ggerganov/llama.cpp/)
- [huggingface-hub](https://huggingface.co/docs/huggingface_hub/en/guides/cli)

## Usage
1. Download a model from Hugging Face

For example, to download https://huggingface.co/TheBloke/Llama-2-7B-GGML:
```shell
huggingface-cli download TheBloke/Llama-2-7B-GGUF llama-2-7b.Q4_K_M.gguf --local-dir models/ --local-dir-use-symlinks False
```

2. Run llama with a prompt
```shell
llama -m models/llama-2-7b.Q4_K_M.gguf --color -p "Hello world!\n" -n 50 -e --log-disable
```

3. Run llama-server and visit http://localhost:8080
```shell
llama-server -m models/llama-2-7b.Q4_K_M.gguf
```
