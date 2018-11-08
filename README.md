# QGitTag

[![GitHub (pre-)release](https://img.shields.io/github/release/Shatur95/QGitTag/all.svg)](https://github.com/Shatur95/QGitTag/releases)

**QGitTag** is a library for **Qt5** that uses the GitHub API to provide information about releases that can be used to check for updates. [Detailed documentation](docs/QGitTag.md "Class documentation").

Example:
```cpp
QCoreApplication app(argc, argv);
QCoreApplication::setApplicationVersion("0.9.0");
QTextStream out(stdout);
    
QGitTag tag();
tag.get("Shatur95", "Crow-Translate")
if (tag.tagName() >= QCoreApplication::applicationVersion())
    out << "Update avaible: " + tag.url().toString() << endl;
```

For real example of usage you can look into my other project: [Crow Translate](https://github.com/Shatur95/CrowTranslate "A simple and lightweight translator that allows to translate and say the selected text using the Google Translate API").


## Installation

To include the library files I would recommend that you add it as a git submodule to your project and include it's contents with a `.pri` file. For example, if you want to clone the library in `src/third-party/` in your project, use this command to clone with **ssh**:

`git submodule add git@github.com:Shatur95/QGitTag.git src/third-party/qgittag`

or this to clone with **https**:

`git submodule add https://github.com/Shatur95/QGitTag.git src/third-party/qgittag`

or if you don't want to add the library as a submodule, you can download the archive from the [releases](https://github.com/Shatur95/QGitTag/releases) page and unpack it to the desired folder **manually**.

Then include the `qgittag.pri` file in your `.pro` project file:

`include(src/third-party/qgittag/qgittag.pri)`

**Header:**

```cpp
#include "qgittag.h"
```

**or:**

```cpp
#include <QGitTag>
```
