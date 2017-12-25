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
