# thinking app

{{TOC}}

## intro

I came to think that we need real hypertext to work proficiently and with different level of degrees in the complexity of our thinking.

And I feel that hypertext has not been really implemented so far (I dare not to say it hasn't been explored though, HTML is very good and Xanadu is very beyond).

The best you can get from a native OS app with a file system, is to link from within a text note to another text now — usually using a wiki-style syntax, eg `[[another document]]`.

While this is nice, it shows how much contemporary personal computing has been stuck with the office-paper-folder metaphor: if you don't print it, it does not exists.

Whenever you place a browser to link together different html documents, then one or more parts of the workflow suffer from sup-optimal tool (eg, collaborative writing). Whenever there is an effort to setup a really networked system, you suddenly get the feeling of being drawn back to use other piece of softwares outside that environment and move materials around by copy pasting, duplicating or moving files, and so forth. 

Rather than building an entire workflow in the browser, I wonder if it's not more a matter of channelling one material to multiple outputs (which might not be its final outcome), and moreover, laying the whole workflow foundation upon a networking system that is made to work non-unilaterally, and instead infinitely collaboratively. For example, from an http-based client-server setup, to a dat peer 2 peer based setup.

All this to say that I have never felt my computing experience as really being networked, also when using file-sharing services like dropbox, or solid wiki software like MediaWiki.

What I'm gonna sketch out in the following text, is a note-taking and mind-mapping system, part of a larger experiment in building a wiki on top of the dat protocol.

## web app

This note-taking and mind-mapping app is first of all a web-app: beside the technologies upon which is it built, it makes use of web formats and concepts, such as [...]

Making it an Electron app would be ideal in this case, at least as a first prototype iteration: `node.js` and `choo.js` are the two technologies going to be used to sketch it out, first of all because we need to build a proactive interface for the html pages we work with when using the app, and second because of JSON as a database format (see `plain/text`). This is general can facilitate the output from html back to markdown and other more readable plain/text format (eg YAML), once you store the [AST](https://en.m.wikipedia.org/wiki/Abstract_syntax_tree) of a document. [CommonMark](http://commonmark.org) will take care of Markdown and dealing with AST operations.

## interface

An important design decision is to let a hybrid level of mixed interfaces. Files will still be files, that we drag and drop onto the app from our desktop, or that we will browse through when moving between folders (or... around the one big folder holding everything?). At the same time, the (web) interface will give us affordances to manipulate our objects, build views, etc.

{{ nothing different from fully desktop GUI app, explain }}

The only good example that we got after [The Mother of All Demos](https://en.m.wikipedia.org/wiki/The_Mother_of_All_Demos) is `emacs-org-mode`. Which is only partially able to compete with the above mentioned demo though. The only other attempt, as far as I know, to implement something similar to The Mother of all Demos was [Smalltalk](https://en.m.wikipedia.org/wiki/Smalltalk) — eg, drawing between two elements to create a direct relation between them. A recent example partially implementing this is [Tinderbox](https://en.m.wikipedia.org/wiki/Tinderbox_(application_software)). In this case though, it only works with text. We need also images, pdfs, ebooks, audio files, etc. Examples like the latest iteration of iOS' Notes (since iOS 9) where you can embed finger-made sketches, maps, audio recordings, etc, is really a nice example of what note-taking is all about and the potentialities of adding from different input sources to a new note. The problem arises once you start to get things out of it, beside the fact that the interface of Notes iOS is thought for an 8 yo kid, as friend told me. Imagine being able to add a text comment to a specific section of an audio file, or to leave a note about a particular section of text, or adding a finger-made sketch to a specific clip of a video file, etc.

Things should be able to move from input and output back and forth, while retaining their "real" format, and using a very malleable interface like HTML, to put all this together.

## collections

Taking as an approach [Are.na](https://www.are.na), this note-taking app lets you make `Collections`, where you can mix different materials together. What I'd like to add on top of this, is the chance to make connection also between items within a Collection (or `Block`, in Are.na's language). It is what has already been proposed as [Flat Ontology on Are.na](https://www.are.na/desmond-wong/flat-ontology-arena).

{{ making above section clearer or cut it and leave only Are.na's Flat ontology example }}

## views

A note-taking app should lets you build views of different kind based on different parameters: tags, connections between elements, search terms, date, etc and combine the above in an easy way.

What usually happens though, is that you get a list view / index of all your notes, and a single note view to display the content of each element. You can filter and search, but the view will still display the new list of elements in the same index modality.

It is very unconceivable for me to realise that not many attempts (successful at least) have been made to disentangle a note taking app from the usual paper document paradigm. Why not making it in a way that lets you choose how to see something, what exactly to see and what to filter out? Again, `emacs-org-mode` does this apparently very well. Tinderbox as well. Most other applications get trapped in an idea of paper boundary that prevent them to move beyond a single object view.

Their main limitations though, is that they only work with text — no images, no audio and video, etc.

The mind-mapping part of this app, lets you draw direct connections between items visually, eg by drawing lines, circles, etc for real. These connections are being displayed when viewing a Collection in `spatial-mode` (a better name might come up later — cfr `index-mode`).

An often undervalued option when working with any document, be it a text file, a pdf, or a drawing, is to use a multi-view setup where you open several views of the same file in order to focus on specific areas of it at the same time.

Views on note-taking apps would be extremely useful for so many things, but the main UI is usually the classic three-pane layout adopted by many macOS built-in apps. While this often organise the material you are working with clearly and lets you browse through it decently, it betrays a certain kind of physical-metaphor heritage, wherein things are one-sided and can be seen only in one specific way.

Introducing a `spatial-view` next to a traditional `index-view`, while integrating `multi-view` options to quickly build up tailored UIs, greatly break away from current sub-standardised data-manipulation UI paradigms and would let users decide which level of granularity they need to work with their archive.

## visual connections

Now, something handy to have to quickly start making connections between items, or to make a new collection, is being able to drag items from the list / index view and dropping them in the 'empty' single-item-view pane. Alternatively, you can simply select some itmes and click on the `spatial-view` to have those elements in the spatial view and start dragging them around, drawing connection between them, etc.

A difference from Are.na when working like this, is that if you think of the `space-view` as a canvas (which I think on a technical level it's what might be used in the `html`), you want to be able to sketch out multiple combination of your elements, alas having a `layer` for each arrangement. In Are.na this would not really possible, the closest thing may be creating different collections with the same items, or with some items out of the collection. Or re-arranging the order of the elements in the collection. But there is no way to draw direct connections between those items visually.

## filesystem

As there are all these needs to create multiplicities of connection and thought configuration between elements, the idea of using 'real folders' in the file system is out of discussion (file alias won’t help much either, as there is no original position).

Therefore, as I care also to let users browse their notes through the file system, the only thing that can work (at least so far), is to get rid of the hierarchical folder structure and put everything in one folder. Then use a JSON file as a database to store the states of each item.

## html

I think I am getting more and more ok in thinking that an `html` document is actually the best way to store notes. To do this though, each document should be self-embeddable and zero-dependant (I don't know what I am saying): somehow make it possible not to have broken links. Which means, you can base64 images (easily I think). Not sure you can do the same with video or audio files though. So what's the deal with that? `epub` has been developed to resolve this problem of asset dependancy, but it failed because it does not support all html and css and js code. Saving a webpage as web-archive would solve this?

Apple Safari has its own archive format called [webarchive](https://en.m.wikipedia.org/wiki/Webarchive), it’s proprietary; Mozilla Firefox has its own as well, called [MAFF](https://en.m.wikipedia.org/wiki/Mozilla_Archive_Format) — apparently not working anymore as of 2017; Google Chrome uses the data URI scheme to package everything in [a single .html file](https://chrome.google.com/webstore/detail/singlefile/mpiodijhokgodhhofbcjdecpffjipkle) (instead of a `.webarchive`); there is the [MHTML](https://en.m.wikipedia.org/wiki/MHTML) archive format, developed originally my Microsoft and in use to produce HTML emails and the [Web ARChive](https://en.m.wikipedia.org/wiki/Web_ARChive), developed by the Internet Archive non-profit organisation.

## sharing

Another approach to sharing a note composed of different material is to run the whole library on / as a `dat` archive. On a normal level your note collection is private. Once you want to share one note with someone else, upon link creation, the app checks for all the material composing that note (eg, all the `transclusion`-syntax links), and turn those items shareable as well.

This only works if you share a note as a dat-link of course, if you share a copy of the single `.md` or `.html` file to someone, then it would still work if they have access to the internet and can fetch the rest of the material upon file opening, otherwise what they probably would see is a placeholder.

As sketched out before, self-embeddable html files, or some web-archive format that upon opening would unzip all the files building up a note and would put them in place in your library would be another way to approach this.

I still find it problematic though, the fact of sharing a note as an html file and therefore not letting the receiver modify and comment it. A nice option would be to let open html documents as markdown files. I wonder how difficult and edge-case it might be. Technically, you only care about the html tag structure, so after converting everything to plain text, you would replace html tags into markdown syntax, and that's it. Pretty sure it might not be so easy though. Put some pandoc in there. If there's something I care, is data conversion and reconversion and being able to shape it in innumerable ways to get only what you need.

## structure

- list view
- spatial view
 - draw connection between objects by drawing lines between them, circling over them, selecting and press buttons
- every element is an object, eg: a text note, a drawing, an image, a map, etc
- to embed rich media on a plain text file, we use iA Writer’s [transclusion syntax](https://github.com/iainc/Markdown-Content-Blocks): `/name-of-file.ext`
- there is no editing and previewing panels? (could be a bad idea though)
- the database is a `json` file, which is mostly useful for searching, storing each object’s state (eg. connection with other objects) and filtering data, still each object stays on its own as a file in a big folder holding everything
- tags exists as inline `#tag` in a text note, and as field for images, audio and video files, etc
- are.na’s buckets exist in the form of filters and objects’s connection? translating this into the form of folders would fail pretty soon, so either we can use smart folders (cfr filters), or some sort of connection mechanism (maybe not only by drawing / connecting objects but also by the above inline `#tag` option