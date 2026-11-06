# MP Programming Language

**MP** is a custom programming language with simple, readable syntax, functions, loops, variables, lists, dictionaries, and support for extensions.

MP runs through **Visual Studio Code** and uses **Node.js** to execute programs.

This guide explains how to install MP on a new Windows computer.

## 1. Requirements

Before installing MP, download and install:

- **[Visual Studio Code](https://code.visualstudio.com/download)** — The editor used to write and run MP programs.
- **[Node.js](https://nodejs.org/)** — Required to execute MP programs. The LTS version is recommended.

After installing Node.js, restart VS Code and open a new Terminal.

Run:

```powershell
node --version
npm --version
```

If both commands display version numbers, Node.js is installed correctly.

## 2. Download MP

1. Open the [MP GitHub repository](https://github.com/mmangaming999/Get_MP_language).
2. Open **Releases** and download the latest MP `.vsix` installer, if available.
3. Alternatively, click **Code → Download ZIP** to download the repository files.
4. Extract any ZIP files you downloaded.

The MP extension installer has a filename similar to:

```text
mp-language-0.6.9.vsix
```

Use the newest compatible version available in the repository.

**Note:** A source-code ZIP is not the same as a `.vsix` installer. If the repository contains only source code, you must build the extension or obtain a packaged VSIX.

## 3. Install MP in Visual Studio Code

1. Open Visual Studio Code.
2. Press `Ctrl + Shift + X` to open Extensions.
3. Click the three-dot (`...`) menu at the top of the Extensions panel.
4. Select **Install from VSIX...**
5. Select the downloaded MP `.vsix` file.
6. Reload VS Code if prompted.

MP should now be available in Visual Studio Code.

## 4. Run Your First MP Program

Create a new file named:

```text
hello.mp
```

Enter the following MP code:

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

Save the file and click the **Run** button provided by the MP extension in VS Code.

### Expected output

```text
Hello, World!
15
MP is working!
```

Congratulations! You have successfully installed and run MP.

## 5. Install getex (Optional)

**getex** is MP's extension installer. It allows you to install compatible MP extensions from GitHub.

Download the universal getex installer from its distribution package.

Extract the package and open a Terminal in the extracted folder.

Run:

```powershell
powershell -ExecutionPolicy Bypass -File .\install-getex.ps1
```

Close and reopen the Terminal after installation.

You can then install MP extensions using commands such as:

```powershell
getex MPxiom
getex MPG
```

You can also install compatible extensions from other GitHub creators:

```powershell
getex username/repository
```

Or provide a complete GitHub repository URL:

```powershell
getex https://github.com/username/repository
```

Only install extensions from sources you trust.

## 6. Available MP Extensions

### MPxiom — Mathematics

[MPxiom on GitHub](https://github.com/mmangaming999/MPxiom)

Install:

```powershell
getex MPxiom
```

Example:

```text
add "MPxiom"

say(factorial(5))
say(fibonacci(10))
say(isPrime(97))
```

### MPG — Graphics Engine

[MPG on GitHub](https://github.com/mmangaming999/MPG)

MPG allows MP programs to create desktop windows, display shapes, detect keyboard input, and build graphical applications.

Install:

```powershell
getex MPG
```

Example:

```text
add "MPG"

win("My First MPG Window", 640, 480)
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

This program should open a desktop window displaying a blue circle. Press Escape to close it.

MPG requires its desktop graphics dependencies, which getex installs through npm.

## 7. Basic MP Syntax

### Variables

```text
set score to 0
change score by 1
say(score)
```

### Conditions

```text
if (score > 10) do {
    say("High score!")
} elif (score > 5) do {
    say("Good score!")
} else do {
    say("Keep trying!")
}
```

### Functions

```text
Make greet(name) do {
    say("Hello, " + name)
}

greet("Alex")
```

### Loops

```text
set x to 0

Long(x < 5) do {
    say(x)
    change x by 1
}
```

### Lists

```text
set fruits to ["apple", "banana", "orange"]

append(fruits, "grape")

say(get(fruits, 0))
```

### Dictionaries

```text
set player to dict({
    "name" = "Alex",
    "score" = 100,
    "health" = 75
})

say(get(player, "name"))
```

### Comments

MP uses `^` to mark comments:

```text
^ This is an MP comment ^
```

Keep each comment on one line.

## 8. Troubleshooting

**MP files don't run**

Make sure Node.js is installed and the MP VS Code extension is enabled. Restart VS Code after installation.

**The Run button doesn't appear**

Check that your file has the `.mp` extension and that VS Code recognizes it as MP.

**An extension cannot be found**

Make sure getex is installed correctly, the GitHub repository is accessible, and the extension follows the supported package format.

**MPG doesn't open a window**

Check that MPG installed its Electron dependency successfully and that you're using a version of MP with MPG runtime support.

**A program shows an error**

Read the error in the VS Code Terminal. MP's editor can also detect some unknown function calls and suggest corrections.

## 9. About MP

MP is an independently developed programming language with a VS Code extension and an expandable ecosystem.

Its related projects include:

- **MP** — The programming language.
- **getex** — The extension installer.
- **MPxiom** — Mathematics functions.
- **MPG** — Desktop graphics and game development.

MP programs use the `.mp` file extension.

**Created by M-Man Gaming**

GitHub: [mmangaming999](https://github.com/mmangaming999)

---

**Enjoy programming with MP!**
