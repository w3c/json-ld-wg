
![W3C Logo](https://www.w3.org/Icons/w3c_home)

# JSON-LD Working Group

This is the repository for the home page of the W3C JSON-LD Working Group:

https://www.w3.org/2018/json-ld-wg/

(That URL is redirected to the `w3c.github.io` view of this repository.)

## Specifications

GitHub repositories are linked from each specification. There is a separate [list of repos of this WG](https://github.com/search?q=topic%3Ajson-ld-wg+org%3Aw3c&type=Repositories).

All repositories for spec development share the same set of labels; inspired by the [labels organized for W3C specification](https://w3c.github.io/issue-metadata.html).

## Contributing to the JSON-LD Working Group Repositories

Use the standard fork, branch, and pull request workflow to propose changes to the specification. Please make branch names informative—by including the issue or bug number for example.

Editorial changes that improve the readability of the spec or correct spelling or grammatical mistakes are welcome.

Please read [CONTRIBUTING.md](CONTRIBUTING.md), about licensing contributions.

## Tools

Generating weekly minutes is done via the
[scribejs](https://github.com/w3c/scribejs) script and some additional
configuration settings provided in this repo (see `.scribejs.json`).

To use this repository's scribejs setup first install the tools...

```bash
$ npm install
```

Then run the following (with date
information changed to match your scenario):

```bash
$ npm run scribejs -- -d 2018-07-06 -o Meetings/Minutes/2018/2018-07-06-json-ld.md
```

This will request the IRC logs for the correct channel and convert them into
the Kramdown (a more feature rich form of Markdown) with settings to match this
repositories other documents.

If you need to make edits to the IRC log before generating the output (due to
incorrect scribenick or similar), you can download the W3C logs from URLs such
as `https://www.w3.org/2018/07/06-json-ld-irc.txt`. Once downloaded, you can
reference that input document directly (rather than using the automagic
date-based retrieval).

For example:

```bash
$ curl https://www.w3.org/2018/07/06-json-ld-irc.txt > 2018-07-06-json-ld-irc.txt
$ npm run scribejs -- 2018-07-06-json-ld-irc.txt -d 2018-07-06 -o Meetings/Minutes/2018/2018-07-06-pwg.md
```
Edit the .txt file and repeat the `npm run scribejs` line as necessary. Once
finished, you can commit the `.md` file and delete the `.txt` file (or keep it
for your records).
