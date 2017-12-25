## structure
The notion of structure is applicable and debatable in a lot of domains
[architecture](https://www.archdaily.com/610531/frei-otto-and-the-importance-of-experimentation-in-architecture) [cosmology](https://en.wikipedia.org/wiki/List_of_largest_cosmic_structures)
[physics](https://leanderherzog.ch/higgsboson/)
[governance](http://www.jofreeman.com/joreen/tyranny.htm)
[holarchy](https://en.wikipedia.org/wiki/Holarchy)
[urbanism](http://en.bp.ntu.edu.tw/wp-content/uploads/2011/12/06-Alexander-A-city-is-not-a-tree.pdf)).
[ecology]()

Mathmatics can be seen as the study of [structure](https://en.wikipedia.org/wiki/Mathematical_structure) in the formal sense.
Structure has usefull primitives such as: order, measure, metric, geometry and topology.

- list view
- spatial view
 - draw connection between objects by drawing lines between them, circling over them, selecting and press buttons
- every element is an object, eg: a text note, a drawing, an image, a map, etc
- to embed rich media on a plain text file, we use iA Writer’s [transclusion syntax](https://github.com/iainc/Markdown-Content-Blocks): `/name-of-file.ext`
- there is no editing and previewing panels? (could be a bad idea though)
- the database is a `json` file, which is mostly useful for searching, storing each object’s state (eg. connection with other objects) and filtering data, still each object stays on its own as a file in a big folder holding everything
- tags exists as inline `#tag` in a text note, and as field for images, audio and video files, etc
- are.na’s buckets exist in the form of filters and objects’s connection? translating this into the form of folders would fail pretty soon, so either we can use smart folders (cfr filters), or some sort of connection mechanism (maybe not only by drawing / connecting objects but also by the above inline `#tag` option

## collections
Taking as an approach [Are.na](https://www.are.na), this note-taking app lets you make `Collections`, where you can mix different materials together. What I'd like to add on top of this, is the chance to make connection also between items within a Collection (or `Block`, in Are.na's language). It is what has already been proposed as [Flat Ontology on Are.na](https://www.are.na/desmond-wong/flat-ontology-arena).

{{ making above section clearer or cut it and leave only Are.na's Flat ontology example }}

## filesystem
As there are all these needs to create multiplicities of connection and thought configuration between elements, the idea of using 'real folders' in the file system is out of discussion (file alias won’t help much either, as there is no original position).

Therefore, as I care also to let users browse their notes through the file system, the only thing that can work (at least so far), is to get rid of the hierarchical folder structure and put everything in one folder. Then use a JSON file as a database to store the states of each item.

My suggestion would be to separate storage from structure. You could store every element in an unstructured storage (similar to `random access memory`). Then all the indexing, lists, collections and hierarchies are stored separately.
