# gpt3-cli
Command-line interface for OpenAI's GPT-3
### Usecases
 * Use GPT-3 distraction-free: Just you and the terminal
 * Distraction-free
### Features
 - [x] Streaming
 - [x] Easy to install
 - [x] Documentation
 - [x] Any temperature up to 2.0 (unlike the Playground)  
 - [ ] Proper error echoing
 - [ ] Search endpoint
```
git clone https://github.com/CrazyPython/gpt3-cli.git
echo "export PATH=\"$(realpath gpt3-cli):\$PATH\"" >> ~/.bash_profile
echo 'export OPENAI_KEY="'$(printf "Your OpenAPI Key: " >&2; head -n 1)'"'  >> ~/.bash_profile
```

Type `source ~/.bash_profile` to get it working immediately without a shell restart.
Usage summary: Inside the brackets means "optional"
`gpt3 [parameters] "prompt" [max_tokens]`
## Parameters
Set OPENAI_KEY as an environment variable
Can be passed via the command-line, or via environment variables. command-line options override environment variables. Environment variables are used for defaults in scripts and environments.


## Examples

## License
**N.B.** You have the full right to base any closed-source or open-source program on this software if it remains on your own, your company's, or your company's contractors computers and cloud servers. (In other words, you can use this to build a closed-source SaaS.) If you distribute a program to a third-party end-user, you are required to give them the source code. The requirement to share source code only applies when distributed to other people. This is the GPLv3's private use clause
The intent is to ensure GPT-3 developer tools remain [open-source](https://www.gnu.org/philosophy/free-sw.en.html). OpenAI asks that end-users of products that use GPT-3 products be shielded from direct API access, so this license should not impose any restriction. A copy of the private use exception is copied below:
> All rights granted under this License are granted for the term of copyright on the Program, and are irrevocable provided the stated conditions are met. This License explicitly affirms your unlimited permission to run the unmodified Program. The output from running a covered work is covered by this License only if the output, given its content, constitutes a covered work. This License acknowledges your rights of fair use or other equivalent, as provided by copyright law.
> You may make, run and propagate covered works that you do not convey, without conditions so long as your license otherwise remains in force. You may convey covered works to others for the sole purpose of having them make modifications exclusively for you, or provide you with facilities for running those works, provided that you comply with the terms of this License in conveying all material for which you do not control copyright. Those thus making or running the covered works for you must do so exclusively on your behalf, under your direction and control, on terms that prohibit them from making any copies of your copyrighted material outside their relationship with you.

AGPLv3.

The requirement to release source code only if you distribute the software to other people.
