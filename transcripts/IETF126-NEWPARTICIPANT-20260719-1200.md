**Speaker 1:** Just a quick reminder. If you could scan the QR code for this session, it is a different attendance record since we have the morning session and the afternoon session. So, we'd love to see you practice that. You'll be doing it all week long, so you become experts.

Okay, I hope everybody got something to eat, maybe rested your eyes a little bit, caught up on email, took a nice little break. Welcome back. This is the afternoon sessions for the New Participant Program. We're going to have session five, which is about Internet Drafts and RFCs. After that, we're going to have a session about the power of the community in the IETF, which is you all. And then we just do a very quick summary and wrap up and we talk a little bit about what's to come during the week, and point out some sessions for new participants, and just, yeah, tell you a little bit about what's going on. So, without further ado, I'm going to pass it off to our speakers for the session. So, thank you.

**Alice Russo:** Hi, I'm Alice Russo, and you are at session five. Um, this is about the work items of the IETF. This is part of the IETF mission, the high-quality, relevant technical documents.

Next slide. 

Um, I'm part of the RFC Production Center. I've been part of the RFC Editor for a long time. *[laughs]* Since the RFCs in the 4,000s, and we recently crossed into the 10,000s. Um, I'm interested in how IETF tools and education can help authors write clear documents, and my favorite RFC is 50 Years of RFCs, which is some of the history of the RFC series, which we will not be covering in detail today. And here's Rich.

**Rich Salz:** Hi, my name is Rich Salz. I've been helping with the newcomer thing for a long time. Uh, disregard the philosophical rah-rah stuff. Um, I don't have a favorite RFC, but, uh, I also got a new haircut, since that was, you know... *[laughter]*

**Alice Russo:** Okay. This is the Note Well. You've seen it earlier today. Um, by participating in person or remotely, you agree to these policies. You'll see this a lot in every working group session this week.

Please go ahead and ask questions along the way. Also, there'll be a chance for questions at the end.

Um, RFC is an acronym for Request for Comments. Um, this is that was the historical purpose of the document series was to share ideas, share notes. Um, to get a sense of your familiarity, I'm just going to go back one so we're not already on that slide. To get a sense of this room's familiarity, can you raise your hand if you've read an RFC or a part of an RFC? So, that's most people in the room. And then can you raise your hand if you've written an internet draft before? So, that's maybe less than a quarter or about a quarter. And then if you have an idea that you want to write into an internet draft, but you haven't done it yet? Okay, less than a quarter. Um, who has visited authors.ietf.org, a website? Anybody? A couple of people, a few people. So, authors.ietf.org is designed to give, um, you the guidance you need to write internet drafts. And a lot of what we're covering today is on that site.

Okay. Um, there are almost 10,000 documents in the RFC series. The official site is rfc-editor.org, and that site was recently totally replaced in May. So, if you haven't checked it out lately, go check it out, please. Um, a lot of what we'll be talking about today is about content on rfc-editor.org, but RFCs, by their very nature, are freely available. Um, and so they're available on a lot of URLs, right? A lot of different places have RFCs. The concept is that they're stable and they support interoperability. Um, some famous examples of RFCs: TCP, IP, um, TLS 1.3 recently published, Quick. Um, and today we'll be going through a lot of aspects of RFCs. Where do they come from? What are they, exactly? What's their status? Um, what does it mean to be in a subseries of the RFC series? Um, relationships with other RFCs. Um, and the RFCs don't change. So, if there is an issue issue in it, an error in it, then it gets reported as Errata. And the Errata are now on a subsite that's errata.rfc-editor.org. They're also linked to from the main display of RFCs that's on rfc-editor.org.

Uh, internet drafts. Many, many more internet drafts. This is what is used um to write down your idea, share your idea. And then and anyone can upload an internet draft. So, as you learned today in the earlier session about standards development, this is how the working groups are moving forward with ideas. Um, by writing internet drafts, and then multiple versions. Um, this is the primary way that a protocol is advanced or an extension or any other idea. Um, datatracker.ietf.org makes them available in various formats and shows the version history. In contrast to RFCs, internet drafts are expected to change. Um, we'll cover today how they're structured and the tools to write them, and they time out after 6 months and they're moved to an archive.

Okay. The RFC series has existed for many years, so they are available in various formats. Um, the bright, shining new format on rfc-editor.org for the more recent RFCs is HTML that is has responsive design, works in different window sizes, will display SVG diagrams if they're available, and on the right side of the page has um metadata about the RFC and also links to Errata. Um, what's shown in this screenshot is the table of contents. There's also available an HTML file that's compact for download, but this is the most accessible and most beautiful of your RFC displays and newest. *[laughs]*

This on the other end of the spectrum is old school plain text. This is the original, um well, originally, they were typed and distributed in hard copy only. Um, then plain text files, um uh so, this was this doesn't have any links in it. These files are still available. Plain text is still available. Um, the series was the RFC series was created before online existed, and the series was created before HTML was defined. So, we've seen the evolution of um the document formats and how they're stored and how they're made available. So, um plain text files have been retyped basically for the super old ones. This is showing the header of a retyped um RFC 1 from 1969. This document series created the IETF, or documented the creation of the IETF, I should say.

And this is a HTMLized display. So, basically, taking an old plain text file and adding links into it. It's also available at that same route, the path which is rfc-editor.org/info/the RFC number. So, it has a similar layout on the right. You're getting the metadata about the RFC, and it's going to show here if this RFC has been obsoleted, which means completely replaced, or updated, which means part of it has been changed. Uh...

There's also PDF available. This is the only paginated format and it contains SVG diagrams that I mentioned earlier. For the newer RFCs, the PDF is very similar to the HTML format. Um, for the older ones, it's just a PDF of the plain text.

This header is the metadata at the time of publication. So, it's not going to be updated to show later that this document has been has been obsoleted. So, you're best off if you want to know if the RFC is current, you're best off with HTML.

And this is the source format for generating the RFCs. It's a defined vocabulary. It's an XML file. Um, the attributes here hold the metadata, and the content follows. But for writing an internet draft, you don't have to use RFC XML, which is this defined vocabulary. Um, you can use Markdown to create this XML file. And there's specifically a flavor of Markdown called Kramdown RFC, which we'll cover more later.

Okay, status. What kind of document is this? Subseries is specifically within the RFC series. There's two smaller subseries, one for Full Internet Standard, one for Best Current Practice, closely tied to the concept of status. And then Stream means where did it come from. So, did it come from the IETF? Likely. Most RFCs in modern times are from the IETF. For example, in 2025, over 90% of the RFCs came from the IETF. So, we'll be talking about the most common case and the other cases as well.

So, Informational. This is for use cases, applicability statements, framework, architecture. It's not the protocol itself. Um, Experimental is a different status for, uh, like a new extension on an existing protocol. It can be run as a time-limited experiment, and then you report back. For example, IMAP extensions are often experimental, like IMAP Message Limit Extension.

Proposed Standard is the most common status. Uh, over about 70% of the RFCs published last year were Proposed Standard. And the standards process is now only two stages. That's why Draft Standard is crossed out here. Um, this maturity level is no longer used, so your document can start as a Proposed Standard, and then when it's shown to be interoperable and widely deployed, then it could become Internet Standard, the final standard stage. Um, for example, uh WebRTC, all the core specs for it are all Proposed Standard. Um, TLS 1.3 is Proposed Standard. Uh, for Internet Standards, we have uh Multicast Listener Discovery v2, um IPv6, and...

More, keep going on statuses, we've got Best Current Practice. So, there are two two things that a BCP could do. One could be that it's about process. So, for example, the IETF standards process itself is documented in a BCP, BCP 9. Or, it could be about technology. For example, OAuth 2.0 Security is documented in a BCP, BCP 240. And Historic are RFC a specification that has been superseded, so, for example, Network Time Protocol v2 and v3 were moved to Historic.

The trick with Historic is not every RFC that has been obsoleted has been changed to Historic status. So, an RFC could have been completely replaced by a new RFC, but the old one might not have had its status changed to Historic. So, when you're reading an RFC, you want to make sure you look at the header and see, has this document has this RFC been replaced? Cuz obsoleted is the word for replaced, then you want to go look at the newer RFC.

And the last category *[laughs]* here is Unknown. So, this is a catch-all for the RFCs that were published before statuses existed. For example, RFC 1, Host Software, that we saw earlier, um, from 1969 is marked as status Unknown. In the sense that these defined categories for the standards process didn't exist at the time that it was published.

Okay, moving into subseries. Um, some RFCs are Internet Standards. These are the one that have reached that that status, Internet Standard, and then they receive another number. So, they have their RFC number, and they also have an STD number. Um, and similarly, some RFCs are in the BCP subseries. They have status Best Current Practice, and then they're assigned another number. So, they have a BCP number. So, it's small here *[laughs]* but BCP 226 is about selecting the... Yes, go ahead.

**Speaker 2:** What is what is STD?

**Alice Russo:** Uh, so the question is, what is STD? And it's, so it stands for standard, the word standard, yeah. Um, and it's, but it's reserved only for the ones that are Internet Standard, so Proposed Standards don't have an STD number and are not part of the STD subseries. Um, the whole, yeah.

So, for an example of how these subseries numbers work, um RFC 793 was TCP. And when it was obsoleted, several times, one of the the most recent obsolete was RFC 9293 in 2022, and that so, when the old RFC was STD 7, but when it was replaced, now the new RFC is STD 7. So, you can think of the STD number, this or the BCP number, as a container. And in the container can go multiple RFCs. Like, in this example, the BCP 226 contains multiple RFCs, or sometimes it only contains one RFC. So, but when RFC 9293 TCP was published, then it became part of STD 7.

Publication streams are, where did the RFC come from? Um, as mentioned, most RFCs come from the IETF stream, um but it helps to know these other ones exist when you're reading an RFC and this is in the header, so you can immediately know what um where it came from, and each stream has its own process for approving documents.

So, uh the IETF stream is the only one that can publish standards track or BCP documents. The IAB usually pub- is the Internet Architecture Board, it usually publishes workshop reports or architecture documents. Um, one of the most important ones is um, well, anyway, they they I won't say most important, anyway, they publish a bunch of documents. IRTF um publishes is the Internet Research Task Force, which I think you learned earlier today. And they publish the results of research, and their documents go through a research group process instead of a working group process.

And the Editorial stream is about the RFC series itself, the policies of the RFC series. And the Independent Submission stream, uh, is content that's about the internet, but has not gone through the official process of the IETF, IAB, and IRTF. Um, it goes through a process where the Independent Submissions Editor, who's Eliot Lear, who's here this week, um reviews the document and has an editorial board that reviews the document, and um he's also checking in to see where you've already taken your internet- if you have an internet draft that you submit to the Independent Submission stream, he's re- excuse me, reviewing where that document has already been, like did you already try to bring it to a working group and is the Independent Submission stream the right place for it? And there's, um, information available on rfc-editor.org with more details about what that criteria is, what is to be included in the Independent Submission stream. Sometimes people just call it Independent Stream for short.

And what content actually goes inside of these documents, um, Rich will tell you.

**Rich Salz:** Okay. So, one way to think of the IETF- excuse me. As we say we make we work to make the internet better, and the way we do it is with words, just lots and lots of words. Um, we uh as you saw in the previous session, we don't have testing programs. Uh, it's all pragmatic. We write documents that we test out in the hackathon, um, and uh clarify if needed, and then we it gets published. Um, there's a two or three parts to the process of publishing, um, and then they're deployed and used. If somebody implements something wrong, it'll be on them. Um, we don't, you know, there's no enforcement mechanism.

So, let me talk about what's in these documents. Uh, both the ID, ID is the abbreviation you'll see all the time because internet draft is just too long to type out, right? So, I-D. Um, and an RFC, so these are things that appear in the drafts that are developed usually through a working group and then finally published. Um, common elements are the title, author. Um, author and editor are sort of used interchangeably. Uh, sometimes there's special meaning associated with it, but fundamentally, it's the person who wrote put those words to, I was going to say paper, but that's dating me. Uh, when it was published. Um, what its status or intended category is. Um, it can change at any time. Someone can start to write something, it's informational, um, and then the working group will decide, no, this should be a new standard, so we'll be on the standards track, Proposed Standard. Uh, if it updates or obsoletes any previous RFCs, those are noted uh in the header too.

Um, some of the differences are, uh if a working group, um, you can be intended or it can be actually adopted by a working group. That's a semi-formal process for working group to say, yeah, we want to work on this problem. Um, those appear, you know, that a working group doesn't appear in the final RFC. The work an RFC is the product of the IETF um, or other streams, but we'll talk mainly about the IETF. Uh, what stream, if it's been adopted, where you intend it to go. Um, how long it how long until it expires. Drafts automatically, uh, expire after 6 months. Whoops.

**Alice Russo:** Oh, okay.

**Rich Salz:** All good?

**Alice Russo:** All good.

**Rich Salz:** Okay, sorry. Um, they normally, uh, expire after 6 months. What expire means is it just doesn't show up in some views of the archive. Um, it's still there. Nothing is actually ever removed. It's really a It is a semi-permanent document. Um, so you can see on the upper right-hand corner there, there's the things that show up in, um, a draft version of a document. Um, later on, it'll show, uh, oh, JD really wrote one. Um, okay. And then at the bottom, you'll see what the RFC actually looks like. It has, for the most part, the same kind of things. Everything is published. What did I do?

**Alice Russo:** Did you fix it? I don't know, I don't know if that was you or not.

**Rich Salz:** All right.

Okay. Maybe we had a network hiccup.

**Alice Russo:** We have?

**Rich Salz:** Might be. If only there were some engineers around who could, yeah, knew how the network worked.

**Alice Russo:** I can, I can help.

**Rich Salz:** Yeah, right. Well, it's, yeah, I would say the it's obviously a DNS fault, but...

Okay, where were we? Okay. Where were we? Uh, 16... Yeah. Do you know where we were? Yeah, try try 18. 18? Yeah. No, keep going. We were there? Yeah, not yet, but we can be there. Okay, we'll take some time. Okay, so this so, yeah. Is that it? No, go back one. Required content. Okay, no, next. One more? One more. Keep going. Keep going. Yeah, but past this. Yeah. We're going the wrong direction. Yeah, we're going the wrong direction. Someone should have someone should have stopped me. Keep going. Where? At, "Click of not working?" Yeah, click. I have to... Oh, she's got it. Well, if you sign to me, I can fast-forward to where we are. Okay, ready? Yes. That's probably that one. Yeah. Okay. Good.

That was our first hiccup in NPP for today, but we're doing good. Yeah. Yeah, this is the first real day of of using it. The tool is really very good, and I'm sure it was a DNS problem. So, um, when you use the standard or the common authoring tools, much of the information, what we call the boilerplate, is sort of automatically generated, the status of the memo. What you see here on the right is the text that appears in an internet draft. Says, you know, "Hey, this is a draft document. Don't use this to make purchasing decisions. It could change. Um, this one is a product of the IAB, which is the Architecture Board, so it's not an official standard at anyway." Uh, copyright notice. When you write an internet draft, uh, intending it to become an RFC, you are giving the IETF rights to do things with it. You don't give up any of your own rights, but you are giving the IETF permission to modify it, use it, publish it, drop it on the floor, whatever the IETF wants to do with it. Um, and then the table of contents. That's automatically generated. In the old days, you used to have to type like, NROFF .ll and .in + 5 and... Nobody counts page numbers anymore.

Uh, required content, uh, similar to what mentioned before, uh, the abstract. This should be a short summary of what the document is. A lot of that abstract is then commented into the intro- copied into the introduction, which is a longer description of what the document is. Uh, the abstract should only be like a paragraph long, right? Uh, security considerations is required. Every document must have a security considerations document, uh, section. And even if it says, "No, there's," it can say something as simple as, "This is all about security." For example, the TLS specification says, "This is all about security." Um, or it can have something that says, "This does not, uh, there is no impact on security at all." Um, for example, one of the BCPs that describes how the IETF standards process works, says, "Oh, this is there's no internet security involved here." Typically, that will be a couple of pages that say, "Well, if somebody does this, then that information could be exposed. So, you have a set of tradeoffs." Often, that's very, very, uh, helpful to implementers. Um, and the working group will often come together and help you provide a security considerations. IANA, the Internet Assigned Numbers Authority, uh, that's the group that assigns things like the protocol number that says, "HTTP is on port 80." Uh, "DNS is on port..." I forget, 23.

**Audience Member:** 53.

**Rich Salz:** 53. I knew there was a 3. Um, they they assign those kinds of numbers. So, if you're making a defining a new protocol, or you're filling out an extension to an existing protocol, you have to describe in the IANA considerations where you want that number to come from. References. They're divided into two parts: informative, "Hey, if you don't know what we're if you're confused, this might be useful to you," and then normative, which says, "This thing builds on those, so you really have to understand those other kinds of documents." There are tools to, uh, particularly for the references, make it very easy to generate reference list and so on.

Talk about writing a draft. Uh, this is the bulk of the work that members in the IETF, that participants in the IETF and folks who want to participate in the IETF will do. Uh, anybody can write one. There is a draft out there by Warren Kumari, I think, that says, "This is not a standard," and it goes through paragraphs of all this cute little phrase that says, "And I can say, I can talk about my peanut butter and jelly sandwich if I want to." Um, anybody can submit a draft. You don't need any permission. All you need to know is when you submit the draft, you're giving the IETF rights to do things with it. Some people write a draft and never submit it because it's a useful construct or a useful outline sometimes to get your thoughts on paper. Um, once it's submitted, it can never be removed, withdrawn, taken away, um, the rights are granted permanently. There have been a few instances where it was decided somebody submitted a draft and that was like blatantly offensive to large groups of people, so they deleted them. Um, they have no formal status until they're adopted. In other words, they're not a part of a product of the IETF or involvement with the IETF. Oh, and there's the Warren Kumari draft. It says, "Here's a draft I wrote. It's nonsense."

Okay. Step one, choose your language and toolchain. There are many ways, uh, to write a draft. Ultimately, as Alice said, the final input format is a dialect of XML, or a particular subset of XML called RFC XML. Nobody cares about XML anymore, right? It's either it's JSON *[laughs]* you know, either unless you're like a a doc writer, you're doing doc-type stuff. Um, it's either going to, you know, XML became either JSON or or something like that, or it became Markdown. So, Markdown, and in particular, a particular dialect of Markdown, um, called Kramdown, uh, is is what to use. So, if you don't know what to do, or even if you think you know what to do, just pick Markdown. The subsite authors.ietf.org has all of these definition all of these examples of, here's a list of all the tools we use, here's the, you know, it should be one long, use Markdown. Um, it should be one. There are also additions to Markdown that provide nice, simple ways to integrate with GitHub. Um, so you can make submissions, you can make drafts, you can do a GitHub task that says, uh, "Publish my new update my draft," and so on. All of that is done by one of the volunteers, a guy named Martin Thomson at Firefox. Um, people often follow the lead of the co-authors. Generally, when you're writing a draft the first time, you'll you'll work with somebody who's either knows how to do it or has already written a draft that you want to add to. So, you work with the co-authors. Guaranteed they're doing Markdown and probably using the GitHub tools.

Step two, add your content, uh, required, recommended, general content. So, um, if you're writing a standard, the terms must, or writing a protocol, uh, the cert- certain terms that have specific meaning: *must*, obviously, you must do somebody implementing the protocol must do this; *should*, uh, you can not do this, but you better have a good reason; *must not*, you must never do this, right? Um, they guide The IESG also has guidance on inclusive language, uh, happened about, well, turn of the century, right? We used to see phrases like master-slave, uh, whitelist-blacklist. We try not to use those anymore. We try to also be gender-neutral. Um, NIST, the US government agency, used to have a spec that was really good about why you would want to do inclusive language. Uh, it got pulled back, but we have a copy of it, you know, stashed. *[laughter]* Nothing ever disappears from the web. You must Well, it's important to remember that. There's also glossaries on the RFC Editor site about abbreviations and special terms that you don't have to explain, right? I don't think anybody really knows what TCP stands for anymore, right? Or HTTP. I mean, yeah. Um, you can put in special content diagrams, uh, which are generally written as scalable vector graphics, SVG. Um, if you're starting to do that, ask the community for help because there's particular dialects and rules. Um, there are formal mini-languages within the I- used within the IETF: augmented BNF, Backus-Naur form, I think, um, that says, you know, you can say, uh, "A *the* must be followed by an *a* or an *an*," and there's there's rules and languages for that. Yang is a data description language. There's also CDDL and CBOR and stuff and so on. So, there are other formal languages used within the document of the prose of your draft.

Author-tools is a separate site that has a whole bunch of tools on how to on how to verify things. It will look at your Yang, it will look at That sounded obscene. *[laughter]* It will look Sorry. Um, it will look at your document and say, are you do you have all the right subjects? Did you have do you have the right copyright notice? Um, did you does your ABNF follow the right structure? Um, did you start to use some terms that maybe you shouldn't have, and so on. Um, it also does a thing called the nit, uh, nit tracking. Uh, nit is like little pieces of fluff or cat hair that you might pull off your clothing. Um, I can't think of a nit offhand.

**Alice Russo:** Typo.

**Rich Salz:** Yeah, typo, typo can be, right, you know. Did you you spelled "teh", did that really mean to be "the"? It will find typos. It will also find references. When you start to use a reference, um, and it says, "You're calling out this RFC which is in standards track, did you really mean for it to be informative or not informative?" and so on. So, um, it will do that. Generally, um, you do this kind of thing often just before you submit a new version of your draft, uh, because as it gets later on in the scheme, right, like software bugs, if you find and fix them after it's in production, it's a lot harder than if you do it during the initial development.

Uh, submit a draft. Again, the datatracker. Datatracker.ietf.org, it can be abbreviated via dt.ietf.org, that's just what I type all the time. There's a page like on the front after you log in, um, it says, "Submit a draft." You just submit it, and you can up- you generally, you want to upload the generated RFC XML. Um, if you use the GitHub tooling, it's you can it's a one-step, you know, click, make draft, and it goes. You get back a confirmation mail that says, goes to all the authors, saying, "Did you really mean to do this?" Yes, go to a website and click, "Yes, I meant to," nobody, you know, two-factor authentication. Um, it will validate the draft. It will check with all the authors, make sure that what they submitted, um, and then once the draft is posted, um, it will go to the working group members and a special mailing list that says this new document a new version of the document came out. The drafts, by the way, they end with -01, -02, -03, and that's how you determine the subsequent editions.

Yeah.

**Speaker 3:** Is Kramdown the only tool that will do that version, or...?

**Rich Salz:** Kramdown is the tool that does it the best. There are probably other tools. I forget there's a, um...

**Alice Russo:** XML...

**Rich Salz:** pardon me, yeah, yeah, there's other Markdown formats, but Kramdown understands, for example, what the front matter looks like, uh, when you how you can you can sort of curly brace, open two open curlies, and then RFC number, it will automatically turn that into an RFC reference. So, that's without a doubt, that's the most time-saving thing. And it looks like Markdown. Every par- you know, paragraphs submitted by blank lines, bullet list have a dash in front of them, it's it's Markdown with some extra additions.

Yeah. Uh, 2 weeks before the IETF, um, we stop publish- we stop accepting drafts, and they start up again tomorrow. Uh, that's to give time, people time to read the drafts that are of interest to them. Um, nobody, it used to be everyone would, you know, print out all of the drafts and read them on the plane. Nobody has time to read all the drafts anymore. There's there's just too many working groups and too much content. But the ones that are, you know, you're probably focused on a particular set of things, so you definitely want time to have the drafts available.

The authors website authors.ietf.org has a whole bunch of things. It's got pointers to all of the tools that we know about. I think the ones you should use are starred. Um, it has, uh, some of them are developed by staff of the IETF staff, um, some are developed by volunteers, Kramdown RFC is by, uh, Carsten, who is guy likes writing tools. Um, as is Martin. Um, templates and schemas for RFC XML and templates for writing different kinds of drafts are also there. As is the full reference for RFC XML, so if you look at something and it comes out weird, you can look at the Kramdown output, it'll change. Um, if you generate a postscript, a PDF file, by the way, your Markdown is embedded in the PDF file. You can't see it, but it's embedded there as an extra item.

Okay. That's all the groundwork, and now Alice will talk about what happens after the working group says, "We're done."

**Alice Russo:** So, from what you learned earlier today about the working group process, let's say we're in the IETF stream, and your document has made it through the working group process, and there's a proof for publication as an RFC, then it enters the queue for the RFC Editor, which is the RFC Production Center to review your document. So, at this point, the technical content should be solid, and so this is an editorial light edit, generally speaking. Occasionally, an editorial question is raised that points out that there's a technical issue. And at that point, the Area Director would be involved, and if necessary, the document can even go back to the working group to resolve a technical issue. But for the typical case, this is not happening. It's not the document does not go back to the working group at this point. Um, the RFC Production Center is editing the source file, giving an RFC number, doing a pass for English syntax. Um, one of the goals is clear, concise, easily understood documentation, and that's what's happening. This is a copy-edit format, questions about any unclear text. 

Um, we ensure that the IANA actions are clearly documented inside in the document if if your document required IANA actions. This means, um, registration on iana.org. 

Um, there is an opportunity for the authors to review the edited document before publication. It's now called Final Review. In the past, you might have heard the former name Auth48. The Auth48 stood for Authors' 48 Hours. It is, in fact, not 48 hours, um, typically. Um, so basically, uh, at this point, um, you see each edit that the RFC Production Center has done, and you are checking to make sure that your technical content is still intact, which it should be. Um, each author who is listed in the header of the document approves the document for publication as an RFC. Um, and then it's made available in various formats, some of which we talked about today. 

Um, this week, I'm here with my colleagues at the RFC Editor desk. You can come by with questions about RFCs or what we've covered today. I really recommend going to authors.ietf.org that was mentioned and grabbing a template and and get started writing down your idea.

Any questions?

Yes.

If you could come to the microphone, and if you even want to practice putting yourself in the queue in MeetEcho, now's the time.

Good job. *[laughs]*

**Nathan:** Hi, everyone. I'm I'm Nathan. Um, I wanted to just ask a little bit more about the the interaction with IANA. I mean, hypothetically, let's say I would like an experimental protocol number for something that I'm working on with the expectation that maybe eventually it will become a production-grade, I don't know the word is, protocol number. Uh, could you talk us through how IETF interacts in either or both of those steps?

**Alice Russo:** Yes. So, IANA's here this week, so they and they have a desk, so you can actually ask them directly. But also, they make a document available on iana.org that's called Guidance to RFC Authors, which is really guidance to internet draft authors, um, and it really gets into, I think, digging into what you're asking, um, and how they'd like it. But it's basically, you write into the internet draft the details of what you want, and they review the text. 

**Nathan:** Okay.

**Alice Russo:** So, before the document even comes to like would be approved for publication as an RFC, IANA would have closely reviewed your text. Even if it gets on a working group agenda for an IETF meeting, they review all the documents that are on the agendas and send you comments and tell you if your IANA considerations section is not okay. So, IANA considerations is the portion of text where you detail exactly what it is that you'd like, a new registration or a specific value in a registry, but you don't say a number of the value, you can put TBD, and they will tell you what number you get if your if your assignment is made. But basically, the IANA, um, decisions about what you want registered happen separate from the RFC Production Center, and by the time we get it, IANA has completed typically completed their actions. And we're just updating the document to match the registry. But in terms of guidance about what how to detail what you want, um, I'd say they have an RFC, which is RFC 8126, but they have this more, what I'd say, more user-friendly guidance that's on their website.

**Nathan:** Okay. And Rich, you had something...

**Rich Salz:** Yeah, I was just going to add, many of the registries, and I think there's there's over 100 of them, um, they have space allocated for, you know, free for open use, experimental use, so you can start to play around with it if you're developing something new or at the hackathon, you know, next meeting or something like that. But, uh, yeah, work with see their website, and often there are registries that have designated experts, and IANA will deal with contacting them and say, "Does this make sense? Are you allowed to approve this?" and so on.

**Nathan:** Okay. So, would it be fair to say that they are kind of a parallel process but that the draft processes are entry point to getting, uh, an official assignment? Or, the entry point.

**Rich Salz:** Almost always, something has to be in a draft. Um, sometimes, it's a provisional assignment waiting for the publication of the RFC. Sometimes, a draft is good enough. Sometimes, other standards organizations request assignments, like the MIME types. W3C can allocate a new MIME type, for example.

**Nathan:** Okay. Thank you so much.

**Alice Russo:** And different registries have different rules, so I would check the registry, look at depend- depending on what you're asking for, check the rules for that registry. There are, um, some experimental numbers that you can get ahead of time for an internet draft. There's just different rules associated with it.

**Nathan:** Got you. Thank you so much.

**James:** Hi, my name is James. I actually put up my hand up there. *[laughter]* Maybe you didn't take note of that, all right. So, I have two questions, right? Um, the first one is, um, the other time, I heard, um, once an RFC is approved, although I think you were not the one that made the presentation, once an RFC is approved with a number, right, that it cannot be changed again?

**Alice Russo:** Right. Yes, so that's the, yeah.

**James:** Okay. So, so my question is, um, we know that things evolve and change with time. Does it mean that if there is a new innovation, which is still related to that RFC, we have to start a new RFC all together? So, I want you to clarify that. Uh-huh.

**Rich Salz:** Sure. So, there are two kinds of ways things can be updated. For example, um, DNS or TLS will have a they'll have different record types that you can add a new thing to. You can add a new record type or a new extension. That you just document in its own RFC. Um, sometimes, there'll be a whole new version of something, IPv4, v6, TLS 1.2, 1.3. At that point, we say, "This updates that," *[coughing]* pardon me, and that old version, it may or may not be obsolete. It's quote unquote "marked obsoleted," but people could still be using it, right? Because we're not going to we're not going to outlaw things, we don't do that. We're not "the protocol police" is a common phrase. So, um, either way, there can be either additions or, as you just it will become in the metadata that Alice talked about, an update to the original, or it will be something if it's a complete replacement, it will be an obsoleting of that other version.

**James:** Okay.

**Rich Salz:** In the interim, we just collect Errata or, yeah, a series of Errata, um, that mark what what we got wrong, and then when the new version comes out, we make sure that they're all addressed.

**James:** Okay, so if the new version comes up, right, uh, that means we have to send it for approval again? Like, it goes for approval?

**Rich Salz:** It goes through the same process: the working group, the IESG, all right, and then, if it's an IETF document, the whole IETF's consensus. Yes.

**James:** Okay, okay. All right. Thank you very much.

**Rich Salz:** Sure.

**James:** Then, the second one is, okay, so if I have an idea, right, and I think it's something that, um, I want people to contribute to, the community and stuff like that, what is the best approach to to to bring it to the community? Is it Hot RFC, Birds of a Feather, IRTF? What is the best approach?

**Rich Salz:** Yeah, so a Hot RFC is definitely one if you haven't written anything down yet, because Hot RFC, you what, 5 minutes to talk about?

**Alice Russo:** Less.

**Rich Salz:** Or, 2 minutes?

**Alice Russo:** Quick.

**Rich Salz:** Yeah, so Hot RFC, which is this evening, yeah, this evening?

**Alice Russo:** Hm-mmm.

**Rich Salz:** Yeah, Hot RFC this evening, you get like 2 minutes to talk about it. You get three slides, "Here's what I want to do. If you're interested, come see me," or, "Here's my email address." If you have a document that's more well-formed, say, you've been working with some other colleagues or in your organization, write it down as a draft. Um, Hot RFC may not be appropriate since you already got more. Um, there each area has what's called a dispatch group. Okay. Where they will to say, "Oh, we think this should go here," and they'll tell you. And there's they a lot of them are meeting I think the first one is Monday morning. Uh, there's a general dispatch area that's covering security and and art.

**Alice Russo:** Yeah, also I was going to mention that on the agenda, you will see, um, two places where it says IAB New Work Help Desk. So, twice during the week, the IAB will have, um, a little office, they have a sign, and, um, there's some times there. Um, and you can talk to them about new work. And that's another place where you can ask them, "What do you think, you know, do you think Hot RFC or dispatch or..." they they might have some suggestions of where you can bring your new new work.

**James:** Okay. All right. Thank you very much.

**Alice Russo:** Yeah.

**James:** Yeah.

**Alice Russo:** Fabulous questions, thank you. Um, we're running just a little bit behind. We're going to take a quick 5-minute break, change over the slides, uh give you a chance uh to get something to drink, and we are going to talk about the power of the community. Um, Bron's going to lead us into our next session, so we will be here uh back here in just a couple of minutes. So, thank you.

Thank you, Alice and Rich. *[applause]*