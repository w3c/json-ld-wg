---
layout: minutes
date: 2019-04-05
title: JSON-LD Working Group Telco — 2019-04-05
json-ld: |
    {
        "@context": "https://schema.org/",
        "@type": "CreativeWork",
        "url": "https://www.w3.org/2018/json-ld-wg/Meetings/Minutes/2019/2019-04-05-json-ld",
        "name": "JSON-LD Working Group Telco — Minutes",
        "about": "JSON-LD Working Group Telco",
        "dateCreated": "2019-04-05",
        "genre": "Meeting Minutes",
        "publisher": {
            "@type": "Organization",
            "name": "World Wide Web Consortium",
            "url": "https://www.w3.org/"
        },
        "recordedAt": {
            "@type": "Event",
            "name": "JSON-LD Working Group Telco",
            "startDate": "2019-04-05",
            "endDate": "2019-04-05",
            "attendee": [
                {
                    "@type": "OrganizationRole",
                    "roleName": "chair",
                    "attendee": [
                        {
                            "@type": "Person",
                            "name": "Benjamin Young"
                        }
                    ]
                },
                {
                    "@type": "Role",
                    "roleName": "scribe",
                    "attendee": [
                        {
                            "@type": "Person",
                            "name": "Rob Sanderson"
                        },
                        {
                            "@type": "Person",
                            "name": "Pierre-Antoine Champin"
                        },
                        {
                            "@type": "Person",
                            "name": "Benjamin Young"
                        }
                    ]
                },
                {
                    "@type": "Person",
                    "name": "Simon Steyskal"
                },
                {
                    "@type": "Person",
                    "name": "Ivan Herman"
                },
                {
                    "@type": "Person",
                    "name": "Adam Soroka"
                },
                {
                    "@type": "Person",
                    "name": "Jeff Mixter"
                },
                {
                    "@type": "Person",
                    "name": "Harold Solbrig"
                },
                {
                    "@type": "Person",
                    "name": "David I. Lehn"
                },
                {
                    "@type": "Person",
                    "name": "Tim Cole"
                }
            ]
        }
    }
---

# JSON-LD Working Group Telco — Minutes
{: .no_toc}
***– DRAFT Minutes –***
{: .draft_notice}

**Date:** 2019-04-05

See also the [Agenda](https://lists.w3.org/Archives/Public/public-json-ld-wg/2019Apr/0013.html) and the [IRC Log](https://www.w3.org/2019/04/05-json-ld-irc.txt)

## Attendees
{: .no_toc}
**Present:** Benjamin Young, Rob Sanderson, Simon Steyskal, Ivan Herman, Pierre-Antoine Champin, Adam Soroka, Jeff Mixter, Harold Solbrig, David I. Lehn, Tim Cole

**Regrets:** David Newbury, Gregg Kellogg, Ruben Taelman, Dave Longley

**Guests:** 

**Chair:** Benjamin Young

**Scribe(s):** Rob Sanderson, Pierre-Antoine Champin, Benjamin Young

## Content:
{: .no_toc}

* TOC
{:toc}
---


### 1. Approve minutes of last call
{: #section1}

> *Benjamin Young:* [https://www.w3.org/2018/json-ld-wg/Meetings/Minutes/2019/2019-03-29-json-ld](https://www.w3.org/2018/json-ld-wg/Meetings/Minutes/2019/2019-03-29-json-ld)

> **Proposed resolution: Approve minutes of last call** *(Rob Sanderson)*
{: .proposed_resolution}

> *Rob Sanderson:* +1

> *Simon Steyskal:* +1

> *Benjamin Young:* +1

> *Jeff Mixter:* +0

> *Pierre-Antoine Champin:* +1

> ***Resolution #1: Approve minutes of last call***
{: #resolution1 .resolution}

### 2. Announcements/Reminders
{: #section2}

**Benjamin Young:** Any announcements?  
… Good on F2F until TPAC. Just passed feature freeze deadline.  
… Anything else, other than issues?  

### 3. Best Practices / Primer / Cookbook
{: #section3}

> *Benjamin Young:* [https://github.com/w3c/json-ld-wg/issues/17](https://github.com/w3c/json-ld-wg/issues/17)

**Benjamin Young:** We have a stub primer that Ivan has made  

> *Benjamin Young:* [https://w3c.github.io/json-ld-bp/](https://w3c.github.io/json-ld-bp/)

> *Adam Soroka:* +1

**Benjamin Young:** and so I think we can close the meta issue  

> **Proposed resolution: close #17 as started with other issues/work to follow** *(Benjamin Young)*
{: .proposed_resolution}

**Pierre-Antoine Champin:** It says community group?  

> *Ivan Herman:* +1

**Ivan Herman:** Yes, that will be changed ASAP ... it's imported from the CG  

> *Benjamin Young:* +1

> *Pierre-Antoine Champin:* +1

> *Rob Sanderson:* +1

> *Harold Solbrig:* +1

> *Rob Sanderson:* +1

> *Simon Steyskal:* +1

> *Jeff Mixter:* +1

> *Adam Soroka:* +1

> ***Resolution #2: close #17 as started with other issues/work to follow***
{: #resolution2 .resolution}

**Benjamin Young:** Should I close by hand?  

**Ivan Herman:** I usually put in comments  

### 4. Issues
{: #section4}

**Benjamin Young:** Diving into the actual issues...  

#### 4.1. Recommended base context
{: #section4-1}

> *Benjamin Young:* [https://github.com/w3c/json-ld-syntax/issues/59](https://github.com/w3c/json-ld-syntax/issues/59)

> *Simon Steyskal:* bigbluehat: feature freeze was not regarding the primer document

**Rob Sanderson:** Issues for today about the primer document, so not subject to feature freeze  

**Benjamin Young:** Idea is to have a default context, similar to RDFa. Discussion about the risks and concerns, mostly about backwards compatibility  
… should it be a best practice / prevailing pattern. Make these available, as a lot of content is in these namespaces  
… dlongley raised that keys not curies are a good pattern  
… repeating common prefixes makes sense.  

**Ivan Herman:** need to be a little bit careful with rdfa comparison.  It had the extra difficulty of not having an equivalent of importing a file with prefixes  
… so supposed to put everything in your document, which becomes a pain  
… so default for RDFa is important.  We don't have that difficulty.  
… Can import context file, so the load is not the same.  Building in an automatic mechanism for these prefixes may not be a good idea;  
… in the RDFa case, the consequence is that every implementation has to regularly update their defaults  
… when the defaults are changed. E.g., writing my comments, I forgot to add something into my implementation, so updated it this morning. A pain on implementers and users of those implementations  
… I think that having an automatic mechanism is not a good idea, but having a context in a well known place with a number of useful things, and is maintained by the community via GH, is a good idea  

> *Rob Sanderson:* +1 to Ivan

> *Pierre-Antoine Champin:* +1 to *not* make it automatic

**Ivan Herman:** what this context should contain is a separate discussion  
… not really agreeing with dlongley. The number of vocabs in RDFa is quite extensive, so flattened would become a problem, and there would be a clash  
… in favor of reproducing the rdfa stuff. If people don't like CURIEs they don't have to use it  

**Pierre-Antoine Champin:** totally agree with ivan. dlongley's concern is orthogonal to this.  This context is useful for more RDF-y, and don't mind CURIEs. Also to context designers, for a base to import  
… to not worry about the prefixes, in order to define the flat namespace  

> *Rob Sanderson:* +1 to pchampin!

> *Benjamin Young:* +1 to having a handy context for common namespaces

**Benjamin Young:** I don't think dlongley was suggesting we discourage curies, but that the prevailing pattern is that communities publish their own context, with imports  
… at the data document level, discouraging curies is fine... but as pchampin pointed out it looks normal for some communities  
… so having a context with common mappings and making it available to import would be nice  
… process wise we need to decide how to maintain it  
… could be in the primer, but not extractable  

**Ivan Herman:** I think you are right — copy/paste is not the right solution.  We can set up a mini repository that contains that stuff and the readme  
… need to agree on a URL to be put somewhere, w3/ns could work  
… would then redirect to the GH document  
… for a start that would be okay, then need to see once the WG is done, then the CG could take over  
… and would have the right to decide on PRs and so on  
… whether it's on json-ld or not ... it doesn't really matter  

**Benjamin Young:** question of URL simplicity, but related to the process  

**Ivan Herman:** No problem with it, but i don't know who maintains json-ld.org the domain and if it will be still around  
… in W3C URL space it's not our problem  

**Rob Sanderson:** I agree with Ivan that a W3C url is less worry about maintaining domain names.  

> *Pierre-Antoine Champin:* ... There is prior art in maintaining a namespace at W3C. We can do the same.

**Benjamin Young:** The activity streams space is now maintained by the CG. They have additive process for getting stuff into it  
… some more prior art there  
… The CORS issues also highlights the need for stability  

> **Proposed resolution: do not create a default context, but do promote the use of common prefix mappings in the Best Practices and highlight a preference toward "bare" (non-CURIE'd) terms** *(Benjamin Young)*
{: .proposed_resolution}

> *Simon Steyskal:* +1

> *Jeff Mixter:* +1

> *Harold Solbrig:* +1

> *David I. Lehn:* with common resources need to consider caching issues so as to not overload servers

> *Adam Soroka:* +1

> *Pierre-Antoine Champin:* +1

> *Rob Sanderson:* +1

> *Benjamin Young:* +1

> *Ivan Herman:* +1

> ***Resolution #3: do not create a default context, but do promote the use of common prefix mappings in the Best Practices and highlight a preference toward "bare" (non-CURIE'd) terms***
{: #resolution3 .resolution}

**Ivan Herman:** I would propose to create a separate repository that will have a readme and a json context file, and redirect from a `/ns/` name  
… as a first approximation, for something to talk about, there is already a context file that was set up some time ago that mimics the RDFa defaults  
… I would take that and put it up, and we can discuss what should be in it  

**Benjamin Young:** What if we were to make this a shared effort to build off the RDFa one, to make it more operationalized  
… it exists, we could make it less brittle  

**Ivan Herman:** do you mean we do this together with the RDFa file?  

**Benjamin Young:** yes, create the repo and process and make that happen using the existing RDFa file. New process would then maintain it, and strengthen the one that's there  
… good to not have two that are 99% the same  

**Rob Sanderson:** it seems like there will be things we'd like to do in a context, which won't be possible in RDFa  
… so they'd be related, but different  
… like we might want "label" as a bare term in the default context  
… or `@id` to `id`, and `@none` to `none`, etc  
… those make no sense in RDFa  

> *Benjamin Young:* ...so, like where this is headed, but the specific documents would need to be separate

**Ivan Herman:** Agree, to add to it, the way the RDFa doc was created I've [described in the issue](https://github.com/w3c/json-ld-syntax/issues/59#issuecomment-480172561), but worth looking at the document critically and see if it's still relevant  
… Another aspect to it  
… merging is risky, and may create problems  
… keep them separate, and w3c's problem to maintain the RDFa doc  

**Benjamin Young:** Good points about different needs. Want the prefixes to match, and to stay matching.  
… We use them together, so lean on the RDFa doc quite a bit  
… Should be as stable and maintained as possible  

> *Pierre-Antoine Champin:* I spotted a discrepancy btw schema.org and RDFa with dublin core

**Ivan Herman:** Prefixes should be the same, as much as possible.  Will need to check, eg that schema.org does the same thing, with a smaller set of prefixes. The schema.org context file has foaf, and there should be compatibility there. If there's a clash, we should be in favor of schema?  
… but I'll set up the initial thing. We can come back and look at it  

> **Proposed resolution: have ivan setup initial repository for publishing a "common" context featuring prefixes and "bare" terms for use in the Best Practices document (and beyond)** *(Benjamin Young)*
{: .proposed_resolution}

> *Ivan Herman:* +1

> *Rob Sanderson:* +1

> *Jeff Mixter:* +1

> *Pierre-Antoine Champin:* +1

> *Benjamin Young:* +1

> *Adam Soroka:* +1

> *Simon Steyskal:* +1

> *Harold Solbrig:* +1

> ***Resolution #4: have ivan setup initial repository for publishing a "common" context featuring prefixes and "bare" terms for use in the Best Practices document (and beyond)***
{: #resolution4 .resolution}

> ***Action #1: set up an initial repository for a common context (Ivan Herman)***
{: #action1 .action}

> *David I. Lehn:* I wasn't sure how to vote on those proposals.  will need to consider proper versioning and caching to make shared resources work.  already an issue with similar things at w3id.org.  but perhaps making a common context is a good experiment that will force related best practices to be developed.

**Ivan Herman:** in the mean time ... bikeshed ... but what URL for `/ns` ?  

**Benjamin Young:** Let's do that on the GH repo :)  

#### 4.2. Multilingual Values
{: #section4-2}

> *Benjamin Young:* [https://github.com/w3c/json-ld-syntax/issues/105](https://github.com/w3c/json-ld-syntax/issues/105)

**Benjamin Young:** Another easy one ;)  
… this one is about how JSON-LD currently works, and our past decisions to use HTML for multi lingual values (strings with multiple languages)  
… so use straight up HTML, which is not ideal  
… Looking at text level semantics HTML, but that's for the future.  
… so what do we need to propose in the primer to close the issue?  
… related - there's no way to do multi-language language maps  

**Rob Sanderson:** it seems we should split this into a primer issue  
… eg how do you use language tags  
… and what do you do with multiple languages  
… and then have a syntax issue around gkellogg's issue for the normative specs  

> *Benjamin Young:* ...about, is it an error to have English and Japanese in a string that is stated to be only one of those

**Ivan Herman:** What was put there by gregg sounds like a solution, but a bit misleading. The use of language tags gives the wrong impression — should be just indexes  

**Ivan Herman:** Language tags are defined by ISO  

> *Rob Sanderson:* "<span lang=\"en\">Ninja in japanese: <span lang=\"jp\">忍者</span>"@ja

**Rob Sanderson:** I agree ivan. to your question, the RDF would look like that:  

> *Rob Sanderson:* `"<span lang='en'>Ninja in japanese: <span lang='jp'>忍者</span>"@ja^^rdf:langString`

**Rob Sanderson:** this has been my issue for 5+ years  
… language tags must be langString  

**Ivan Herman:** an RDF issue that is not ours to solve  
… Lots of nice discussions in dbooth's repo, but it should happen in RDF not here  
… same as missing base direction  
… we can only set a single language. And this is the same as base direction, shouldn't touch it  

> *Rob Sanderson:* +1 to ivan

**Benjamin Young:** RDF is woefully broken in this way, but Gregg's proposal of HTML +  language map would be desirable by JSON developers  

> *Rob Sanderson:* [https://iiif.io/api/presentation/3.0/#44-html-markup-in-property-values](https://iiif.io/api/presentation/3.0/#44-html-markup-in-property-values)

**Benjamin Young:** If built to contain HTML, they're not going to take it into RDF, so a little misuse has advantages  

> *Ivan Herman:* q=

**Benjamin Young:** our audience is interested in JSON, with a side plate of a graph  

**Rob Sanderson:** I put this link in earlier https://iiif.io/api/presentation/3.0/#44-html-markup-in-property-values  
… it uses exactly what gkellogg describes  
… it is common and exactly what people want to be able to do  

**Ivan Herman:** The funny thing is what you wrote is legal but ugly RDF -- a microsyntax for a string, which is outside of RDF or JSON-LD  
… it happens to be a subsyntax of HTML  
… don't need anything in the syntax document to do this, its a private agreement between parties  

> *Rob Sanderson:* +1 to Ivan

**Ivan Herman:** this is probably the only thing we can do  
… so no issue in the syntax document  
… it's an ugly but best practice given the current technologies  

**Pierre-Antoine Champin:** Going to propose a crazy idea, in the line of what Ivan said. We don't need to change RDF, we could define a custom datatype. `langString` is syntactic sugar for a standard datatype for a more ugly microsyntax of the language inside the value  
… we could define a more complex but similar datatype. That's the crazy idea :) We could instrument it in RDF, with another container type, so that what gregg proposed would generate the appropriate structure  
… but it's quite some work  

**Ivan Herman:** technically ... yes ... and now I put on the W3C hat, it's outside of our charter.  This would be a RDF datatype.  

**Pierre-Antoine Champin:** What about JSON data type?  

**Ivan Herman:** JSON is closer to our charter. But language isn't.  
… it would be a lot of work ... the flood gates would be open. Ruby, direction, etc.  

> *Benjamin Young:* [https://w3c.github.io/string-meta/](https://w3c.github.io/string-meta/)

**Benjamin Young:** worth pausing on the JSON data type. I hear the concerns ... is there a way around them? This string-meta document from i18n suggests JSON-LD as a solution for multi-language use  
… feel that there's an opportunity here  
… And if we miss it, there'll be a lot of terrible looking JSON-LD  
… I see that it evokes process specters, but it comes up a lot  
… The genie won't go back into the bottle. So any hope of this?  

**Ivan Herman:** Don't remember the issue, but got into a long discussion with the editors. The examples are mostly wrong.  

> *Benjamin Young:* [https://github.com/w3c/string-meta/issues/27](https://github.com/w3c/string-meta/issues/27)

> *Benjamin Young:* also [https://github.com/w3c/string-meta/issues/13](https://github.com/w3c/string-meta/issues/13)

**Ivan Herman:** I understand the problem. Would love for the problem to be solved, but outside our influence  

> *Benjamin Young:* oh...and [https://github.com/w3c/string-meta/issues/23](https://github.com/w3c/string-meta/issues/23)

**Ivan Herman:** I don't see any other proper way, other than having it done at the RDF level.  

> *Benjamin Young:* ...and another [https://github.com/w3c/string-meta/issues/11](https://github.com/w3c/string-meta/issues/11)

**Rob Sanderson:** The bigger risk is to build on shifting sands and have RDF come up with a different syntax that's incompatible with whatever we come up with  
… should instead use it as a way to highlight the need, and potentially a micro-chartered group to solve it for RDF  

**Benjamin Young:** Not ready to recharter, or make a new datatype. Rob proposes to kick it to another group and then an update to JSON-LD. Not a solution, but don't want to lose the actions  
… to close the issue we should state what can be done  
… but need to be clear as to what /should/ be done that's not confusing  

> *Jeff Mixter:* +1 to that

> **Proposed resolution: highlight the need for work is ongoing, but it should present what can be done today via language/data maps and/or using HTML (or other) micro-syntax for expressing multiple language** *(Benjamin Young)*
{: .proposed_resolution}

> *Rob Sanderson:* +1

> *Benjamin Young:* +1

> *Jeff Mixter:* +1

> *Ivan Herman:* +1

> *Tim Cole:* +1

> *Pierre-Antoine Champin:* +1

> *Simon Steyskal:* +1

> *Adam Soroka:* +1

> ***Resolution #5: highlight the need for work is ongoing, but it should present what can be done today via language/data maps and/or using HTML (or other) micro-syntax for expressing multiple language***
{: #resolution5 .resolution}

**Ivan Herman:** procedural question - if we close the issue, then I think we will lose it for the bp doc. For the time being we don't have an editor for the document. So don't want it lost.  
… should be raised in the BP repo  

> *Rob Sanderson:* +1

> *Benjamin Young:* +1

**Ivan Herman:** should go through the issues to make sure we don't lose them  

**Benjamin Young:** Agreed -- open editorial issues on BP?  
… keep these initial discussion in the syntax doc, to not have the comments scattered  

**Ivan Herman:** Wouldn't close this one  

> *Simon Steyskal:* [https://github.com/w3c/json-ld-bp/issues](https://github.com/w3c/json-ld-bp/issues)

**Benjamin Young:** not until there's another issue to write it up  

**Ivan Herman:** editor will write it up as they see best  

**Benjamin Young:** And it's the top of the hour  
… thanks for all the input  

---


### 5. Resolutions
{: #res}

* [Resolution #1](#resolution1): Approve minutes of last call
* [Resolution #2](#resolution2): close #17 as started with other issues/work to follow
* [Resolution #3](#resolution3): do not create a default context, but do promote the use of common prefix mappings in the Best Practices and highlight a preference toward "bare" (non-CURIE'd) terms
* [Resolution #4](#resolution4): have ivan setup initial repository for publishing a "common" context featuring prefixes and "bare" terms for use in the Best Practices document (and beyond)
* [Resolution #5](#resolution5): highlight the need for work is ongoing, but it should present what can be done today via language/data maps and/or using HTML (or other) micro-syntax for expressing multiple language

### 6. Action Items
{: #act}

* [Action #1](#action1): set up an initial repository for a common context (Ivan Herman)