# Usage

Hydrogen provides a selection of commands for running code. Press ⌘-⇧-P to open the command palette and type "hydrogen" and they will come up.

## "Hydrogen: Run"
There are two ways to tell Hydrogen which code in your file to run.

1. **Selected code:** If you have code selected when you hit Run, Hydrogen will run exactly that code.
2. **Current block:** With no code selected, Hydrogen will try to find the complete block that's on or before the current line.

    - If the line you're on is already a complete expression (like `s = "abracadabra"`), Hydrogen will run just that line.

    - If the line you're on is the start of a block like a `for` loop, Hydrogen will run the whole block.

    - If the line you're on is blank, Hydrogen will run the first block above that line.

It's easiest to see these interactions visually:

![execute](https://cloud.githubusercontent.com/assets/13285808/20360915/a16efcba-ac03-11e6-9d5c-3489b3c3c85f.gif)

**"Hydrogen: Run And Move Down"** will run the the code as described above and move the cursor to the next executable line.

If your code starts getting cluttered up with results, run **"Hydrogen: Clear Results"** to remove them all at once.

## "Hydrogen: Run Cell"
A "code cell" is a block of lines to be executed at once. You can define them using inline comments. Hydrogen supports a
multitude of ways to define cells. Pick the one you like best.
The following is an example for `python` but it will work in any language, just replace `#` with the comment symbol for your desired language:

<img width=280 src="https://cloud.githubusercontent.com/assets/13285808/17094174/e8ec17b8-524d-11e6-9140-60b43e073619.png">

When you place the cursor inside a cell and hit **"Run Cell"**, Hydrogen will execute this cell. The command **"Hydrogen: Run Cell And Move Down"** will move the cursor to the next cell after execution.

## "Hydrogen: Run All" and "Hydrogen: Run All Above"
These commands will run all code inside the editor or all code above the cursor.


## Watch Expressions

After you've run some code with Hydrogen, you can use the **"Hydrogen: Toggle Watches"** command from the Command Palette to open the watch expression sidebar. Whatever code you write in watch expressions will be re-run after each time you send that kernel any other code.

![watch](https://cloud.githubusercontent.com/assets/13285808/20361086/4434ab3e-ac04-11e6-8298-1fb925de4e78.gif)

**IMPORTANT:** Be careful what you put in your watch expressions. If you write code that mutates state in a watch expression, that code will get run after every execute command and likely result in some _extremely confusing_ bugs.


You can re-run the watch expressions by using the normal run shortcut (⌘-↩ by default) inside a watch expression's edit field.

If you have multiple kernels running, you can switch between their watch expressions with the **"Hydrogen: Select Watch Kernel"** command (or just click on the "Kernel: <language>" text).

## Completion

Receive completions from the running kernel.

<img width="416" src="https://cloud.githubusercontent.com/assets/13285808/14108987/35d17fae-f5c0-11e5-9c0b-ee899387f4d9.png">

## Code Introspection

You can use the **"Hydrogen: Toggle Inspector"** command from the Command Palette to get metadata from the kernel about the object under the cursor.

<img width="770" src="https://cloud.githubusercontent.com/assets/13285808/14108719/d72762bc-f5be-11e5-8188-32725e3d2726.png">

## Managing kernels

Sometimes things go wrong. Maybe you've written an infinite loop, maybe the kernel has crashed, or maybe you just want to clear the kernel's namespace. Use the command palette to **interrupt** (think `Ctrl-C` in a REPL) or **restart** the kernel.

You can also access these commands by clicking on the kernel status in the status bar or via the command palette. It looks like this:

<img src="https://cloud.githubusercontent.com/assets/13285808/16894732/e4e5b4de-4b5f-11e6-8b8e-facf17a7c6c4.png" width=300>

Additionally, if you have two or more kernels for a particular language (grammar), you can select which kernel to use with the "Switch to <kernel>" option in the Kernel Commands menu.

## Multiple kernels inside one rich document

If you are working in a markup file that supports highlighted code blocks, we can handle multiple kernels per file. This way you can write your documentation, readme or paper together with your code while retaining the interactivity of Hydrogen.

<img src="https://cloud.githubusercontent.com/assets/13285808/24365090/0af6a91c-1315-11e7-92c6-849031bf9f6a.gif" height=350>

We support [markdown](https://github.com/burodepeper/language-markdown), [gfm](https://github.com/atom/language-gfm), [asciidoc](https://github.com/asciidoctor/atom-language-asciidoc), [reStructuredText](https://github.com/Lukasa/language-restructuredtext) and [knitr](https://github.com/christophergandrud/language-knitr/).