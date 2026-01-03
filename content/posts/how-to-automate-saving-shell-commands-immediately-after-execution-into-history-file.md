---
date: "2022-06-01T20:19:00+00:00"
title: "How to Automate Saving Shell Commands Immediately After Execution Into History File"
---

By default, shell commands are first stored in internal memory and written to the **~/.bash_history** file only after the shell session exits properly.

Depending on how the shell is used, this behavior can lead to undesired results. For example, if a remote connection is disconnected unexpectedly, the history file will not be updated and previously executed commands will be lost. Additionally, while commands from an active session remain in memory, they are not accessible from other shell sessions.

## a) Configuring _Bash_

Open your **~/.bashrc** file in your preferred text editor with the appropriate privileges and add or edit the following line:

```sh
PROMPT_COMMAND="history -a"
```

This forces Bash to append each executed command to the history file immediately after execution.

## b) Reloading the Configuration

Apply the changes by sourcing the updated **~/.bashrc** file:

```sh
source ~/.bashrc
```

The automation will take effect immediately.

---

## Documentation

- <https://www.gnu.org/software/bash/manual/html_node/Controlling-the-Prompt.html>
- <https://tldp.org/HOWTO/Bash-Prompt-HOWTO/x264.html>
