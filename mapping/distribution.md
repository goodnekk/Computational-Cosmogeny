## distribution

Distribution is the problem of having the physical data somewhere else than the machine you're working on, and creating abstractions that let you ignore that fact.

Another approach to sharing a note composed of different material is to run the whole library on / as a `dat` archive. On a normal level your note collection is private. Once you want to share one note with someone else, upon link creation, the app checks for all the material composing that note (eg, all the `transclusion`-syntax links), and turn those items shareable as well.

This only works if you share a note as a dat-link of course, if you share a copy of the single `.md` or `.html` file to someone, then it would still work if they have access to the internet and can fetch the rest of the material upon file opening, otherwise what they probably would see is a placeholder.

As sketched out before, self-embeddable html files, or some web-archive format that upon opening would unzip all the files building up a note and would put them in place in your library would be another way to approach this.

I still find it problematic though, the fact of sharing a note as an html file and therefore not letting the receiver modify and comment it. A nice option would be to let open html documents as markdown files. I wonder how difficult and edge-case it might be. Technically, you only care about the html tag structure, so after converting everything to plain text, you would replace html tags into markdown syntax, and that's it. Pretty sure it might not be so easy though. Put some pandoc in there. If there's something I care, is data conversion and reconversion and being able to shape it in innumerable ways to get only what you need.
