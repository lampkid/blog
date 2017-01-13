---
title: '#HTML5# #设计#原理'
id: 243
categories:
  - HTML5
  - video
  - 他山之石
  - 设计之美
  - 转载
date: 2012-01-04 16:00:03
tags:
---

视频：

[jeremy-keith-the-design-of-html5.ogv](http://fronteers.nl/_downloads/2010/jeremy-keith-the-design-of-html5.ogv)

PPT：

*   [See slides on SlideShare](http://www.slideshare.net/adactio/the-design-of-htm)
*   [Download slides](http://fronteers.nl/_downloads/2010/jeremy-keith-the-design-of-html5.pdf) (PDF, 380KB)
中文版：

[http://developer.51cto.com/art/201103/247880.htm](http://developer.51cto.com/art/201103/247880.htm)

### [为之漫笔](http://www.cn-cuckoo.com/2010/10/21/the-design-of-html5-2151.html/comment-page-1#comment-3416)

### Transcript

Jeremy Keith: So, yeah. I would like to talk to you today about the design of HTML5\. So there's two parts to this. One is, of course, HTML5\. I could stand up here and just talk about HTML 5, but that's not what I'm going to do. Because you want to know what's in HTML5, you can Google it, you can read books, you can go and read a spec. Actually, some other people are going to be talking about the contents of the spec.

[0:32] Steve Faulkner will be talking about accessibility and HTML5, and Paul Irish is going to go through a whole bunch of the APIs that are in HTML5\. So I'm not going to stand up here and run through what's in HTML5\. Actually, before I even get started, I should probably clarify what I mean by HTML5, which seems kind of crazy, because why should I have to clarify what I mean by HTML5? Well, what I mean by HTML5 is HTML5\. There's a specification. It's called HTML5, and when I say HTML5, that's what I'm referring to.

[1:03] The problem is that other people are using the term HTML5 to refer to just about anything, which can be problematic. For example, referring to CSS3 as HTML5 for some reason seems to be a common technique. That's not what I'm referring to. When I say HTML5, I don't mean CSS3\. I mean HTML5\. We've been here before with terms. Like, it used to be that Ajax meant something specific, and then after a while it just became doing anything cool with JavaScript. That was Ajax, right?

[1:34] And now the same thing seems to be happening with the term HTML5\. It's supposed to mean a specific specification, and now it just means doing anything cool, full stop, on the Web. But that's not the HTML5 I mean. I don't mean this umbrella term that covers everything that's new these days. I'm specifically talking about the specification HTML5\. But as I said, it's not so much the contents I want to talk about. It's not going through a checklist…what's in HTML5?

[2:02] It's the other side of it, is the design of HTML5\. What I want to talk about is not so much what is in the spec, but why these things are in the spec--what the process was in thinking of these things, designing the specification. And in particular I think one of the reasons why HTML5 as a specification is quite successful, and the process has been successful, is that it is driven by design principles.

[2:29] Design principles are something I'm getting more and more fascinated with. So a design principle is essentially a belief, a tenet, a concept that you sort of rally behind. And it doesn't matter whether you're making a specification or you're making a physical object, or a piece of software, a programming language. You'll probably find the design principle, or multiple design principles, behind all good examples of anything that's been built collaboratively. And, it's not just in the world of the Web.

[3:01] Throughout history there are examples of design principles for large-scale constructions like countries and societies. I'll give you an example from the United States of America, is a design principle built into the Declaration of Independence. So they have the watchwords and then the sort of, the things like "life, liberty and the pursuit of happiness"--these are the key things that they've kind of thrown into the Constitution saying, this is what we're all about.

These are the principles upon which we want to build our society. Another example would be from Karl Marx, whose writings were used as a basis for building societies throughout the 20th century. And a lot of it could be boiled down to this one design principle: [3:31] "From each according to his ability, to each according to his needs." So here's a design principle guiding a sentient economic system.

[3:53] Another example much older than that but similar in principle to this would have been, "Do unto others as you would have them do unto you." A very simple, small design principle that Jesus Christ, a Nazarene Jew from about 2000 years ago…. And this design principle is theoretically what drives a number of religions that have been built on top of the teachings of this person. The principles and the practice sometimes go out of sync, but that's the way things work.

[4:23] Here's an example from fiction, when George Orwell wrote "Animal Farm." Here we had a fictional society and that fictional society was built upon a design principle. In this case the design principle was, "Four legs good, two legs bad." And what's interesting is that in Animal Farm, as the society changes, as the society evolves for the worse, the design principle changes along with it. So it just becomes, "Four legs good, two legs better, " as the animal farm itself changes.

[4:53] But it is interesting to see this even in works of fiction. And there's another work of fiction that has three design principles sort of baked in, and that's the canon of work that Isaac Asimov on robotics…he coined the term "robotics." And he basically ensconced into these three laws of robotics, three fairly simple design principles, but then built a whole canon of work around it--about 50 books based upon permutations of examining these design principles from different aspects.

[5:19] You're all probably familiar with the three laws of robotics, I'm sure. And this is, I think, the first example in fiction of design principles for a piece of software. In this case, the software is a software run on a positronic brain in a robot and it's down to three separate design principles. But I think this might be the starting point of actually having design principles for software. And since then we see design principles for a lot of really good software.

[5:48] Tim Berners-Lee--who, as you know, co-invented the Web--he has a document on the W3C website where he keeps his own personal design principles at a URL. And they're kind of sprawling. There's a lot of them there, and he adds to them, he adjusts them, he takes things away as time goes on. But I think it's actually a really good idea to kind of have a personal set of design principles somewhere.

Actually, Bert Bos, co-inventor of CSS--he's got a great document on the W3C website that's kind of a meta design principles document, like how to design building a format, whether it's CSS, whether it's anything else. Well worth reading. So you root around the W3C site, you find a bunch of these design principles and here we have Tim Berners…these own sort of personal ones. And you can see the watchwords that he's taken from schools of software engineering: [6:11] decentralization, tolerance, simplicity, modularity.

[6:44] So these are key watchwords that he keeps in mind as they come up with format. So you're all pretty familiar with the work of Tim Berners-Lee, because you use it every day, right? He invented the Web--co-invented the Web with Robert Cailliau. And as well as inventing the Web itself, he also came up with the language that we use every day on the Web. That language is, of course, HTML--hypertext markup language.

[7:09] And this is the sort of early history of HTML. It started with version 2.0\. So there never was an HTML one. If anyone ever tells you they've been doing HTML since version one, they're bullshitting you. There was a document called HTML Tags that contained kind of a handful of tags that still exist in HTML today, but it wasn't an official specification.

[7:31] And this whole idea, by the way, of using tags--angle brackets and then P or H1 or what have you--that isn't something that Tim Berners-Lee came up with. He was basically taking an existing vocabulary from SGML, particular versions of SGML that were in use at CERN at the time. So even back then he wasn't creating things from scratch, and that's an important lesson. You can still see in the evolution of HTML, is that it was that building on what's come before rather than trying to build something from scratch.

[7:59] So this HTML tags document was the first sort of version of HTML but wasn't an official version. The first official version was HTML 2.0, which didn't come from the W3C. HTML 2.0 was from the IETF, the Internet Engineering Task Force. Which is kind of--they were responsible for putting out a lot of standards before the W3C really started up.

[8:22] But then from version 3.2 onwards, it was at the W3C, World Wide Web Consortium, that later versions of HTML were spec'd. And as you can see there was some fairly rapid movement in the '90s. The '90s were a pretty turbulent time, if anybody was building websites back then. We had the browser wars. It was pretty messy. You had a lot of proprietary shit being thrown into browsers as they tried to compete at having the best proprietary shit. It was kind of a messy time.

[8:54] It wasn't clear at all at this time that HTML was even going to be around, that HTML was going to last as the format for the web.

[9:03] But you can see it evolved fairly quickly -- we're at 3.2, 4.2, 4.01, right from 1997 to 1999 -- a very rapid evolution. What happened with 4.01, W3 sort of stepped back, they look at it, and they said, "OK. This is good. We're done with HTML. HTML 4.01 is the final version of HTML. We don't need an HTML working group anymore."

[9:25] But they didn't stop working on the language, but it was no longer HTML that interested them. Right after HTML 4.01, they came up with XHTML 1.0\. Sounds like something completely different, but actually XHTML 1.0 was really the same as HTML 4.01\. I mean literally the content of the specification were the same. The vocabulary was the same -- all the same elements, all the same attributes.

[9:50] The only difference was that in XHTML 1.0, you would use XML syntax. So that meant all of your attributes had to be lowercase. All of your elements had to be lowercase. All of your attributes had to be quoted. You had to remember to use closing tags with the self-closed tags like image and break. Right?

[10:11] From the point of view of the contents of the spec, exactly the same. There really was no difference. It was, in a sense, really just coding style, because to a browser if you served up HTML 4.01, HTML 3.2 or you served up XHTML 1.0, it didn't matter. It was all the same to the browser. It would make the same DOM tree. But what was kind of nice about XHTML 1.0 was because it had this kind of stricter syntax, it was a coding style people could get behind.

[10:39] So this time period of 2000, this is when the Web Standards project was picking up steam, and developers were really pissed off with all the proprietary crap that was being thrown into browsers. They're getting angry and saying to browsers, "Why don't you just follow the damn specifications?" And CSS was starting to really to take off in a big way.

[10:59] They kind of latched on to XHTML 1.0\. It was like, OK, this was going to be best practice, even though as I said, there's really no difference between HTML 4.01 and XHTML 1\. They said, "OK, professionals always use lowercase elements, always use lowercase attributes, always quote attributes." It was a good body of practice. So a lot of people got behind that syntax.

[11:18] I did, for example. For the last 10 years I've been using the XHTML 1.0 doctype. One of the reasons is that makes the validator a more powerful tool for me. So if I'm writing XHTML 1.0 and I've run my document through the validator, it's going to tell me if I forgot to quote an attribute or if I forgot to include the closing tag -- stuff like this. Whereas if I was writing in HTML 4.01, that stuff would be legal. It wouldn't necessarily catch it.

[11:44] So that's the reason I've been using XHTML 1.0, and I'm guessing a lot of people… Hands up those who use XHTML 1.0\. Yeah, OK. HTML 4.01? A few people. Any others? Just shout them out.

Audience: [12:00] member: HTML 5.

Jeremy K: [12:01] HTML 5\. Good for you. [laughter]

Jeremy K: [12:03] Anything older? Anybody use older doctypes? No?

[12:07] Like I said, I've been using XHTML 1.0 for ten years now because it make the validator a more useful tool. Is anybody using XHTML 1.1? Are you now? Keep those hands up. Are you certain your document is in XML?

Audience: [12:23] member: Some of them are.

Jeremy K: [12:24] The ones that are not are not XHTML 1.1\. So this is the big issue. After XHTML 1.0 came XHTML 1.1\. A small point increase doesn't sound like much. And again, there's nothing new in the spec from a vocabulary point of view. It's all the same elements. It's all the same attributes. The only difference was that now, with XHTML 1.1, you must serve your documents as XML.

[12:47] With XHTML 1.0 you could serve them as HTML if you wanted, and that's exactly what we do because, you would be kind of crazy to serve your documents as XML. One of the reasons why it would be crazy to serve your documents as XML is that Internet Explorer can't handle it. It can now in version 9\. It's like, aw, that's so cute, that they're even still thinking about that stuff. That boat has sailed -- but, it's nice.

[13:13] So the world's leading browser at the time couldn't even handle documents sent as XML, and this specification is mandating you must send the documents as XML, which is kind of crazy.

So XHTML 1.1 was just not that realistic. And the reason why you wouldn't want to send your documents as XML even to browsers that understand XML, is the error handling model of XML. So the syntax of XML, OK, I have no problems with lowercase attributes, lowercase elements, always quote your attributes. That's fine. In fact, I kind of like it. But the error handling model of XML is this: [13:26] when a parser comes across an error, stop parsing. That's in the specification.

[13:55] So when you serve up XHTML 1.1 as XML, and let's say you open it up in Firefox and you've got one un-coded ampersand, just one on the whole page -- then what you see is the yellow screen of death. Firefox will say, "Nope, you can't see this web page, " because of this one error on this page. That is the correct behavior according to the XML specification. For Firefox to stop right there and not render anything else is actually correct according to XML.

[14:24] Not in HTML, because HTML has never had an error handling model. But according to rules of XML, that was correct. So that's another reason why you really would not want to serve your documents as XML.

[14:36] And then the next iteration was XHTML 2, and you'll notice there's no date next to that because it never actually got finished. Now, XHTML2 -- I want to be really clear on this -- is actually a really, really nice specification. A really good specification, from a theoretical point of view. I mean, the people building the spec were very, very smart people. Actually the main guy leading the spec was Steven Pemberton, who was a resident of these parts and he's an incredibly smart guy.

[15:06] It's a fantastic specification, and it would be a wonderful format if everyone agreed to use it, but it's just not that practical. For one thing, it still uses the XML error handling model. You're supposed to serve your documents as XML. Forget about it right? We're not going to do that.

[15:23] Two, it was deliberately going to break backwards compatibility with existing versions of HTML. At one point they were talking about deprecating the image element, which seems kind of crazy to people who are working on the web everyday, but they had good theoretical reasons for doing this -- that the Object DOM may be the better one to use.

[15:40] So XHTML 2, despite the fact that it was a great format in theory, it never took off in practice. It was never going to take off in practice, because authors like you and me were never going to get behind something like that, that breaks backwards compatibility. And neither were browser makers. Browser makers committed to maintaining backwards compatibility.

[16:00] There's one single reason why XHTML 1.1 is really not that widely used as XML and why XHTML 2 never took off. It's down to a design principal. That design principal is Postel's Law. You've got to be conservative in what you send, be liberal in what you accept.

[16:19] Be liberal in what you accept -- that's what the web is built on. People making web browsers have to be liberal in what they accept, because they are given some pretty crappy stuff to accept. A lot of documents on the web are not pretty, but that's the way the web is.

[16:33] The web has kind of evolved in a very messy way, but it's a beautiful mess. There's a lot of badly formed documents out there, and it would be great if everyone was writing proper XML and everything was well formed, but that's not the reality. The reality is Postel's Law.

[16:48] So as professionals we try to be conservative in what we send. We try to use best practices. We try to make sure our documents are well formed. But from a browser's perspective, they must be liberal in what they accept.

[16:59] And if you think about the error handling model of XML that was applied to XHTML 1.1 and XHTML 2, That error handling model, this draconian error handling model, is definitely not being liberal in what it accepts. It's quite the opposite to say, "When you encounter a single error, stop parsing." That's the opposite of the robustness principal.

[17:20] So we get to HTML5, which didn't come directly from the W3C. So what happened was…so there hadn't been an HTML working group since the end of the 20th century.

[17:38] Some people at the W3C kind of think, maybe there's still life in HTML. If we just extended it a bit more. Instead of concentrating all our efforts in XHTML, we could improve the forms in HTML. We could make HTML a bit more application like, and just evolve it a bit more.

[17:55] So there was a workshop in 2004, some W3C members, and Ian Hickson, who was working at Opera at the time, he put forward this proposal to extend HTML, to do some work on HTML, in parallel to XHTML2, but to continue working on HTML, to expand it a bit more.

[18:11] And they had a vote, and the W3C voted, NO, so HTML was dead, and XHTML2 was the future. So the browser makers, Opera, Apple, a few others, said, "That's fine. We're just going to go over here, and we're going to work on this stuff by ourselves outside W3C." So they formed the Web Hypertext Applications Technology Working Group.

[laughter]

Jeremy K: [18:39] WHATWG And it's a good thing they called themselves a working group rather than a task force.

[laughter]

Jeremy K: [18:49] So what they decided to do was, completely outside the W3C, continue working on HTML and throwing in some new stuff. And because they're browser makers, not only are they coming up with this stuff, but they're also shipping it, right?

[19:01] They're coming up with good ideas and putting it into browsers. And things move pretty fast. They start getting stuff done. Well, meanwhile, over at the W3C, with the XHTML2 nothing much is really happening. In terms of actual implementations, there really isn't much happening.

[19:15] So then an interesting thing happened, which was in a blog post in 2006, Tim Berners-Lee said, "You know what? We were wrong. We were actually wrong to expect the whole Web to turn to XML overnight. It was pretty unrealistic of us, and yeah, we probably should re-charter the HTML working group." So that's exactly what happened, that the W3C started up an HTML5 working group in 2007.

[19:40] And the first question they had, of course, was, well do we start from scratch, or do we take as our basis all this work that's been done since 2004 over at this other group called WHATWG?

[19:50] And that was a no-brainer, because, of course, we're going to take the existing work, and we should build on that. So they had a vote, and they agreed, "Yeah, we're going to build on what the WHATWG is doing. So now we need to work together with the WHATWG."

[20:02] Second question is, OK, how to make that smoother? Who should be the editor at the W3C? Should we have the same editor that they have over at the WHATWG? Which is Ian Hickson, who at this stage is working at Google.

[20:14] And they had a vote and said yeah, actually it would make things better if Ian Hickson was editor of the HTML5 spec at the W3C, as well as being the editor at the spec over at the WHATWG. So they voted on that. And that's kind of the situation today.

[20:30] So it is one format, but it lives in two places, because you've got the specification listed on the WHATWG site, and it's also listed on the W3C side. It's a little bit confusing. If you're coming to it cold, you might go, "Which one is the real spec?" Well, they're both the same, kind of.

[20:50] Actually the specifications will diverge in the future. They'll start to diverge slightly. The idea is that the W3C are working on nailing down a specific specification, right? It'll go to last call, and it'll become a working draft, and it will be set in stone.

[21:03] Whereas the WHATWG, their plan is for a constant iteration. So, even though it's currently called HTML5, it's actually not a great term for what the WHATWG are working on. It's better to think of it as just plain HTML, or web technologies, because that's the idea there.

[21:19] But it's definitely a confusing situation, that there are these two groups working on what's basically the same specification. It can be quite confusing.

[21:27] And then there are the processes behind the two groups, because they're quite different, philosophically speaking. The way that things work at the WHATWG is essentially a dictatorship, right? You've got Ian Hickson as the editor. He will listen to all sides. Everyone states their arguments, and then he does what he thinks is the right thing to do.

[21:49] And then at the W3C, it's the opposite. It's a democracy. Everyone gets a say, and everyone gets a vote, and it's the vote that matters, the vote that decides. Now on the face of it, the WHATWG way of doing things sounds horrible. It sounds really bad. It's like, that's no way to run any kind of project, and the W3C way sounds great. It sounds very egalitarian.

[22:11] In practice, however, the WHATWG way works pretty darn well. I think it works well because of Ian Hickson. He is actually a really, really, good editor and is almost robotic in his ability to listen to arguments dispassionately.

[22:24] And the W3C way, which is very fair and principled, is actually…it can get bogged down very quickly in process and procedure, and it takes a long time to get stuff done. So what works best in a way, I think, is to have a mixture of the two. So the fact that these two bodies are working on the same spec, I think they kind of complement each other quite well.

[22:47] And one of the reasons that they can work together is because of the design of HTML5\. It's because they have thought from the start what they're trying to achieve. So as well as there being the specification itself that lives at a document on the W3C site, this is the specification for the HTML5 language, there is another document on the W3C site, and that is HTML design principles.

[23:15] And one of the editors of this document is here in the room with us today, Anne van Kesteren, so if you have any questions about this document, you can ask Anne. It's an excellent document. It's really good.

[23:27] And essentially, what it is, is…so you've got the W3C, you got the WHATWG trying to work together, and it's like "The Odd Couple." How will they ever get on? Well, this document kind of enshrines what they're working on, what they can both agree on. And I want to go through those things.

[23:43] So if they can all agree on what's in this document, then I think HTML5 will be a great specification. And they have agreed on that this is what they're working towards. So you can see the watchwords are, "Compatibility, " "Utility, " "Interoperability."

[23:56] So for all the differences between the WHATWG and the W3C, and there are plenty of differences, they also have this stuff in common, and that's the most important thing, right, that they've got common ground, and that they've enshrined that common ground into a designs principles document.

[24:13] So I'd like to show you some of the design principles that you can find in this document. Here's one, very simple, "Avoid needless complexity." It seems fairly straightforward. I'll illustrate with an example.

[24:27] Let's say I'm writing an HTML4.01 specification, so I open up my document, and I'll type the doctype. Does anyone got that doctype memorized? No, OK, no, I guess not. It was possible, right? You're a geeky bunch. Somebody here might have it memorized.

[24:47] This is the HTML4 doctype, and I don't keep this stuff memorized, because this is why we have text snippets, this is why we have Google, this is why we have templates, right? OK, what about if I'm writing XHTML1.0, which I have been writing for 10 years now? I've been writing this. Anyone got the doctype for that?

[25:05] Well, it's kind of an equally long string. But basically, you'll say this document is XHTML1\. That's essentially what it's saying. So in HTML5 to omit needless complexity, the doctype is simply `&lt;!DOCTYPE html&gt;`. That's it. Now, even I can remember that one.

[laughter]

Jeremy K: [25:27] I don't need to keep a text snippet for that. I have to say when I first saw this doctype, that this was supposed to be the doctype of HTML, I was somewhat taken aback.. I was like, "Wait a minute. Shouldn't the number five be in there somewhere?"

[25:40] I thought, "What are they saying here? Are they saying like, 'This is it? This is the only version of HTML there will ever be? We're going to get it right and there will never be a need for another version of HTML?' That seems so arrogant."

[25:53] But that's not what they're saying at all. Instead what you have to understand is why doctypes exist in the first place. It's not for browsers. Doctypes exist for validators. So the reason why I slap an XHTML1.0 doctype on the top of my document, is that when I feed it through a validator, the validator checks against that doctype. Right?

[26:15] A browser doesn't care. Let's say I'm writing HTML 3.2\. At the top of my document I put the doctype for HTML 3.2\. And then somewhere in my document, I use an element that was first introduced in HTML 4.01.

[26:31] What's the browser going to do? Is it going to not render that element, because it was introduced in a version of HTML later than the doctype I've specified. No, of course not. It's going to render the element, because of Postel's law, because of robustness. It's got to be liberal in what it accepts.

[26:47] So browsers are not checking against any particular format. Validators do. Validators care. This is the reason why doctypes exist.

[26:55] And because one of the design controls of HTML5 is it's got to be backwards compatible and future compatible, any future versions of HTML - and there will be. There will be an HTML6 and an HTML7, whatever.

[27:08] But they need to backwards compatible with the current version of HTML, which is HTML5, right? Hence having a version number in our doctype doesn't really make much sense, even to a validator.

[27:21] So I say that the doctypes aren't for browsers, they're for validators. That's mostly true. There is one instance where it matters to browsers what doctype you're using, and you're probably all familiar with it. It's not the reason why doctypes exist, it's a hack that uses doctypes.

[27:37] And that's when Microsoft were introducing CSS, kind of getting ahead of the standard, they tried putting CSS into their browser. They had their own box model. In some ways, a more intuitive box model than the standard box model. And then the standards came out and the standard box model was using it differently.

[27:55] What do they do? They want to support the standards, but they also have to maintain backwards compatibility with the old way they were doing things. How can they tell if an author means "I want to use standards, " or "I want to use the old-fashioned way"?

So the trick they came up with is a very clever hack: [28:08] to use the presence of a valid doctype as a trigger for standards mode rather than quirks mode. That was very clever, and that's generally what we do today. When we put a doctype on our documents, we're saying, "I want to use standards mode."

[28:25] But that's not why doctypes were invented. That's a hack that happens to use doctypes.

[28:30] So the six-million-dollar question is, hey, if I go ahead and slap doctype HTML on the top of a document and I feed that into Internet Explorer, is it going to use standards mode or is it going to use quirks mode?

[28:44] And it turn out this is the minimum number of characters necessary to trigger standards mode in Internet Explorer. And I think that illustrates that kind of fundamental approach to HTML5, that it's not about the theoretical benefits. It's not just about, "Wouldn't it be nice if authors had a nice, short doctype that was easy to memorize?"

[29:05] Yeah, that would be nice, but if it doesn't work in existing browsers, forget about it.

[29:10] So this great balance between something that's theoretically a good idea - a nice short doctype - and practically a good idea because it still triggers standards mode. The doctype is a good example.

[29:22] There are other examples of omitting needless complexity or avoiding needless complexity in the spec. In some of the previous version of HTML, HTML4.01, suppose I want to specify character and coding of my document.

[29:35] Well, the idea was you have the server send the character and the encoding in the heading, but you can also specify it at the document level. So, again, I wouldn't memorize this. I've got better things to do with my brain cells. But this is how you specify that I want this document to be utf8\. This is how you do it in HTML4.01.

[29:53] In XHTML1.0, you have to do a bit more, because as well as the meta element itself, you also have to declare it in the XML opening tag. And it turns out in HTML5, all you have to do is say, "meta charset equals utf8." Nice and short, and I can memorize that.

Once again, it turns out this works. It works not only in very modern browsers, in future browsers, this works today in all browsers. Which is turns out that when we were feeding these meta elements to browsers, that they were parsing them like this: [30:14] "Meta, blah, blah, blah, charset utf8."

[laughter]

Jeremy K: [30:35] That's essentially what a browser sees when it parses that string. And it has to be, because of Postel's law. We keep coming back to the robustness principle. But people get this wrong. And they simply say, "OK, I think somebody's trying to specify a character set. Oh, yeah, utf8."

[30:51] So that's just getting codified into the specs. Now it's OK to just leave out the "blahs" and just write "Meta charset equals utf8."

[30:59] And there are some other examples where it's not just about the idea of avoiding needless complexity, but the needless complexity can be avoided without breaking in existing browsers. For example in HTML5, if I'm linking off to a stylesheet, using the link element, I say, "rel equals stylesheet" and then I say "type equals text/css."

[31:20] Well, I'm kind of repeating myself. And it turns out for a browser, I'm repeating myself, but the browser doesn't need both things. The browser is fine if I say "rel equals stylesheet." Because it's going to guess that you're serving up CSS.

[31:34] So you don't have to include the type attributes, you've already said it's the stylesheet. You don't have to say it again. You can if you want. If you want to include the type attribute, go ahead.

[31:42] Likewise, if you're using a script element, and you say, "type equals text slash JavaScript, " the browser kind of knows that already. Because, frankly, what else would you be using on the web? If you want to use a different scripting language on the web, go for it. I don't think any browsers will support you, but you can have a type attribute if you want. But you can leave it out and the browser's going to assume you're using JavaScript. Avoiding needless complexity.

Another one: [32:10] "Support Existing Content." This is really important, because a lot of people think that HTML5 is all about the new shiny. It's all about what's coming in the future. How can we make the web better in the future.

[32:20] And it is. Obviously you have to think about the future and making the web a better place, but they have to think about the past. And remember, a lot of people on the WHAT Working Group group and WC3, these are browser makers.

[32:33] So they very much have to think about support existing content. This is the watchword of anybody who has had to build a browser. You have to support existing content.

[32:44] Let me show you the example of how HTML5 supports existing content. This is existing content. Here we have four different ways of writing essentially the same thing. There's an image element and there's a paragraph element with an attribute on it.

[33:01] The only difference is the syntax. So you serve any one of these four pieces of code, pieces of markup into a browser, the browser will translate it into the same DOM tree. No difference whatsoever. So from a browser's perspective, there's no difference between these four examples. In HTML5, you can go ahead and use whatever syntax you want.

[33:26] Now to us, looking at this, we kind of look at this and go, "No, no, no. One of those is right. Three of those, there's something fishy about that." Because I look at that, and I'm like, no, you should be quoting your attributes. We all should be quoting our attributes. Uppercase elements, really? Didn't we leave that behind 10 years ago?

[33:44] So I kind of get a bit of a queasy feeling when I see this is all now allowed in HTML5\. Because I've been writing XHTML1 for ten years now, and I've gotten pretty used to that coding style. But you have to understand, from a browser's perspective, this is all the same. It really doesn't matter.

[34:01] Does this make anyone else queasy? " Do you look at and go, "Ewwwghhhh, this is sloppy. This is bad." Is it just me? Am I the only one?

[34:09] But they have to support existing content. And existing content looks like this, right. And this is the way browsers already work, because of Postel's law, right?

[34:18] Some people have said, "This will not do." We need some kind of trigger within the language to say the author knows what they're doing. They want to use one particular syntax, like the XHTML syntax for example, rather than a different syntax.

[34:33] And I can see why people want that. But I disagree that it needs to be in the language itself. Because what we are talking about essentially here is a coding style or a writing style, rather than being syntactically correct.

[34:48] So I think what's needed for professionals like us is lint tools. Because we have lint tools for other technologies we use.

[34:57] For example, with JavaScript, JavaScript is another example of kind of messy, sloppy language that's powerful because it is messy and sloppy. There's many different ways of writing things. So, in JavaScript, you're supposed to put a semicolon on at the end of every statement, but you don't have to, because JavaScript will perform semicolon insertion, which does sound quite painful.

[laughter]

[35:18] We have tools like JS Lint, JSlint.org from Douglas Crockford, where it says right there on the page, "JS Lint will hurt your feelings." But, it's a really good tool, because you can take perfectly valid JavaScript, run it through JS Lint, and then you say, "OK, this JavaScript is valid, but you're doing it wrong." Right? "This coding style, I don't like it, I disagree with it; it's not good."

[35:42] That's actually really, really handy when you're working in a team, to have one coding style you can all agree on. So, while I think that if you're working in a team -- actually even if you work alone -- you need to settle on one syntax, no one syntax is superior to another, in terms of browsers parsing it. But, I do think that it's important at least as professionals, we decide that this is my coding style.

[36:07] But, I don't think that that needs to be in the language. I think that the lint tools helps solve all of that, and there are now lint tools. If you go to HTMLlint.com, you can run your HTML5 documents through it, and it will check for things, like have you coded your attributes, are the elements lowercase? You can click check boxes to say what you want.

[36:20] So, it's not a return to sloppy markup if you don't want it to be, right? As I said, they have to allow this in HTML5 for the very simple reason that this is what browsers allow, and it all comes back to Postel's Law as well. We keep coming back to Postel's Law.

[36:38] Another design principle in HTML5 is to solve real problems. It seems obvious, and yet there are plenty of formats and specifications out there that, in my opinion, are solving theoretical problems, rather than real problems. HTML5 is all about solving problems that people have today, solving the pain points.

[36:58] Let's do an example. This is one that I think some of you might be able to relate to. Let's say that in HTML4 or XHTML1, I've got this one on my piece of paper, a block of content, and I want the whole thing to be clickable. But, it's got a headline, it's got a paragraph, maybe it's got an image in there, too. I want the whole thing to be clickable, so now I've got to use three link elements.

[37:09] So, I open up my headline, H2, for example, and I got my text and that's what I wrap in the A element. Then I open up a paragraph. Then I open up another link and I wrap that, put the text in that.

[37:29] Well, in HTML5, what I can do is simply wrap the whole thing in an A element. OK, it has the block level elements, but yet, I can wrap them in an A element. This is great. I know this is great, because I've have been in the situation where I needed to do this and I, for one, welcome our new HTML5 overlords.

[37:48] It's solving a real-world problem. I bet you've come across this pattern before, as well. And once again, here's the great part about it. This isn't something that now browsers just need to go out and start supporting. This is something that works already in browsers, because, frankly, people were doing this kind of stuff anyway, even though it was never legal until now.

[38:06] Essentially, all that HTML5 is saying is, "This thing that a lot of people have been doing for years, that's actually allowed. You can do that now."

[38:14] This design principle is the most buzz-wordy, "Pave The Cowpaths." It sounds like something you'd hear at a business meeting. You run it up the flagpole and pave the cowpaths.

[38:23] But, it's actually a really good design principle because, essentially what it's saying is, when you're deciding what to tackle, where are the pain points, it is look at where people are already finding hacks and ways to patch these problems today. That's where you should concentrate your efforts. Right? Look at where people are already coming up with solutions.

[38:44] So, a good example of paving the cowpaths is the new semantic elements we get in HTML5\. There's not that many. It's not infinitely extensible, which I think is a good thing. It's basically a handful. But, they're good. They're good, for headers, or footer, section, article.

[39:00] And a lot of these will be familiar to you. The names of these will be familiar to you already, even if you're not using HTML5, because you have been using class names, like "class equals header, or heading or head. Right? "Class equals footer or foot, " right? Or IDs, maybe you're saying, "ID equals header, ID equals footer." These are already fairly familiar things.

[39:22] So, for example, today, you might be writing a document like this, where you've got ID with div, "ID equals header div, " ID with navigation, stuff like this. But, if it's HTML5, you could go swap out with these new elements.

[39:32] Then, talking about these new elements, this is the way it's often presented, "Oh, look; it's great. You can swap out these digital IDs for these new HTML5 elements." And that's true; you can. These elements work at the document level like this, and that's good. But, if that were the only reason why these elements were introduced, that would be a wasted effort.

[39:52] While you can use these new elements this way, at the document level as a replacement for IDs, it's much more useful, in my opinion, to think of them as a replacement for classes; because the real power comes in that you can use these things multiple times per page, not once per page.

[40:08] So, yes, you've got a header for your document and you've got a footer for your document, but you also have a header and footer for each section within each your document. And each section might have another section that's in it, and that could have header, and that could have a footer, right?

[40:21] So, it's these four elements - section, article, aside and nav - that are the really powerful ones, because they introduce a whole new content model that hasn't existed in any previous version of HTML, this idea of sectioning content.

[40:36] Up to now, we've used divs to group things together, but divs are just like any other element. They don't have any extra semantic meaning, where section article, aside and nav are essentially saying that this is a like document within a document. If it's inside one of these elements, it will have its own outline, it could have its own heading, it could have its own footer.

[40:55] The way to think of this is basically that section is the most generic one, of thematically related content. Then, article is a specialized section. Aside is a specialized section. Nav is a specialized section. Whereas today, I might have a markup that looks like this, we're using classes to delineate the different parts of a part of a page, using divs, where I have the meta content about who wrote this piece of content. We have some links at the bottom, stuff like that.

[41:24] With HTML5, I basically can say that this is a document in itself, by using sectioning content. By using something like section or article or aside, I can say that this stands alone. I can use header; I can use footer. Notice also that the footer doesn't necessarily have to be at the bottom, right?

[41:41] The important thing about footer, and aside and nav, is the semantics. It has nothing to do with positioning. We think with the word "footer, " we think that that comes at the bottom. When we think of aside as a side bar, but if you look at the specification, it's all about the content.

[41:56] So, the content that you put in the footer is things like the byline and who wrote this, and that's the element that you use. It doesn't say, "Must come at the bottom of the document or the bottom of your section."

[42:06] The really interesting thing here, though, is not that I've swapped some divs with classes for some new elements, but the fact that I've swapped out an H2 element for an H1\. Shock, horror, what if I already have an H1 on the page? The Google siren will go off, and my SEO will be terrible and the world will end.

[42:25] You can have multiple H1s in a document. This is not something new to HTML5\. You've always been able to have multiple H1s in a document - shock, horror.

[42:33] I've met working professionals on the Web who have thought for years that it was in the specification that you could only have one H1 per document. There's been a lot of SEO snake oil pedaled on this subject. SEO's got a lot of dogma attached to it. Whereby dogma, I mean belief without data.

[42:49] The dogma has traditionally been, "Oh, if you ever put more than one H1 on the page, you will die."

Audience: [laughs] [42:54]

Jeremy K: [42:56] In HTML5, every time you open a new piece of sectioning content -- section, article, aside, nav, whatever -- you can begin with H1 again, rather than having to stick with whatever level you were at - H2, H3, whatever it was. This is incredibly powerful. This could really revolutionize content management, the fact that you can now literally think about your chunks of content as stand alone content that can be taken out of context.

[43:22] Now, depending on the context you find itself in the page, this H1 would have the role of being an H2 or an H3, depending on where it finds itself in the document. It will be a little weird to get your head around at first, but I actually think that this is possibly the most powerful part of the new semantic elements in HTML5, is that they are literally stand alone elements. We get this whole new level of headings in there. I can have a document with a section in it. That section can have a section within it or an article. Sections in articles, articles in sections, sections in sections, articles in articles. Each one could have H1s through H6s all the way down. So there's like H-infinite at this point.

[43:57] But when you're dealing with your content, your content management system, they are properly standalone chunks of content, and that's very powerful.

[44:04] This is not some wacky idea that the WHAT Working Group came up with or the W3C came up with recently. Here's an email from Tim Berners-Lee from 1991, an email to Dan Connolly. He's explaining this HTML thing. And he says, "You know what I prefer instead of H1, H2, and all that stuff? I'd like it to be this nestable section element, a generic sort of H element, so we can just nest our levels within them."

[44:31] Now, we don't have this generic H element. We're still using H1, H2\. That's because we're supporting existing content. But we're finally seeing this idea realized 20 years later.

[44:43] Here's a principal that I'm sure you're all familiar with already, which is degrading gracefully. We've all been doing this for years anyway. With progressive enhancement, we get graceful degradation for free.

[44:54] One of my favorite examples of this principal in action in HTML5, is the way that forms have been enhanced in HTML5 using the type attribute. There's a whole bunch of new values that you can give the type attribute in HTML5, like number and search, range, email, all this stuff.

[45:11] The great thing is what browsers do when they encounter this. Existing browsers, not future browsers, existing browsers that don't understand this stuff, the way they degrade gracefully is whenever they see a type value they don't understand, they just treat it like text.

[45:25] You write input type equals "foo", input type equals "bar", and every browser out there will say, "Eh, he probably meant text." So that means you can start using this stuff and be secure in the knowledge the browsers that don't understand it will simply treat it like input type equal "text" -- a great example of browsers practicing graceful degradation.

[45:44] So this type equals "number" for example, suppose you have an input that requires a number. You could say input type is number, and then a browser that understands that input type, you might get a nice control like this little spinner thing. Right? And then in a browser that doesn't understand it, you just get a text input, which is what you would have used anyway. So why not just say, input type equals "number", and you get that spinner for free?

[46:07] You can have min and max and all that stuff in there as well, but it degrades gracefully. That's the key issue.

[46:13] Input type equals "search". You might as well start using it, because in a browser like Safari you get this nice operating system level search control and a little X you can click away the search term with. And in all other browsers you just get a text input, as if it were input type equals "text", which is what you would have used anyway. So why not just say input type equals "search"? It doesn't hurt, right?

[46:35] And new attributes have been added as well. You've got this placeholder attribute you can throw in. You know this pattern, right? You've got some text that's already inside the input. Not a label -- a placeholder and a label are two very different things. It's an example value that sort of grayed out. You click in there and it goes away. You click out and type again, it'll come back.

[46:54] We can hack this stuff together with JavaScript today, but now with HTML5 you just use a placeholder attribute.

[47:00] And what you can do as well, if you still want to do it with JavaScript for browsers that don't support this, is it's pretty easy in JavaScript to test -- does the browser understand the placeholder attribute? If it does, just step back, get out the way, don't do anything. If it doesn't, then include your JavaScript to mimic this functionality.

[47:18] Now, I couldn't talk about HTML5 without bringing up this subject -- HTML5 versus Flash. You may have heard about this. You may have read about this somewhere. And I really don't get it. I'm really puzzled by this whole battle that's supposedly going on.

[47:36] First of all, when people talk about HTML5 versus Flash, they're not talking about HTML5 and they're not talking about Flash. They are talking about a subset of HTML5 and a subset of Flash. Specifically, they're talking about video. So whenever you hear, "HTML5 versus Flash" they probably mean HTML5 video versus Flash video.

[47:55] And another thing, this framing of it as HTML5 versus Flash -- like you have to choose. Which side are you on? That's just not the case. Because of the way that the spec has been designed, you can have your cake and eat it too.

[48:09] So this is the way that it works with the new video element -- a really nice element, really simple, elegant design. You have an opening video tag, a closing video tag, and in-between you put your fallback content. Fallback content, not accessibility content, fallback content. So this is for browsers that don't understand the video element.

[48:27] So what would you put, for example, for your fallback content? Well, you can put a Flash movie. You can have HTML5 video and Flash video. You don't have to choose. It's not quite as simple as that, of course, because here I am sending in H264, and some browsers will understand that. Other browsers don't understand that.

[48:47] Don't get me started on the whole formats thing, because I'll get really upset. Not because of the technologies. I don't care about the technologies, but the fact that patents and lawyers and intellectual property and other enemies of the web are getting in the way of me building better websites.

[49:02] But actually what you have to do is -- put your fallback in there as well -- you can have different formats. And you can specify these different formats using the source element rather than the source attribute if you want.

So here I've kind of got four different levels going on. I got like: [49:17] OK, if the browser understands the video element and it understands H264, it gets that. If the browser understands the video element and it understands Ogg, then it gets the second one. If the browser doesn't understand the video element, then I'll try to give it Flash. If the browser doesn't support the video element or Flash, then I give it just a download link.

[49:37] So it's kind of like you've got Inception going on right here. You've got different levels that you can go down.

[49:45] I think it's a good idea to hedge your bets and start up your video both ways. If you're only serving video using the video element, you're kind of shooting yourself in the foot, I think. But if you're only serving your video with Flash, you're kind of doing an equal disservice. You should probably do it both ways.

[50:04] Why would you want to do this? Well, suppose you've got some sort of handheld device that doesn't support Flash. Maybe you want to make sure they get your content too, right?

[50:15] The reason why it's such a problem, that we have to have these different formats, and the reason why Flash has been so successful with video and audio (everything I've said about video applies to audio), is down to another design principal. And that's the principal of Metcalfe's Law. Now, he was talking about telephony networks when he came up with this law, but it applies to pretty much anything. That the value of a network increases, basically the more people that are using the network. So everybody uses Facebook because everybody uses Facebook. It's not that it's inherently valuable, but the fact that everyone's on it is what makes it valuable.

[50:52] So a good example of Metcalfe's Law would be whoever bought the first fax machine. Why did they buy it? It was pretty useless. But as soon as other people started buying fax machines, then it started gaining value.

[51:04] So when you've got competing formats and different ways of encoding things, you're not getting the benefit of Metcalfe's Law. That's why I get upset that we have to encode our video in different ways. I can't just serve it up one way to the browser. And that's why Flash has been very successful in the video/audio areas -- that they can serve up one thing to any browser and have it mostly work. Basically makes use of Metcalfe's Law.

[51:30] The final design principal that I'll leave with is my favorite. There's no code examples to show you for this one, because it's much more philosophical -- the priority of constituencies. And this is really about working together. This is really solving the problem of when we've got an issue, when we've got a problem we need to tackle -- when we've got the W3C wants to do it one way and WHATWG want to do it another way, or this person thinks it should be done this way and this person thinks it should be done the other way, here is the flag in the sand to say this is how we'll approach the problem.

[52:00] In case of conflict, you consider users over authors, over implementers, over specifiers, over theoretical purity. So theoretical purity, that's like building the best format we possibly can do. Specifiers are the working groups, WHATWG, W3C. Implementers are browser makers. The authors, that's us. And look at how high up the chain we are. We're second only to users, as it should be. The users come first. Our voice is very, very important in this process.

[52:31] So Hixie has stated often as features being proposed and debated in HTML5 that if there was a browser manufacturer who said of a feature, "We would never support that feature. We will never implement that feature in our browser, " then that feature's coming out of the spec.

[52:49] Because if we put that feature into the spec anyway, then the spec will be fiction. Right? Because the implementers are refusing to implement it.

[53:00] Because, according the priority of constituencies, we are higher up the chain than the implementers, if we have a problem with something in the spec, if we think we disagree with this, we will never implement what you specified in our documents, then equally it should come out of the spec. Because our voice should carry more weight.

[53:17] I like that. This basically makes us very powerful. And I think that's a good thing.

[53:23] I think this is probably the most important design tool we have, because it is acknowledging that you have to have design principles when you're building a format, when you're building software. This is just the way that the worlds works.

[53:35] It might seem obvious, users over all authors over implementers over specifiers. But if you think about other specification, like XHTML2, it was the complete opposite way around. Theoretical purity was the most important thing.

[53:47] And the users, what with the draconian error handling, came very much at the end of that chain. I'm not saying it was wrong, but it was a very different philosophical approach.

[53:56] So I think no matter what you're doing, whether it's building a format like HTML5, whether it's building a website, whether it's building a content management system, having design principles is really, really useful.

[54:07] I'll give you an example. When the Drupal community got in touch with Mark Boulton and Lisa Reichelt to redesign the Drupal interface, they sat down to come up with the design principles that would drive it. I don't mean that they sat down and scribbled them down on a piece of paper, they took a long time - weeks - to boil it down into these four design principles they were going to operate with.

[54:28] And actually when I was talking to Mark about this, it's really those two. They could have boiled it down even further to those two in the middle that you would design for the 80% and privilege the content creator.

[54:36] That's good, taking a stance. And we are going to value the content creator more than other people in this project. And that's an important thing to remember about design principles, because a lot of the time the idea of the design principle is that, look, you're not going to please everyone.

[54:50] And the whole point is, we don't aim to please everyone. We're deciding who is valuable. And they decided that the content creator was the most valuable thing.

[54:57] And then this other design principle of designing for the 80%. It turns out this is really common design principle. It's common in nature. It's called the Pareto Principle. Pareto was an Italian economist, and he noticed this ratio, the 80/20 ratio. 20% of the population have 80% of the wealth. It gets mapped onto a power law distribution that shows up everywhere in nature.

[55:20] It turns out when you're writing software, when you're building something, it's kind of the same. You can achieve - with 20% of the effort, you can hit 80% of the use cases. Now the final 20% of the use cases is probably going to require 80% more of the effort.

[55:33] Sometimes it's a good design principle to say that we're going to design for that 80%, because we know we can do it with 20% of the effort. Microformats, for example, very much use the Pareto Principle, that they're solving some use cases and they're not going to worry about the edge cases. They know they're not going to please everyone, but that's not what they need to do.

[55:53] They really encapsulate - they've got a whole bunch of design principles and it's worth reading all of them, but it's really encapsulated by design for humans first and machines second. Again, it might seem obvious to you and me, but there are examples of other formats where it's the other way around, where the ease of parsing for machines is more important than the ease of authoring for users.

So I think it's really good to look at these design principles that other people have out there. And whatever you're doing, think about what the design principles are and nail them to the wall. Basically, have a URL where you publish this stuff, like the Mozilla Foundation has done: [56:11] these are the design principles behind Mozilla. I think it's a really good thing to do.

[56:27] And there's a design principle that, it seems to me, had driven a lot of really good projects. It's driven the web itself. And I think it's certainly a philosophy that's behind HTML5\. That's a design principle you've definitely heard of, and that's rough consensus and running code.

[56:49] It keeps cropping up over and over. And for me, it kind of encapsulates what the web is about, and it encapsulates the way that HTML5 is heading. So this is probably the one that I would nail to the wall in my office and say this is the design principle of the web. Rough consensus and running code.

[57:06] OK, I'm out of time, so I'm going to leave it there. If you have any comments about this, you can hit me up on Twitter. I sometimes blog about this stuff on adactio.com. A shameless plug, yes, I have a book out. But thank you very much for listening to me.

[applause]

Jeremy K: [57:38] Oh, do I have time for question? Cool. I didn't realize I had time. There's time for questions. I love questions. Anybody? So shy. We have microphones. OK, the microphone is coming to you, sir.

Audience: [57:54] Member: If you're using HTML4.01, are you allowed to use HTM5 elements in there? Or it doesn't make sense, like will the browser support it? Should you really use HTML5, if you want to HTML5 elements?

Jeremy K: [58:11] I would recommend using doctype HTML, rather than a legacy doctype like 4.01\. It's not because of the browser support, because as I said, browsers support whatever they can.

[58:22] I guess I should define what I mean by support here. With these new semantic elements - section, article, header - you can go ahead and use them in the browsers and the browsers will render them fine and style them fine. Except for one browser that we're all familiar with. But a little bit of JavaScript will help with a little kick up the ass and then Explorer can understand them as well.

[58:41] But it's not so much that these browsers understand what the elements are, it's just that these browsers allow you to use any odd elements you want. You could write a foo element and a bar element and you could still go ahead and style it, and the next version of Firefox would properly understand HTML5 and would understand these elements.

[58:58] So you can go ahead and use a header/section/article in HTML4 if you want, but then your document would be invalid, because when you run it against a validator it will say, "No, I have no idea what a section is, no idea what an article is."

[59:10] But the browser won't complain. The browser will parse it just fine. It depends on what you want to do. I would recommend changing the doctype as well, just so you get the nice green tick from the validator.

[59:22] You can, if you want, just start using the stuff without changing the doctype, but I would recommend changing the doctype. That's the minimum that you do, is change the doctype. You can start messing around with the stuff as you feel comfortable with it.

[59:34] But here's something else you can do, if you're still using HTML4.01, and you want to get the drift of the semantics of these new elements. You don't necessarily have to start using the new elements themselves, but you can take those names and use them as class names.

[59:47] This is what I'm doing now with a lot of client work. In my personal work, I'm just going ahead and using section and article and nav, aside, header, footer. But in client work, maybe I better ease off a bit on this. I will still use divs, but I will say div class equals section. Div class equals header. Div equals footer. So I'll reuse the vocabulary with class names.

[60:08] It's kind of handy, because a lot of times you're handing off these documents to be turned into some server-side programmer that has to build the actual app. I need to document why I've chosen these class names. And by using these class names from HTML5, I have existing documentation, which is the HTML5 spec.

[60:25] I simple say, if you want to know what section means or what article means, here's a URL that explains the semantics of it. I'm not using the element, I'm using the classes, but the semantics are important.

[60:34] So that's an idea. If you don't want to dive into using these new elements, you maybe just use the class names instead.

[60:42] Do we have another question over here? There's a microphone coming your way.

Audience: [60:48] Member: You touched on input types there. When you use an input type that's not recognized by the browser and you interrogate the input type, it reports type text.

Jeremy K: [60:58] That's correct.

Audience: [60:59] Member: In CSS, when you style it with an attribute selector, it styles with the original type that you specified. What's going on?

Jeremy K: [61:09] I guess there's different parsing rules for the CSS HTML. I don't know, is the answer to your question. It's a good question. I guess it's just different parsing models, the way the CSS is parsed, the way the HTML is parsed.

[61:21] But the fact that you can query with JavaScript, does the browser think this is input type number, input type name, is actually really, really handy. Because then you can use a JavaScript fallback depending on whether it responds with input type text or not. So that's actually pretty handy.

[61:37] But I don't know why CSS does things differently to HTML. I'm not a browser maker. We have browser makers in the room someplace, so that would be a good question to ask them, why it works that way. But it's a good question.

Audience: [61:49] Anne van Kesteren: I can answer it if you want.

Jeremy K: [61:50] Hey, I hear a voice from the audience.

Audience: [61:53] Anne: The difference is that in JavaScript, you probably used the IDL attribute, or the property, and you don't actually query the actual attribute value. Because if you would use getAttribute, you would actually get back search instead of text.

Jeremy K: [62:06] That's a good point. I'm going to do a quick live coding. This is going to go horribly wrong. So 99 times out of 100, there's no difference between using getAttribute and using just a dot syntax. Say "image.source," 99 times out of 100, it makes no difference whether you say "image.source" or "image.getAttribute('source')." That's going to be the same thing 99 times out a 100.

[62:41] With the input types, we can use the fact that this is - in some cases it's not quite the same. What we do is, let's say we create a new input element. Everyone?

[off-mike comment from the audience, probably saying the screen isn't visible]

Jeremy K: [62:57] Oh, shoot. Hang on. Sorry. Thank you for pointing that out.

[63:11] Let's say we create a new input type. Let's see if I get this wrong. And now I say "test.setAttribute." I'm not saying "test.type, " but I'm saying set the type attribute to be whatever type we're testing. Let's say input type equals range. OK?

[63:33] And then we can query is test.type is equal to text. Then we know it's time for some JavaScript fallback. That goes here. This code is probably horrible. I can't believe I'm trying to do JavaScript in the same room with PPK looking at the screen.

[laughter]

Jeremy K: [63:59] But you get the idea. This is one of the few times where the fact that there's a slight difference between "getAttribute" and "setAttribute" and the dot syntax, is important. So that's a good point. If you were to query in JavaScript "getAttribute('type')" you would get the same report as CSS is doing. Whereas what you're querying is probably ".type" and you're going to get text. I think. I hope I've explained that reasonably well.

[64:29] Any other questions? I hope that helps clear that up. Who's got the microphone? I'm somewhat blind up here. We've got the microphone coming your way. And there you go.

Audience: [64:44] Member: Hello.

Jeremy K: [64:45] Hello.

Audience: [64:45] Member: When you want to start using these HTML tags for your website, will it improve your position in the search engines?

Jeremy K: [64:57] I'll tell you what improves your position in search engines: write good content. It's crazy, but it works.

[laughter]

Audience: [65:04] Member: I guess that's the first place.

Jeremy K: [65:05] And you know what, everything after that is secondary. It's not secondary, it's tertiary. It's less than tertiary.

[65:10] The most important thing is you've got good content. Structure it well, obviously. The fact that you're using headings at all in a document is good. And the fact that you're using semantic markup is good. But most importantly, as we call it now, the fine details of whether this element or that element gets ranked more by Google--it changes every week anyway. And I know, yes, I'm pointing out every section or article can start with H1\. Oh my God, what will Google do? I will point out that Ian Hickson does actually work at Google, so I wouldn't worry too much about it, frankly.

[65:43] Look. Here's my approach to SEO. If you're thinking in terms of SEO, search-engine optimization, you're doing it wrong. You want to be thinking in terms of people optimization, because Google practices people optimization. So, when someone enters a search term in Google, Google is now thinking "What is the best document, what's the best resource I can give to this person who's trying to find a result for this search?" And so it thinks in terms of what people want. When it's analyzing the documents, it's thinking about "What do people want out of this document?"

[66:14] So when you're creating your documents, instead of thinking about what does Google want, because Google is thinking about what people want, why don't you just cut out the middle man and think "What do people want?" And if you do that, you'll get good SEO anyway, because Google is also practicing this people optimization. So cut out the middle man. Don't think about Google. Think about your content, think about your users, think about using the best semantics available, and by a happy coincidence, you will get good SEO from that.

[66:43] As for the fine details of which element is better than the other elements, it doesn't matter nearly as much as having relevant, well-written, well-structured content. What's that excellent, excellent phrase you have in Dutch? Mierenneuken, right?

[laughter and applause]

Jeremy K: [67:00] That's what a lot of SEO is. I've got to use that. That was awesome.

[laughter]

Man 1: [67:07] Jeremy?

Jeremy K: [67:08] Yes.

Man 1: [67:09] One more question, please.

Jeremy K: [67:09] One more question. One more question. Who's got a hand up? I can't see a thing. Run, microphone man, run.

Man 2: [67:23] Hi. You mentioned that you don't use HTML5 on your own websites for customers. But you've been talking about using it today for about an hour now. Why is that?

Jeremy K: [67:34] Yeah. Well, I use the doctype, obviously. No problem using it. I was talking specifically about the new semantic elements: section, article, nav, aside. I'm instead using div class equals"section", div class equals "article".

[67:45] It depends on the client, but there's a very, very, very, very, very small use case where they might not get the styles. And that is, like I said, you can style these elements in every browser. But to style them in Internet Explorer, you'll have to use a little bit of JavaScript. Right? So, for some bizarre reason, you have to tell Internet Explore that an element exists by saying document.createElement("section"). Now you can style it in Internet Explorer. It doesn't make any sense, but that's the way it works. And Remy Sharp has written a nice little piece of code which encapsulates all of this, and it's on Google Code. He just pointed it out. Always a good one.

[68:20] So there's a very, very, very, very, very small possibility of your audience using Internet Explorer, less than nine, and having JavaScript switched off, in which case they then won't get the styles that you apply to any of these new elements. So for that very small use case, I'm a little bit more cautious about using the new semantic elements.

[68:40] But I absolutely use HTML5 in my clients' sites, because what I'll do is maybe I won't use section, article, nav, and aside. I'll use div classic equals "section", div classic equals "article", and so on. But I will start using the new input types. I'll use input type equals "search", because why not? I will start using the placeholder attribute. Why not? I will start using ARIA roles, right? You can use ARIA roles in any version of HTML, but in HTML5, it's valid. The role attribute is valid, so you can go ahead and start using ARIA roles in your document. Frankly, for that reason alone, it's worth switching over to using the HTML5 doctype, in my opinion.

[69:17] So, it wasn't quite correct to say I'm not using HTML5 on client sites. I am using HTML5 on client sites. I'm not necessarily using the new structural elements, just because there's that potential for a small portion of the audience to not get the styles for those new elements, if I'm using them in a styling place. I don't have to necessarily use them in a styling place.

[69:37] OK. I think I'm out of time?

Man 1: [69:38] Yeah.

Jeremy K: [69:39] OK, I'm out of time. Thank you.

[applause]

转自：[http://fronteers.nl/congres/2010/sessions/the-design-of-html5-jeremy-keith](http://fronteers.nl/congres/2010/sessions/the-design-of-html5-jeremy-keith)

参考：[http://developer.51cto.com/art/201103/247880.htm](http://developer.51cto.com/art/201103/247880.htm)