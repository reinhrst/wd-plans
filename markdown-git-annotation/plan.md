## Markdown git annotation

Markdown allows people to quickly create documents with a limited amount of formatting.
This has many advantages over creating documents in Word:

- No "hidden" formatting in the documents (e.g. in Word documents people may be tempted to use crazy fonts etc). This means it's much easier to lay out the document into the format you want later (e.g. typesetting for a certain academic journal; typesetting documents from multiple authors into the same format; different post-processing that e.g. fix intra-document references; use on different formats (screen-readers, phone-screens, ebooks, ...); etc).
- At the same time, text reads like it should
- Codes are relatively easy to learn (unlike something like LaTeX)
- Many plugins available to add diagrams (e.g. mermaid) and other things
- Clear source-driven generation of the document from the code; e.g. something like R-markdown allows insertion of _R_-code, which gets executed and rendered into (e.g.) graphs that get inputted into the final document (Jupyter-notebook like).
- Clear-text input, meaning that you can use tools like git(hub) for source control.
- No vendor-lock

Over the past I've been trying to use Markdown for most of my own text-generation efforts, and trying to convince others to do the same.
The things I ran into:

- Easy format is easy, however we're spoiled with Word / etc and we're used to having full control of layout.
- Sharing documents in PDF means that recipient has to make comments on PDF (rather than "track changes" in word)
- Alternative is to give someone source code (or access to git(hub)). Making changes this way will only work if people (both reviewer and reviewee) are happy commenting on source code / through github tools.

---

Idea is to make a website where people can host their Markdown (html) files.
This website syncs with github (and others), to show (the latest version / a version selection box / all tagged versions / etc).
Github --> HTML can go through standard markdown renderes, or custom methods (github actions?).
After document is uploaded on website, owner can send out invites to reviewers.
Reviewers can edit document on website, with familiar word-like "track-changes" and "add comment" interfaces.
All changes and comments are made into pull request / issues (or do we need something else?) in github. This means that website needs to be able to map the text in the HTML document into the text in the Markdown document (this should not be too hard in 99% of cases; if problematic in some cases, something like javascript sourcemap files could help if markdown->html engine supports them).
Further interactions on the PR / issues / etc will result in alerts / notifications to the person making them.

It should be noted that the people doing the reviewing do not need a github account ( I think; although maybe it should be made very much advised to get one).

As a result, you can have a collaboration on a markdown document with a very diverse group; some people may be very happy to edit the markdown directly and interface directly with git.
Others (the professor / manager / customer / external reviewer) can use an interface that they are familiar with to make their changes.
The owner of the document can use all of github's / git tools to combine the comments / reviews / changes from different people.
