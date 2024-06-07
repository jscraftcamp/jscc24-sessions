# Tauri

Matthias introduced us to Tauri, an Electron alternative which uses the OS native web view with a Rust backend.

His example app was an actually useful app that detects open ports and lets you kill the apps on click.
Check it out: https://github.com/ms-tng/tauri-demo

Interesting tidbits:
* Heavy security focus
* Uses a custom protocol to avoid opening a port
* Backend communication works via a special event system: "listen" for events and "invoke" handlers
* Uses lots of macros to generate handlers on Rust side
  * Special learning for me: A proc_macro is the wizard of macros as it is an actual separate program that has the full power of Rust to transform the Rust tokens

Also interesting:
* Rust supports async await syntax sugar, but it needs a "runtime"
* "tokio" is apparently the go-to choice here
* Supports .await but it is a keyword
* tokio::select is like Promise race, but it can actually abort the losing future

Error handling
* ? automatically converts errors into the expected format if implemented
* "anyhow" is another way to make it easier to handle errors without thinking about conversion
