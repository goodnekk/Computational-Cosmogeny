# format

## web app
This note-taking and mind-mapping app is first of all a web-app: beside the technologies upon which is it built, it makes use of web formats and concepts, such as [...]

Making it an Electron app would be ideal in this case, at least as a first prototype iteration: `node.js` and `choo.js` are the two technologies going to be used to sketch it out, first of all because we need to build a proactive interface for the html pages we work with when using the app, and second because of JSON as a database format (see `plain/text`). This is general can facilitate the output from html back to markdown and other more readable plain/text format (eg YAML), once you store the [AST](https://en.m.wikipedia.org/wiki/Abstract_syntax_tree) of a document. [CommonMark](http://commonmark.org) will take care of Markdown and dealing with AST operations.


## html
I think I am getting more and more ok in thinking that an `html` document is actually the best way to store notes. To do this though, each document should be self-embeddable and zero-dependant (I don't know what I am saying): somehow make it possible not to have broken links. Which means, you can base64 images (easily I think). Not sure you can do the same with video or audio files though. So what's the deal with that? `epub` has been developed to resolve this problem of asset dependancy, but it failed because it does not support all html and css and js code. Saving a webpage as web-archive would solve this?

Apple Safari has its own archive format called [webarchive](https://en.m.wikipedia.org/wiki/Webarchive), it’s proprietary; Mozilla Firefox has its own as well, called [MAFF](https://en.m.wikipedia.org/wiki/Mozilla_Archive_Format) — apparently not working anymore as of 2017; Google Chrome uses the data URI scheme to package everything in [a single .html file](https://chrome.google.com/webstore/detail/singlefile/mpiodijhokgodhhofbcjdecpffjipkle) (instead of a `.webarchive`); there is the [MHTML](https://en.m.wikipedia.org/wiki/MHTML) archive format, developed originally my Microsoft and in use to produce HTML emails and the [Web ARChive](https://en.m.wikipedia.org/wiki/Web_ARChive), developed by the Internet Archive non-profit organisation.
