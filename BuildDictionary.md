

# Getting data files onto your computer #

You can get some data files from these places:

  * [Chemnitz German-English](http://ftp.tu-chemnitz.de/pub/Local/urz/ding/de-en-devel/) (GNU license)
  * [www.dicts.info](http://www.dicts.info/uddl.php) (tab\_delimited format--note that you only need to download the file in one direction, for exampe EN=>ES or ES=>EN, but not both).
  * [DictCC](http://www1.dict.cc/translation_file_request.php) (English and German to many other languages, copy restricted)
  * Any other new-line delimited text file in either of the formats:
    * `language1[tab]language2`  (tab\_delimited format)
    * `language1 :: language2`   (chemnitz format)

Example command to download and unzip chemnitz dictionary:
```
curl --remote-name http://ftp.tu-chemnitz.de/pub/Local/urz/ding/de-en-devel/de-en.txt.gz
gunzip de-en.txt.gz
```

You can combine as many input data files as you like into a single QuickDic file.

You can also use data from [en.wiktionary.org](http://dumps.wikimedia.org/enwiktionary/), but processing of this data is significantly more complex.  To do this, you need to download the QuickDic source code.

# Download the builder Java application #

Save the [DictionaryBuilder.jar](http://dictionarypc.quickdic-dictionary.googlecode.com/git/custom_dictionary/DictionaryBuilder.jar) to your computer.

One quick way to do this is to run:

```
curl --remote-name http://dictionarypc.quickdic-dictionary.googlecode.com/git/custom_dictionary/DictionaryBuilder.jar
```

Note that you'll need a Java runtime environment to run it.  To check if you have one, try opening a command window and typing:

```
java -version
```


# Building the dictionary file #

Open a command window and run these commands from the directory that contains `DictionaryBuilder.jar`.

```

# Make an English stoplist file (optional).
# The stoplist is a list of very common words that aren't very informative and shouldn't be indexed.
# For example, if there's an entry like:
# Weltkarte :: map of the world
# then this entry would be filed under "map" and "world", but not under "of" and "the" (if those words are in the stoplist.
echo "a" >> EN_stoplist.txt
echo "and" >> EN_stoplist.txt
echo "the" >> EN_stoplist.txt
echo "of" >> EN_stoplist.txt

# Make an Spanish stoplist file (optional).
echo "y" >> ES_stoplist.txt

# Build the dictionary.
java -Xmx512m -jar DictionaryBuilder.jar \
  --dictOut=MyDictionary_EN-ES.quickdic \
  --lang1=EN \
  --lang2=ES \
  --lang1Stoplist=EN_stoplist.txt \
  --lang2Stoplist=ES_stoplist.txt \
  --dictInfo="I created this dictionary all by myself." \
  --input1=EN-ES_dicts.info_wiktionary.txt \
  --input1Name="EN-ES_dicts.info_wiktionary.txt" \
  --input1Charset=UTF8 \
  --input1Format=tab_separated \
  --input1FlipColumns=false \
  --input2=EN-ES_dicts.info_omegawiki.txt \
  --input2Name="EN-ES_dicts.info_omegawiki.txt" \
  --input2Charset=UTF8 \
  --input2Format=tab_separated \
  --input2FlipColumns=false

# Another example:
java -Xmx512m -jar DictionaryBuilder.jar \
  --dictOut=IT-TR.quickdic \
  --lang1=IT \
  --lang2=TR \
  --dictInfo=it-tr_dictcc_simulated \
  --input1=it-tr_dictcc.txt \
  --input1Name=dictcc \
  --input1Charset=UTF8 \
  --input1Format=tab_separated

```

You should now have a file in the current directory called `MyDictionary_EN-ES.quickdic`.

## Extra notes ##

inputNCharset should usually be "UTF8", but if weird things happen to your special characters, try "latin1".

inputNFormat should be "tab\_separated" or "chemnitz" (chemnitz uses "::" and "|" as separators).

inputNFlipColumns tells the indexer that your text file has lang2 in the first column and lang1 in the second column (opposite the expected ordering based on the --lang1 and --lang2 flags).  So if you download an ES->EN text file, you should either use (--lang1=ES --lang2=EN --inputNFlipColumns=false) or (--lang1=EN --lang2=ES --inputNFlipColumns=true).

QuickDic builds indices in both directions from the same text file.  So if you download a EN->ES text file from somewhere, you'll get both EN->ES and ES->EN indices.

# Putting the dictionary on your device #

The fastest way to do this is over USB with adb (part of the [Android SDK](http://developer.android.com/sdk/index.html)).
```
adb push MyDictionary_EN-ES.quickdic /sdcard/quickDic
```

You can also copy the `MyDictionary_EN-ES.quickdic` file from your computer to the `quickDic` folder on your device's SD card.

Next time you start QuickDic, it should automatically find any new dictionaries you've copied to the dictionary folder.

# Troubleshooting #

Feel free to contact me: thad.hughes@gmail.com.


### TODO: Write section describing how to parse enwiktionary data ###