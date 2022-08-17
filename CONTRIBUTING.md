# Contributing

## Guidelines
1. Test the command and ensure that it works on a standard Linux environment[^1] with a bash shell. You can use the trickest base image on `quay.io/trickest/base` which is based on ubuntu with a few extra utilities installed.
2. Scripts are meant to process the output of a tool not invoke the tool itself
```bash
$ amass -d example.com | whatever ❌
$ cat in/amass-*/output.txt | whatever ✅
```
3. Always assume that the input comes through a folder named `in` and write the output to a folder named `out`.
4. If the script produces one file, write it to `out/output.txt`
5. Follow the [format specification](#format) to add a new script YAML file.
6. Do not edit [scripts.md](scripts.md) manually. This file is generated automatically
7. Use the defined pull request and issue templates when possible.

---

## Format
### Example
```
name: count-lines-in-all-files
description: Used to quickly count all lines inside of all files in in folder.
author: trickest
author_info: https://trickest.com
script: find in -type f -exec cat {} + | wc -l | tee out/output.txt
language: bash
```

| Property    | Description                                                                         |
|-------------|-------------------------------------------------------------------------------------|
| name        | The name of the script. Try to keep it short but descriptive                        |
| description | The long-form description of the script. Add as much detail as you think is needed. |
| author      | The name of the person who contributed the script.                                  |
| author_info | A link to the author's website/Twitter/GitHub where people can go to say thank you. |
| script      | The actual script code                                                              |
| language    | The language of the script. Currently supported languages: bash                     |

[^1]: Feel free to suggest installing new utilities though if you think they will be handy!
