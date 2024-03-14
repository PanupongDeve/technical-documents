Solving VS code cannot remote ssh

Why: VScode cannot download .vscode-server in host

Fix: 
    1. ctrl + shift + P > Perference: Open User Settings(JSON)
    2. add 
        "remote.SSH.useExecServer": false,
        "remote.SSH.localServerDownload": "always",
        at {} in settings
    3. restart vscode and try to remote to host