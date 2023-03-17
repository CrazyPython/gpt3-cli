# gpt3-cli
Streaming command-line interface for OpenAI's GPT-3

Also supports ChatGPT (non-streaming)

Use the `ask-gpt3` and `ask-chatgpt` scripts for prettier formatting
### Usecases
 * Use GPT-3 distraction-free: Just you and the terminal
 * Command-line remembers your past prompts and output history
 * Command-line streams just like the Playground
### Features
 - [x] Streaming
 - [x] Any temperature up to 2.0 (unlike Playground)  
 - [x] Any presence and frequency penalty up to 2.0
 - [x] Easy to install
 - [x] Documentation
 - [ ] Proper error echoing
 - [ ] Search endpoint

### Installation
0. If you are on Windows, install [Git for Windows](https://gitforwindows.org)
1. Install [jq](https://stedolan.github.io/jq/download/)
2. Run these commands (on macOS, at the built-in Terminal app. on Windows, at Git Bash)
```
git clone https://github.com/CrazyPython/gpt3-cli.git
echo "export PATH=\"$(realpath gpt3-cli):\$PATH\"" >> ~/.bash_profile
echo 'export OPENAI_API_KEY="'$(printf "Your OpenAPI Key: " >&2; head -n 1)'"'  >> ~/.bash_profile
```

Type `source ~/.bash_profile` to get it working immediately without a shell restart.

## Usage summary
Inside the brackets means "optional"
```
gpt3 [parameters] "prompt" [max_tokens]
```

## `[parameters]`
Set OPENAI_KEY as an environment variable
Can be passed via the command-line, or via environment variables. command-line options override environment variables. Environment variables are used for defaults in scripts and environments.

- `-e`/`--engine` - or the `ENGINE` environment variable
- `-t`/`--temperature` - or the `TEMPERATURE` environment variable
- `-f`/`--freq-penalty` - or the `FREQ_PENALTY` environment variable
- `-p`/`--pres-penalty` - or the `PRES_PENALTY` environment variable

Defaults to OpenAI's defaults.

## Examples

### Basic usage

```
gpt3 --engine ada --temperature 0.5 --freq-penalty 1 --pres-penalty 1 \
    "As Descartes said, I think therefore" 2
``` 

The prompt of the above command is "As Descartes said, I think therefore".
The max tokens of the above command is 2.

Shorthand version of the same above command:

```
gpt3 -e ada -t 0.5 -f 1 -p 1 "As Descartes said, I think therefore" 2
```


### Setting global defaults to frequency and presency penalty 1

Add these lines to your `~/.bash_profile`:

```
export FREQ_PENALTY=1
export PRES_PENALTY=1
```

### Keep your input and prompt separate and concatenate them togehter

1. Make a folder, "myproject"
2. `cd myproject`
3. Make a new file, input1.txt with your favorite editor
4. Make a new file, prompt.txt with your favorite editor
5. Run `gpt3 -e davinci-instruct-beta "$(cat input.txt prompt.txt)" 100`

This concatenates the input and the prompt together, input first, prompt second,and streams the result with 100 max tokens.

## File upload via CLI
Try [OpenAI's Python tool.](https://github.com/openai/openai-python#openai-python-library)

## License
**N.B.** You have the full right to base any closed-source or open-source program on this software if it remains on your own, your company's, or your company's contractors computers and cloud servers. (In other words, you can use this to build a closed-source SaaS.) If you distribute a program to a third-party end-user, you are required to give them the source code. The requirement to share source code only applies when distributed to other people. This is the GPLv3's private use clause.
The intent is to ensure GPT-3 developer tools remain [open-source](https://www.gnu.org/philosophy/free-sw.en.html). OpenAI asks that end-users of products that use GPT-3 products be shielded from direct API access, so this license should not impose any restriction. A copy of the private use exception is copied below:
> All rights granted under this License are granted for the term of copyright on the Program, and are irrevocable provided the stated conditions are met. This License explicitly affirms your unlimited permission to run the unmodified Program. The output from running a covered work is covered by this License only if the output, given its content, constitutes a covered work. This License acknowledges your rights of fair use or other equivalent, as provided by copyright law.
> You may make, run and propagate covered works that you do not convey, without conditions so long as your license otherwise remains in force. You may convey covered works to others for the sole purpose of having them make modifications exclusively for you, or provide you with facilities for running those works, provided that you comply with the terms of this License in conveying all material for which you do not control copyright. Those thus making or running the covered works for you must do so exclusively on your behalf, under your direction and control, on terms that prohibit them from making any copies of your copyrighted material outside their relationship with you.

AGPLv3. As long as you use this library on a server, you do not have to release any source code that is in a separate file, because AGPLv3 can be linked with GPLV3, and GPLv3 has a private use clause.
