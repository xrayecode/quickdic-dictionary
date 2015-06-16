# Getting the source code #

There are several Eclipse projects containing the source code.  To get them all, you'll need to run these commands on your shell.  These can be run in any

```

# You can name this whatever you want.
mkdir quickdic
cd quickdic

# Java utilies used in the code:
git clone https://code.google.com/p/quickdic-dictionary.util/ Util

# A copy of ActionBarSherlock:
git clone https://code.google.com/p/quickdic-dictionary.actionbarsherlock/ JakeWharton-ActionBarSherlock

# The Android application.  This and Util is all you need if you want to work on the UI.
git clone https://code.google.com/p/quickdic-dictionary.dictionary/ Dictionary

# The desktop-based code used to produce dictionary files.
git clone https://code.google.com/p/quickdic-dictionary.dictionarypc/ DictionaryPC

```


# Setting up Eclipse projects #

First, make sure you've installed the Android SDK and Eclipse plugin.

You need to set up several Eclipse projects (in this order, because there are dependencies between them):

  1. A Java project named "Util" pointing at the code in: quickdic/Util
  1. An Android project named "actionbarsherlock" pointing at the code in: quickdic/JakeWharton-ActionBarSherlock/actionbarsherlock
  1. An Android project named "Dictionary" pointing at the code in: quickdic/Dictionary
  1. A Java project named "DictionaryPC" pointing at the code in: quickdic/DictionaryPC

Once you get those compiling, you're ready for the next step.

# Downloading the input files #

```

```

# Splitting enwiktionary #

# Running the JUnit tests #

# Troubleshooting #

Feel free to contact me: thad.hughes@gmail.com.