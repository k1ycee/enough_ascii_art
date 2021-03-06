An ASCII art library for Dart developers.

Available under the commercial friendly 
[MPL Mozilla License 2.0](https://www.mozilla.org/en-US/MPL/).

## Usage

Things you can do with `enough_ascii_art`:
* Generate a textual representation of an image using `convertImage(..)`.
* Convert common UTF-8 emoticons to their text-representation with `convertEmoticons(..)`.
* Create [FIGlet](https://en.wikipedia.org/wiki/FIGlet) text banners with `renderFiglet(..)`. 

Usage example:

```dart
import 'dart:io';
import 'package:enough_ascii_art/enough_ascii_art.dart';
import 'package:image/image.dart' as img;

void main() async {
  var image = img.decodeImage(File('./example/enough.jpg').readAsBytesSync());
  var asciiImage = convertImage(image, maxWidth: 40, invert: true);
  print('');
  print(asciiImage);
  var helloWithUtf8Smileys = 'hello world 😛';
  var helloWithTextSmileys =
      convertEmoticons(helloWithUtf8Smileys, EmoticonStyle.western);
  print('');
  print(helloWithTextSmileys);
  print('');
  print('cosmic:');
  var figure = await renderFigletWithFontName('ENOUGH', 'cosmic');
  print(figure);
  print('');
  print('shadow:');
  figure = await renderFigletWithFontName('ENOUGH', 'shadow');
  print(figure);
  print('');
  print('smslant:');
  figure = await renderFigletWithFontName('ENOUGH', 'smslant');
  print(figure);
  print('');
  print('eftifont:');
  figure = await renderFigletWithFontName('ENOUGH', 'eftifont');
  print(figure);
  print('');
  print('big:');
  figure = await renderFigletWithFontName('ENOUGH', 'big');
  print(figure);
  print('');
  print('isometric1:');
  figure = await renderFigletWithFontName('ENOUGH', 'isometric1');
  print(figure);
  print('');
  print('chunky:');
  figure = await renderFigletWithFontName('ENOUGH', 'chunky');
  print(figure);
  print('');
}
```

The above code renders the following output:

```
%%%%%%%%%%%%%%%%%%@%@%#%#%%%%%%%%%%%%%%%
%%%%%%%%%%%%%%%%%%##      -@%%%%%%%%%%%%
%%%%%%%%%%%%%%%%%%.        .#%%%%%%%%%%%
%%%%%%%%%%%%%%%%%#          #%%%%%%%%%%%
%%%%%%%%%%%%%%%%#@           %%%%%%%%%%%
%%%%%%%%%%%%% #*  #      @   %%%%%%%%%%%
%%%%%%%%%%%%%%-    *   =%    #%%%%%%%%%%
%%%%%%%%%%%%%%@#      *%     .#%%%%%%%%%
%%%%%%%%%%%%%%%%-    .@%%       %%%%%%%%
%%%%%%%%%%%%%%%=    @%%@          #%%%%%
%%%%%%%%%%%%%%#     #%%=            ##%%
%%%%%%%%%%%%%%%.      .               #%
%%%%%%%%%%%%%%%%@                      *
%%%%%%%%%%%%%%%%%%%%%%
%%%%%%%%%%%%%%%%%%%%%%
%%%%%%%%%%%%%%%%%%%%%%                 #
%%%%%%%%%%%%%%%%%%%%%%-              +%%
%%%%%%%%%%%%%%%%%%%%%%%.             %%%
%%%%%%%%%%%%%%%%%%%%%%%.           :%%%%
%%%%%%%%%%%%%%%%%%%%%%.             +@%%
%%%%%%%%%%%%%%%%%%%%%%    +%%%%%@    @%%
%%%%%%%%%%%%%%%%%%%%%.    @%%%%%#     %%
%%%%%%%%%%%%%%%%%%%%%     #%%%%%@     %%
%%%%%%%%%%%%%%%%%%%%%%-  -%%%%%%      %%


hello world :-P

cosmic:
.,:::::::::.    :::.    ...      ...    :::  .,-:::::/    ::   .:
;;;;''''`;;;;,  `;;; .;;;;;;;.   ;;     ;;;,;;-'````'    ,;;   ;;,
 [[cccc   [[[[[. '[[,[[     \[[,[['     [[[[[[   [[[[[[/,[[[,,,[[[
 $$""""   $$$ "Y$c$$$$$,     $$$$$      $$$"$$c.    "$$ "$$$"""$$$
 888oo,__ 888    Y88"888,_ _,88P88    .d888 `Y8bo,,,o88o 888   "88o
 """"YUMMMMMM     YM  "YMMMMMP"  "YmmMMMM""   `'YMUP"YMM MMM    YMM


shadow:
 ____|  \  |  _ \  |   |  ___| |   |
 __|     \ | |   | |   | |     |   |
 |     |\  | |   | |   | |   | ___ |
_____|_| \_|\___/ \___/ \____|_|  _|



smslant:
   _____  ______  __  _________ __
  / __/ |/ / __ \/ / / / ___/ // /
 / _//    / /_/ / /_/ / (_ / _  /
/___/_/|_/\____/\____/\___/_//_/



eftifont:
 ___  _  _  _  _ _  __  _ _
| __|| \| |/ \| | |/ _|| U |
| _| | \\ ( o ) U ( |_n|   |
|___||_|\_|\_/|___|\__/|_n_|



big:
 ______ _   _  ____  _    _  _____ _    _
|  ____| \ | |/ __ \| |  | |/ ____| |  | |
| |__  |  \| | |  | | |  | | |  __| |__| |
|  __| | . ` | |  | | |  | | | |_ |  __  |
| |____| |\  | |__| | |__| | |__| | |  | |
|______|_| \_|\____/ \____/ \_____|_|  |_|




isometric1:
      ___           ___           ___           ___           ___           ___
     /\  \         /\__\         /\  \         /\__\         /\  \         /\__\
    /::\  \       /::|  |       /::\  \       /:/  /        /::\  \       /:/  /
   /:/\:\  \     /:|:|  |      /:/\:\  \     /:/  /        /:/\:\  \     /:/__/
  /::\~\:\  \   /:/|:|  |__   /:/  \:\  \   /:/  /  ___   /:/  \:\  \   /::\  \ ___
 /:/\:\ \:\__\ /:/ |:| /\__\ /:/__/ \:\__\ /:/__/  /\__\ /:/__/_\:\__\ /:/\:\  /\__\
 \:\~\:\ \/__/ \/__|:|/:/  / \:\  \ /:/  / \:\  \ /:/  / \:\  /\ \/__/ \/__\:\/:/  /
  \:\ \:\__\       |:/:/  /   \:\  /:/  /   \:\  /:/  /   \:\ \:\__\        \::/  /
   \:\ \/__/       |::/  /     \:\/:/  /     \:\/:/  /     \:\/:/  /        /:/  /
    \:\__\         /:/  /       \::/  /       \::/  /       \::/  /        /:/  /
     \/__/         \/__/         \/__/         \/__/         \/__/         \/__/


chunky:
 _______ _______ _______ _______ _______ _______
|    ___|    |  |       |   |   |     __|   |   |
|    ___|       |   -   |   |   |    |  |       |
|_______|__|____|_______|_______|_______|___|___|

```

## Installation
Add this dependency your pubspec.yaml file:

```
dependencies:
  enough_ascii_art: ^0.8.0
```
The latest version or `enough_ascii_art` is [![enough_ascii_art version](https://img.shields.io/pub/v/enough_ascii_art.svg)](https://pub.dartlang.org/packages/enough_ascii_art).


## Features and bugs

Please file feature requests and bugs at the [issue tracker][tracker].

[tracker]: https://github.com/Enough-Software/enough_ascii_art/issues

## Run Example
After checking out this project, you can run the example from the root with this command:
```bash
dart ./example/enough_ascii_art_example.dart
```

## Contribute & Known Limitations
Any contributions are welcome!

Known limitations:
* Images are always converted to grayscale
* The FIGlet banners are currently only supported with left-to-right text direction
* The FIGlet banners are not wrapped into multiple lines
* You cannot list all available FIGlet fonts, but instead need to know their names (check out the *lib/src/figlet/fonts* directory!)
* Currently only western style text emoticons are available

Please help removing these limitations!
