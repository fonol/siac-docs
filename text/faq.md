# Frequently asked questions

## Does the add-on need an internet connection?
It works completely offline, with the small exception that Youtube videos can be opened only with a working internet connection.

## My screen is too small for the add-on
There are some settings you could try out: First, you could increase the right column's size by modifying Left Side Width,
if that's not enough, you could modify the Zoom setting to some value < 1.0, which will simply scale everything on the right side down a bit.

## When I open the add dialog for the first time, index creation takes too long.
There is not much I can do about that, performance depends on your machine and the size of your collection. You can always exclude decks in the config file to reduce the index size.

## My searches take too long
As stated elsewhere, search time depends on lots of factors, but the most determining one's are: Collection size, type of index used.  
I always get the fastest results with SQLite FTS version 5. You can check your version in the Info dialog. If you are using FTS 3, queries are much slower. I suggest trying to update your system's SQLite installation with one that comes compiled with FTS 5 support if possible. As for collection size, you can choose to limit the decks that go into the index, see the decks config option. And make sure you use a stopwords list for your language, as explained in the second paragraph.

## A note in the results seems to be displayed incorrectly (text flows out of the card).
Some notes might contain html that breaks the container into which they are rendered. I try to catch these cases, but if you stumble upon such a note, please open an issue in the github repo with the note text.

## Sometimes a search is not triggered when selecting
The search is triggered when the mouse up happens inside (!) the note (or field input). So if you mark some text, and leave the note area before
releasing the mouse, nothing happens.

## Some part of the add-on layout is cut-off
The layout tries to make everything visible on every screen size, but if you have problems (typical ex. would be that the add-on UI covers some part of the editor buttons), it could be that its another add-on modifying the editor UI, e.g. an add-on adding an additional row below the editor buttons or stuff like that.

## I have a note with lots of text, and typing seems to lag at some point
Typing typically lags when the results are rendered. My advice would be to either increase the delayWhileTyping config value, which determines how long to wait after the user has stopped typing (I am a slow typer and have mine set to 1500ms atm), so searches aren't triggered too soon while typing, or to uncheck search while typing and use only the FIELDS button to search for your current input.

## What is this Performance stat?
I wanted to have a stat that includes not only the pass rate of a note's cards, but also how long I took on average to answer these cards.
So I simply came up with a crude formula that calculates a score (1-100) out of the pass rate and avg. time taken. I am open to suggestions about better stats to display there instead, so if you have any ideas, let me know.

## How are the keywords determined?
The keywords are not really determined in a sophisticated way, it's just the words that appear most often in the top n results (n = 20 atm) , minus any stopwords.

## How do I add a PDF?
Click on Notes -> Create -> PDF. Or use Ctrl+Shift+N. In general, all notes are treated as PDF if their Source is a path to a file ending with .pdf.

## How do I add a Youtube video?
Open the Create Note dialog and paste the URL of the video into the source field. It will be opened as an embedded video then. Please note that not all Youtube uploaders allow embedding their videos on other sites, so in some cases, it might not work.

## What if I move a PDF file while a note is linked to it?
If you moved the file, nothing really should happen except you cannot open the PDF anymore (because the path in source is now incorrect).
Reading progress and marks are linked with the ID of the note, so if you change the source of the note to again contain the correct path, everything should be fine.

## What is the "Queue"?
The queue can be used to kind of schedule your reading, by taking the first item out of it (typically a pdf note or a note containing some pasted article from the web), reading some part, creating notes while doing so, then moving it somewhere back in the queue. This might not be fitting for everyone's workflow, but I am quite happy with it.

## Pasted Text from a PDF looks weird
Since some of the latest versions, Anki keeps formatting in pasted text. So your pasted text might contain the dark background of the PDF viewer and similar stuff. I don't exactly know about Mac/Linux, but on Windows, you can paste with Ctrl+Shift+V, which pastes the plain text.
