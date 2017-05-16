extends: default.liquid

title: Warum Rust
date:       16 May 2017 00:00:00 +0000
humandate:  16.05.2017
tags: rust
categories: Programming
path: /2017/why-rust.html
---
Warum überhaupt Rust? 

Rust ist eine System-Programmiersprache, bei deren Konzeption gleichermaßen viel Wert auf Sicherheit, Geschwindigkeit und Parallelität gelegt wurde. Durch die verwendeten Konzepte sollen solche Programmierfehler weitgehend ausgeschlossen werden, die zu Speicherzugriffsfehlern oder Pufferüberläufen und damit häufig zu Sicherheitslücken führen. Im Gegensatz zu anderen Programmiersprachen mit automatischer Speicherverwaltung verwendet Rust hierfür keine Garbage Collection, sondern setzt auf ein besonderes Typsystem.

Rust ist eine Multiparadigmen-Programmiersprache, das heißt die Sprache vereint Ansätze aus verschiedenen Programmierparadigmen, unter anderem aus der funktionalen, der objektorientierten und der nebenläufigen Programmierung, und erlaubt so ein hohes Abstraktionsniveau. Beispielsweise gibt es in Rust algebraische Datentypen, Pattern Matching, Traits (ähnlich den Typklassen in Haskell), Closures, sowie Unterstützung für RAII. Die Sprache wurde so entworfen, dass die Kosten der Abstraktionen zur Laufzeit so gering wie möglich bleiben können (zero-cost abstractions), um eine mit C++ vergleichbare Effizienz zu erreichen.

Die Entwicklung der Sprache begann als persönliches Projekt von Graydon Hoare, einem Mozilla-Mitarbeiter.
Rust 1.0, die erste stabile Version von Rust (Compiler und Standardbibliothek), wurde am 15. Mai 2015 veröffentlicht.

#### Weiterführende Links:
* [Vorlesung „Programmieren in Rust“, Universität Osnabrück](https://github.com/LukasKalbertodt/programmieren-in-rust)
* [rust-learning - A bunch of links to blog posts, articles, videos, etc for learning Rust.](https://github.com/ctjhoa/rust-learning)
* [Learning Rust - Medium](https://medium.com/learning-rust)