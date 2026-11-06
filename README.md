
# MP Programming Language

**MP** is a custom programming language designed for readable programs, with variables, functions, loops, lists, dictionaries, and optional extensions. Write `.mp` files in **Visual Studio Code** and run them with **Node.js**.

This repository contains the installers you need to get started on **Windows**.

## Download MP

You are already on the MP GitHub repository! The installer files are in the file list above this README:

| File | Purpose |
| --- | --- |
| [`mp-language-0.6.9.vsix`](./mp-language-0.6.9.vsix) | MP language extension for Visual Studio Code |
| [`getex-universal-0.3.0.zip`](./getex-universal-0.3.0.zip) | Optional extension installer for MP packages |

**To download a file:** click its filename in GitHub, then click the **Download raw file** icon (or **View raw / Download raw file**, depending on GitHub's layout). **Do not copy the file's preview or the GitHub page URL into VS Code.** Download the actual `.vsix` file.

## 1. Install the prerequisites

1. Install [Visual Studio Code](https://code.visualstudio.com/download).
2. Install the LTS release of [Node.js](https://nodejs.org/en/download).
3. Restart VS Code after installing Node.js.

Open **Terminal → New Terminal** in VS Code and verify:

```powershell
node --version
npm --version
```

Both commands should print version numbers.

## 2. Install MP in VS Code

1. Download [`mp-language-0.6.9.vsix`](./mp-language-0.6.9.vsix) from this repository.
2. Open VS Code and press **Ctrl+Shift+X** to open the Extensions view.
3. Select the **…** menu at the top of the Extensions view.
4. Click **Install from VSIX…** and select the downloaded `.vsix` file.
5. Reload VS Code if prompted.

> **Note:** You do not need to install MP from the VS Code Marketplace. The `.vsix` file in this repository is the installer.

## 3. Enable the MP logo and syntax colors

After installing, VS Code may keep your previous themes. If the **MP logo does not appear**, or **`Make` looks blue instead of pink**, enable MP's included themes manually.

### Show MP file icons

1. Press **Ctrl+Shift+P** to open the Command Palette.
2. Search for **Preferences: File Icon Theme** and select it.
3. Choose **MP File Icons**.

This enables the MP icon for `.mp` files in VS Code.

### Make `Make` pink

1. Press **Ctrl+Shift+P** again.
2. Search for **Preferences: Color Theme** and select it.
3. Choose **MP Blue Dark**.

The function declaration keyword **`Make`** should now appear **pink**. Other MP keywords, such as `do`, use the theme's blue styling.

`Make` is **capitalized** in MP source code. Write `Make`, not `make`.

If the changes do not appear immediately, run **Developer: Reload Window** from the Command Palette. Also ensure the file has a `.mp` extension and that the language mode in the bottom-right corner of VS Code is **MP**.

## 4. Run your first MP program

Create a file named **`hello.mp`** in VS Code, paste the following code, and save it:

```text
^ My first MP program ^

say("Hello, World!")

set x to 10
change x by 5
say(x)

Make hello() do {
    say("MP is working!")
}

hello()
```

Click the MP **▶ Run** button in the editor.

Expected Terminal output:

```text
Hello, World!
15
MP is working!
```

## 5. Install extensions with getex (optional)

**getex** installs compatible extensions for MP from GitHub. You do not need getex to run basic MP programs.

1. Download [`getex-universal-0.3.0.zip`](./getex-universal-0.3.0.zip) from this repository.
2. Extract the ZIP.
3. Open a Windows Terminal in the folder containing `install-getex.ps1`.
4. Run:

```powershell
powershell -ExecutionPolicy Bypass -File .\install-getex.ps1
```

Close and reopen the Terminal. You can then install optional libraries:

```powershell
getex MPxiom
getex MPG
```

You can also specify compatible GitHub projects directly:

```powershell
getex username/repository
getex https://github.com/username/repository
```

Only install extensions from repositories you trust: some may run dependency installation scripts.

### MPxiom: math functions

GitHub: [MPxiom](https://github.com/mmangaming999/MPxiom)

```text
add "MPxiom"
say(factorial(5))
say(fibonacci(10))
```

### MPG: graphics and game development

GitHub: [MPG](https://github.com/mmangaming999/MPG)

```text
add "MPG"

win("Hello MPG!", 640, 480)
fps(60)
background("black")

goto(320, 240)
set ball to stamp("circle", 30, "blue")

Long(isopen()) do {
    if (key("escape")) do {
        quit()
    }
    clear()
    update()
}
```

MPG uses a desktop window and has additional runtime dependencies, installed via getex. Ensure you're running MP v0.6.9 or another version that supports MPG.

## 6. MP syntax at a glance

```text
^ Single-line comment ^

set score to 0
change score by 1

if (score > 10) do {
    say("High score!")
} elif (score > 5) do {
    say("Nice!")
} else do {
    say("Keep going!")
}

Make greet(name) do {
    return "Hello, " + name
}

say(greet("Alex"))

set items to ["apple", "banana"]
append(items, "grape")
say(get(items, 0))

set player to dict({
    "name" = "Alex",
    "score" = 100
})
say(get(player, "name"))
```

**Remember:** MP comments using `^ ... ^` should stay on a single line, and MP syntax is not identical to JavaScript or Python.

## Troubleshooting

| Problem | Try this |
| --- | --- |
| `node` or `npm` is not recognized | Install Node.js and reopen VS Code/Terminal. |
| The MP **▶ Run** button is missing | Ensure `.mp` file extension, set language mode to **MP**, and verify the VSIX extension is installed and enabled. |
| MP logo is missing | **Ctrl+Shift+P → Preferences: File Icon Theme → MP File Icons**. |
| `Make` is lowercase or colored blue | Type **`Make`** with a capital M, then choose **MP Blue Dark** under **Preferences: Color Theme**. |
| Colors or icons still look wrong | Run **Developer: Reload Window**. |
| `add "MPG"` cannot load | Install getex, then run `getex MPG`; use an MP version with MPG support. |
| MPG window does not launch | Check Electron/dependency installation and the error output in the VS Code Terminal. |
| F5 asks for a debugger | MP v0.6.9 does not include a dedicated VS Code debugger; use MP's **▶ Run** button. |

## Project links

- [MP programming language](https://github.com/mmangaming999/Get_MP_language)
- [MPxiom mathematics extension](https://github.com/mmangaming999/MPxiom)
- [MPG graphics engine](https://github.com/mmangaming999/MPG)
- [M-Man Gaming on GitHub](https://github.com/mmangaming999)

**Created by M-Man Gaming. Enjoy coding in MP!**
