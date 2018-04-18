# thinking app

{{ name will be changed? }}

## preface

This text serves as an introduction and overview to the project. See each subfolders for more extended and messy notes with other materials complementing them.

Also: as of 2018-03-30 we are still re-organising this repo, so... you know it.

## intro

We came to think that we need a general system for creating information structures to work proficiently and with different levels of degree in the complexity of our thinking. We came to realise that a lot of software tries to solve the same problem over and over again: organising information in different (collaborative) structures, transforming that information, and viewing that information in different ways. This abstract description encompasses anything from filesystemes, hypertext, excell, productivity and mind-mapping tools.

This kind of activity is usually done by people called "programmers", but we think anyone should be able to deal with these more abstract structures. That's why we talk about "computation": the system should hold a middle ground between a programming language and a program. The system is not so much an "app" as more an open "environment". It should be expressive enough to allow a user to bend, adapt and extend the system to their own needs, but also opiniated enough to allow a novel user to use it easily.


What we’re gonna sketch out in the following text, is a note-taking and mind-mapping system, part of a larger experiment in building (a computational engine??).

## Existing systems

In this section we analyse existing attempts. We disuss their limits and good parts.

### hypertext

The best you can get from a native OS app with a file system, is to link from within a text note to another text — usually using a wiki-style syntax, eg `[[another document]]`.

{{While this is nice, it shows how much contemporary personal computing has been stuck with the office-paper-folder metaphor: if you don't print it, it does not exists.}}{{ ?? }}

Whenever you place a browser to link together different html documents, then one or more parts of the workflow suffer from sup-optimal tool (eg, collaborative writing). Whenever there is an effort to setup a really networked system, you suddenly get the feeling of being drawn back to use other piece of software outside of that environment; moving materials around by copy pasting; duplicating or moving files; and so forth.

### Networking and filesharing

Rather than building an entire workflow in the browser, we wonder how to set hybrid setups, where what we are working on can be manipulated and reviewed through different applications and interfaces. Moreover, we really want to lay the whole workflow foundation upon a networking system that is made to work non-unilaterally, and instead infinitely collaboratively. Peer-to-peer protocols are evolving fastly enough that it’s possible to ditch the central server that-sync-that-latest-state for all users working on the same doc altogether.

All this to say that we have never felt our computing experience as really being networked, also when using file-sharing services like Dropbox, or solid wiki software like MediaWiki. There is always a feeling that your are renting an office, or paying for an office, and the moment when you setup a LAN network everybody is like “this is not the internet!”. Exactly! It’s not, it’s the web. Big difference. It’s not capitalised. Please don’t bring up the Declaration of Independence of the Cyberspace either.

Another approach to sharing a note composed of different material is to run the whole library on / as a `dat` archive. On a normal level your note collection is private. Once you want to share one note with someone else, upon link creation, the app checks for all the material composing that note (eg, all the `transclusion`-syntax links), and turn those items shareable as well.

{{This only works if you share a note as a dat-link of course, if you share a copy of the single `.md` or `.html` file to someone, then it would still work if they have access to the internet and can fetch the rest of the material upon file opening, otherwise what they probably would see is a placeholder?}}{{ revise, a bit unsure where it wants to go }}

### Note taking systems

~~The only good example that we got after [The Mother of All Demos](https://en.m.wikipedia.org/wiki/The_Mother_of_All_Demos) is `emacs-org-mode`. Which is only partially able to compete with the above mentioned demo though. The only other attempt, as far as I know, to implement something similar to The Mother of all Demos was [Smalltalk](https://en.m.wikipedia.org/wiki/Smalltalk) — eg, drawing between two elements to create a direct relation between them. A recent example partially implementing this is [Tinderbox](https://en.m.wikipedia.org/wiki/Tinderbox_(application_software)). In this case though, it only works with text. We need also images, pdfs, ebooks, audio files, etc.~~

{{mg: This is all rather uninformed, smalltalk is not about "drawing connections", and saying that tinderbox "only uses text" is both not true, and completely beside the point. We should discuss and analyse here more the good ideas in these projects rather than flatly dissmiss them}}

Examples like the latest iteration of iOS' Notes (since iOS 9) where you can embed finger-made sketches, maps, audio recordings, etc, is really a nice example of what note-taking is all about and the potentialities of adding from different input sources to a new note. The problem arises once you start to get things out of it — beside the fact that the interface of Notes iOS is thought for an 8 yo kid, as a friend told me. Imagine being able to add a text comment to a specific section of an audio file, or to leave a note about a particular section of text, or adding a finger-made sketch to a specific clip of a video file, etc. That is the kind of workflow that we aim for.

### collections

Taking as an approach [Are.na](https://www.are.na), this note-taking app lets you make `Collections`, where you can mix different materials together. What we’d like to add on top of this, is the chance to make connection also between items within a Collection (or `Block`, in Are.na's language). It is what has already been proposed as [Flat Ontology on Are.na itself](https://www.are.na/desmond-wong/flat-ontology-arena).

### html

`html` documents are actually the best way to store notes. As in, a finished, presentational, and collaborative format from which other users can start work on by converting them into markdown files, or by adding them in their app library and go in edit mode (eg drawing connection, adding images or other files).

{{To do this though, each document should be self-embeddable and zero-dependant (I don't know what I am saying): somehow make it possible not to have broken links. Which means, you can base64 images (easily I think). Not sure you can do the same with video or audio files though. So what's the deal with that? `epub` has been developed to resolve this problem of asset dependancy, but it failed because it does not support all html and css and js (new) features. Would saving a webpage as web-archive solve this?

Apple Safari has its own archive format called [webarchive](https://en.m.wikipedia.org/wiki/Webarchive), it’s proprietary; Mozilla Firefox has its own as well, called [MAFF](https://en.m.wikipedia.org/wiki/Mozilla_Archive_Format) — apparently not working anymore as of 2017; Google Chrome uses the data URI scheme to package everything in [a single .html file](https://chrome.google.com/webstore/detail/singlefile/mpiodijhokgodhhofbcjdecpffjipkle) (instead of a `.webarchive`); there is the [MHTML](https://en.m.wikipedia.org/wiki/MHTML) archive format, developed originally my Microsoft and in use to produce HTML emails and the [Web ARChive](https://en.m.wikipedia.org/wiki/Web_ARChive), developed by the Internet Archive non-profit organisation.}}{{ this whole part if kinda interesting, but I think the next section is the approach I’m leaning towards more }}

{{As sketched out before, self-embeddable html files, or some web-archive format that upon opening would unzip all the files building up a note and put them in place in your library would be another way to approach this.}}{{ integrate this bit? }}


We still find it problematic though, the fact of sharing a note as an html file and therefore not letting the receiver modify and comment it. A nice option would be to let open html documents as markdown files. We wonder how difficult and edge-case it might be. Technically, you only care about the html tag structure, so after converting everything to plain text, you would replace html tags into markdown syntax, and that's it. Pretty sure it might not be so easy though. Put some pandoc in there. If there's something we care, is data conversion and reconversion and being able to shape it in innumerable ways to get only what you need. {{The problem is mainly that html is not `isomorphic` to markdown. Markdown only represents a subset of html. Of course, there are tools that attempt to extract plain text from websites, `instapaper` does this.}}

## interface

An important design decision is to let a hybrid level of mixed interfaces. Files will still be files, that we drag and drop onto the app from our desktop, or that we will browse through when moving between folders (or... around the one big folder holding everything?). At the same time, the (web) interface will give us affordances to manipulate our objects, build views, etc.

{{ nothing different from fully desktop GUI app, explain }}

Things should be able to move from input and output back and forth, while retaining their "real" format. Using a very malleable interface like HTML, we can put most of this together.

Still, for certain features, we cannot do much but ask / wait for web browsers to implement particular features.

### escaping the paper metaphor (views)

A lot of `desktop publishing` applications are built on the `skeuomorphic` idea of paper as a metaphor. We call this idea `magical paper`, because the idea is to invoke a form of `magical power` over the elements on the screen. It is very unconceivable for us to realise that not many attempts (successful at least) have been made to disentangle note taking from this paper document paradigm. Why not making it in a way that lets you choose how to see something, what exactly to see and what to filter out? Again, `emacs-org-mode` does this apparently very well. Most other applications get trapped in an idea of paper boundary that prevent them to move beyond a single object view.

An often undervalued option when working with any document is to use a multi-view setup where you open several views of the same file in order to focus on specific areas of it at the same time. The main UI in note taking apps is usually the classic three-pane layout adopted by many macOS built-in apps. While this often organises the material you are working with clearly and lets you browse through it decently, it betrays a certain kind of physical-metaphor heritage, wherein things are one-sided and can be seen only in a specific way.

A note-taking app should let you build views of different kind based on different parameters: tags, connections between elements, search terms, date, etc and combine the above in an usable way.

We propose a system of layered abstractions based on this `magical paper` metaphor where elements can change their "physical" properties in time.
* `magical ink` (classic word processor): The screen represents a piece of paper, the elements or ink can change in time.
* `magical paper` (websites): The screen a pieces of paper, the paper can move and change in time. Patterns of ink can change in time (stylesheets, filters).
* `magical space`: The screen represents a space with pieces of paper (views). Patterns of paper can change in time.

#### escaping the clipboard

The clipboard is one of the most powerfull yet poor points of interacting with current systems. It's comparable to picking up an object and putting it back down somewhere else. The clipboard allows us to restructure documents, copy elements and apply transformations on them, and move content between programs. All these actions could be improved significantly.

- Visible state: the current clipboard doesn't visibly show what is 'on' it, nor is it possible to keep multiple elements on the board. Why not have an inventory type system, that is used in a lot of rpg- type games?

- Allow transclusion, i.e. pointers, not only deep copies.

- Alllow data to flow between environments, (piping).

### visual connections

Introducing a `spatial-view` next to a traditional `index-view`, while integrating `multi-view` options to quickly build up tailored arrangements, greatly break away from current sub-standardised data-manipulation UI paradigms and would let users decide which level of granularity they need to work with their archives.

The mind-mapping part of this app, lets you draw direct connections between items visually, eg by drawing lines, circles, etc for real. These connections are being displayed when viewing a Collection in `spatial-mode` (a better name might come up later — cfr `index-mode`).

{{Now, something handy to have to quickly start making connections between items, or to make a new collection, is being able to drag items from the list / index view and dropping them in the 'empty' single-item-view pane. Alternatively, you can simply select some items and click on the `spatial-view` to have those elements in the spatial view and start dragging them around, drawing connection between them, etc.}}{{ rewrite, confused }}

A difference from Are.na when working like this, is that if you think of the `space-view` as a canvas, you want to be able to sketch out multiple combinations of your elements, alas having a `layer` for each arrangement. In Are.na this would not really be possible, the closest thing may be creating different collections with the same items, or with some items out of the collection. Or re-arranging the order of the elements in the collection. But there is no way to draw direct connections between those items visually.

Computers make relations by storing `symbolic representations`. Humans can visually process relations by `gestalt`. The system should support parsing implicit relations between elements that are for example close to each other.

{{What we want to implement here, is the option to have multiple files arrangements in a collection — in terms of connections, tagging, ordering, placing, etc — and keep each of these layers as a separate entry. This allows to have different combinations and share specifically one with some other users, without having to delete, or make a clone of the same files as a backup.}}{{ write better, are.na works like this but the interaction is tedious and feels more for contemplation of your blocks rather than by moving them around, connecting them in one go, etc }}


## structure

### distinctions

We propse a symbolic system for representing information structures based on `distinctions` and `composable behaviours`. The system recursively implements more advanced structures in itself. This gives a hierarchy of structures:

- distinctions
    - values, numbers, text
- distinctions of distinctions
    - group (unordered, multiple)
    - set (unordered, unique)
    - ordered-set (ordered, unique)
    - list (ordered, multiple)
    - tuple (orderd, unique, bounded)
- distinctions of distinctions of distinctions:
    - trees
    - semi-lattice, rhizome, graphs, networks
    - maps, structs, objects, tagging
- distinctions of distinctions of distinctions of distinctions:
    - matrix, grid, table
    - classes, inheritence
    - [patterns](http://web.utah.edu/stat/tom/tpwc.html)

### transformations

The user builds, or grows information structures by applying transformations to them. These transformations are an important part of the interface, because they replace our usual ways of interacting with the computer (i.e. the clipboard).

We are strong beleivers in [Gall's law](https://en.wikipedia.org/wiki/John_Gall_(author)#Gall's_law). This means the system should allow for what Alexander has [called](http://makingpermaculturestronger.net/christopher-alexanders-neglected-challenge-to-permaculture/) `Unfolding Wholeness` or `structure preserving transformations`. This is directly contrary to what we would normally do in programming; laying out a structure top-down as architecture. We beleive the system should support both ways of structuring activity, allowing the user to `think in both ways`.

### values

Values are stored not as computer-based types (int, float, string, etc) but as `distinctions` in a `dimension`. For example a date marks a certain period(not a point) in the continuous dimension time. A name is a distinctions in a discrete nominal dimension. This means the system implements conversions between formats for you.

### mappings, processes, functions

Lastly, actual computation is done in the form of mappings. Mappings transform structures into other structures by combining, transforming, filtering and reducing them. This is how we can begin to make views, because views are just mappings of symbolic structures onto visual structures.

For example, We can implement a spatial view by taking a list and augmenting it with positional information (x,y coördinates).

We can implement a stylesheet, by taking a document tree, and augmenting it with style information.

Information is loosly coupled (separation of concerns), and [subject oriented](https://en.wikipedia.org/wiki/Subject-oriented_programming). This makes it very easy to make multiple alternative views of the same information from different perspectives.

Mappings are themselves just structures, which means that mappings can recuresively map mappings. These become processes in time.
