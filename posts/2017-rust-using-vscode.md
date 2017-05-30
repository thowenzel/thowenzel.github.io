extends: default.liquid

title: Rust und Visual Studio Code
date:       06 Apr 2017 00:00:00 +0000
humandate:  06.04.2017
tags: rust, vscode
categories: Programming
path: 2017/rust-using-vscode.html
---
Wie in einem älteren Beitrag angekündigt habe, nutze ich inzwischen __[Visual Studio Code](https://code.visualstudio.com/)__.

__Visual Studio Code__ ist ein unter der MIT-Lizenz stehender Quelltext-Editor von Microsoft. Er ist für die Betriebssysteme Windows, MacOS und Linux verfügbar. Technologisch basiert __Visual Studio Code__ auf Electron (Framework) und ermöglicht auch Debugging, IntelliSense und Versionsverwaltung.

![Visual Studio Code](../img/vscode_editor_overview.png)

Warum ich umgestiegen bin, das habe ich ja in einem älteren [Blogbeitrag](../2017/atom-my-conclusion.html) schon beschrieben. Inzwischen kann ich sagen: __Visual Studio Code__ rockt!

### Extensions
VSCode lässt sich über das Installieren von Extensions sehr gut an die eigenen Bedürfnisse anpassen.

![Meine Liste der installierten Erweiterungen in VSCode](../img/vscode_editor_installed_extensions.png)

### VSCode installieren und für Rust anpassen
Ich arbeite momentan auf einem Windows-System, daher weichen die nachfolgenden Schritte auf Linux- oder Mac-Systemen ggf. leicht ab.


VSCode unterstützt das Highlighting von Rust-Syntax von Haus aus. Um aber einigermaßen produktiv arbeiten zu können, erwarte ich von einem Editor natürlich noch etwas mehr. Das Compilieren, Ausführen und Testen von Rust-Code soll möglich sein.

Als erstes installieren wir daher die Erweiterung __[Rust](https://github.com/editor-rs/vscode-rust)__, diese erweitert die Sprachunterstützung für Rust in VSCode erheblich. Die Erweiterung kann durch Auswahl des unteren Buttons in der Seitenleiste und der Suche nach 'Rust' installiert werden. Vor dem Installieren wird eine Infoseite angezeigt, die weitere Angaben zur Erweiterung bereithält. Nach der Installation lassen sich die Cargo-Kommandos, wie z.B. `build`, `test`, `run`, direkt in VSCode ausführen (Befehlspalette mit *Ctrl+Shift+P* öffnen, die Befehle beginnen alle mit `Cargo: `).

Alternativ lässt sich `cargo` natürlich auch über das integrierte Terminal bedienen.

The Erweiterung __[Rust](https://github.com/editor-rs/vscode-rust)__ besitzt zwar eine experimentelle Unterstützung für den Rust Language Server, aber richtig gut funktioniert das noch nicht. Daher aktivieren wir noch den legacy mode von __racer__ in the Einstellungen von VSCode.

Die Einstellungen werden von VSCode in einer JSON-Datei gespeichert und müssen auch in dieser bearbeitet werden. Dazu *Datei > Einstellungen > Einstellungen* aufrufen (oder *Ctrl + Comma* klicken). Es öffnet sich die Datei `settings.json`. Auf der rechten Seite können die Benutzerdefinierten Einstellungen eingetragen werden. Dort folgende Einstellungen vornehmen:

```
{
    "editor.formatOnSave": true,
    "editor.rulers": [80],
    "files.trimTrailingWhitespace": true,
    "rust.actionOnSave": "check",
    "rust.forceLegacyMode": true,
    "workbench.iconTheme": "vscode-icons"
}
```

#### Weiterführende Links:
* [Setting up a Rust Development Environment](http://asquera.de/blog/2017-03-03/setting-up-a-rust-devenv/)
* [Using Visual Studio Code for Rust on Ubuntu](https://klausi.github.io/rustnish/2017/05/28/using-visual-studio-code-for-rust-on-ubuntu.html)