QuickDic parses data from [wiktionary.org](http://wiktionary.org) and [Beolingus](http://dict.tu-chemnitz.de/) to generate dictionary files that can be used offline on Android devices.  I made QuickDic for myself because I wanted to read more easily in German, and later to learn Italian, and it's been fun to expand it to other languages.

You can download the [current signed APK](http://dictionary.quickdic-dictionary.googlecode.com/git/Dictionary_signed.apk) directly, or find it  [QuickDic on Google Play](https://play.google.com/store/apps/details?id=com.hughes.android.dictionary)!

QuickDic currently has built-in dictionaries for many language pairs (some much more complete than others, your mileage may vary!).  I also recently added single-language dictionaries for English, German, Italian, and French, but these are likely to be lower quality.

Here are some of the languages QuickDic has dictionaries for:

Afrikaans, Albanian, Ancient Greek, Arabic, Armenian, Azeri, Basque, Belarusian, Bengali, Bosnian, Breton, Bulgarian, Burmese, Burmese, Cantonese, Catalan, Chinese|Mandarin, Croatian, Czech, Danish, Dutch, English, Esperanto, Estonian, Faroese, Finnish, French, Gaelic, Galician, Georgian, German, Greek, Haitian Creole, Hawaiian, Hebrew, Hindi, Hungarian, Icelandic, Indonesian, Irish, Italian, Japanese, Korean, Kurdish, Lao, Latin, Latvian, Lithuanian, Luxembourgish, Macedonian, Malay, Malayalam, Maori, Mongolian, Nepali, Norwegian, Persian, Polish, Portuguese, Punjabi, Romanian, Russian, Sanskrit, Serbian, Slovak, Slovene|Slovenian, Somali, Spanish, Swahili, Swedish, Tagalog, Tajik, Tamil, Thai, Tibetan, Turkish, Ukrainian, Urdu, Vietnamese, Welsh, Yiddish, Zulu

[This file](http://code.google.com/p/quickdic-dictionary/source/browse/res/raw/dictionary_info.txt?repo=dictionary) lists all the built-in dictionaries that you can download and use with QuickDic.

## Helping out ##

QuickDic is open source and I'd love to have help!  One thing that would be really great is if you can translate the strings into other languages.  For the most part, they're here:

  * http://code.google.com/p/quickdic-dictionary/source/browse/res/values/strings.xml?repo=dictionary
  * http://code.google.com/p/quickdic-dictionary/source/browse/res/values/languages.xml?repo=dictionary
  * http://code.google.com/p/quickdic-dictionary/source/browse/res/values/arrays.xml?repo=dictionary
  * http://code.google.com/p/quickdic-dictionary/source/browse/res/raw/help.html?repo=dictionary


## Custom dictionaries ##

You can also generate your own dictionaries for use offline, using data sources such as [dict.cc](http://www.dict.cc/)  (whose copyright prevents distribution along with the dictionary).

See the [instructions for building a custom dictionary](BuildDictionary.md).

## Getting the source code ##

I'd love to have some help, especially with things like making the UI prettier, translating the UI to other languages, and generating new dictionaries.

See the [instructions for getting the source code](UsingSourceCode.md).