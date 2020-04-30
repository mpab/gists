# Add bash shell to vscode

settings.json (F1->open settings.json icon)

```json
{
    "terminal.integrated.shell.windows": "D:\\Apps\\Git\\bin\\bash.exe",
    "terminal.integrated.env.windows": {
    "CHERE_INVOKING": "1"
    },
    "terminal.integrated.shellArgs.windows": [
    "-l"
    ]
 }
```
