# FastAPI server converted into a single executable binary.

The binary can be used inside Tauri app.

## Pyinstaller executable setup

First we need to generate a spec file from pyinstaller. To do that we need to point pyinstaller to main.py file using:

```
pyinstaller --onefile --distpath ./bin ./src/server.py
```

The above command will create a `main.spec` file in root folder. Now we need to reuse this spec file onward. Rename the spec file to `pyinstaller.spec` so that it won't be overrided by default pyinstaller for future usage.

After this, if we need to add some files or modify config we need to that in `main.spec` file and we point pyinstaller to this spec file instead of `main.py` file. So now command will be:

```
pyinstaller --distpath ./bin ./pyinstaller.spec
```
