**Samuel Schlesinger:** Let's see here. All right, I think we have quorum. So I'm going to get started here. Um, so this is a Privacy Pass interim, first one we've had in 2026. Um, I'll put up the Note Well here, just so everybody is reminded that we are still operating under all IETF processes and policies with regard to IPR, anti-harassment, behavior, etc. So I think most people are familiar with it, but if not, you can scan this QR code pretty quick and get a refresher. Um, but I'll move on to the next slide now, where we talk about the agenda. So we have some updates for ARC (draft-ietf-privacypass-arc-protocol / draft-ietf-privacypass-arc-crypto), and then some updates for ACT. An update with respect to the PACT workshop, and Thibault has some work on the reverse flow draft (draft-ietf-privacypass-reverse-flow). Um, are there any requests to modify the agenda somewhat?

**Dennis Jackson:** Yeah, it'd be great to do Thibault's before the ACT and PACT workshop one, because I think reverse flow is good context for me to have in mental scope for everyone when I do my presentations.

**Samuel Schlesinger:** All right, we can do that. Anybody have any concerns with that? Sounds good. Um, yeah. Oh, Robert, did you have...?

**Raphael Robert:** Hi, yes. Sorry, I will just take one minute of your time. Can we add a status update to the batched tokens draft (draft-ietf-privacypass-batched-tokens)? I just want to ask where we stand on that.

**Samuel Schlesinger:** Yeah, we can chat on that now. Um, so I think that lies with the chairs. Ben, did you have...?

**Benjamin Schwartz:** Uh, yeah. I was just going to jump in for this slide.

**Samuel Schlesinger:** Okay. Yeah, we'll cover the metadata extensions and batched tokens as well, so...

**Benjamin Schwartz:** Sure. Thanks. Uh, yeah. So, the public metadata (draft-ietf-privacypass-public-metadata-issuance) and the auth scheme extensions (draft-ietf-privacypass-auth-scheme-extensions) drafts um, went through a working group last call last year, and they they were approved with some changes needed. And those, uh, not all of those changes happened in a timely fashion. Uh, and there's been some slow-moving back-and-forth since then. Uh, and also, the chairs got some input that it was unclear whether these drafts were still relevant. So we sent that to the list and asked for input on whether we should be continuing to move forward with these drafts. And we did get a couple of comments so far supporting continuing toward publication for these two drafts. Um, so if you have comments on that, please send them to the list, uh, and help us figure out what the right final status is for these drafts. Um, but in any event, there are—we are going to need new revisions of both of these drafts because there are some pending changes in GitHub, committed or in pull requests, that need to be resolved before we can move forward regardless. So, uh, if you're involved in these drafts, please um, please take a look at those pending changes and uh, press publish if that's all that's needed. Um, and if you have thoughts about whether these proposed standards are still relevant, um, and should proceed through IETF publication, uh, please comment on the list. Thanks. Uh, Joe, maybe you can um, talk about batched tokens.

**Joseph Salowey:** Yeah, so for- for batched tokens (draft-ietf-privacypass-batched-tokens), the the action item was with the chairs. Uh, recently, a- I believe, a- a new draft was published. Um, we just need to take a look at that and- and make sure that there's no uh, changes that would go against where we were at. I believe we had passed working group last call a long time ago. Um, so I think we just want to make sure we're still within that consensus, and then I hope we can move that forward. Um, does that answer your question, Robert, or did you- or did you have uh, a more uh, specific question? Yeah, okay. All right. Um, so now we'll move on to the main part of our agenda. Uh, what are we doing—Chris asks, "What are we doing with the expiration draft (draft-ietf-privacypass-expiration-extension) given that it's the first user of extensions?" I do not know offhand. Probably we should uh, look at moving that forward, but I think there was a question as to whether people wanted that use case. Ben?

**Benjamin Schwartz:** Yeah, so I think um, you know, the the same- a similar situation applies here um, but that draft, I believe, has not entered working group last call. So, uh, we- we had originally um, set up a sort of situation here where the- we- we felt that if we adopted the expiration draft, that was sufficient evidence that the public metadata and extensions drafts were necessary and useful to close them out and move forward. So those two could go through to publication, while we continued to work on- on the expiration draft. Uh, the adoption was enough to confirm the use case. Um, so I think uh, yeah, it would be very interesting to know whether there's still interest in the working group in that specific extension, in addition to the question of whether there's general continued interest in extensions and public metadata.

**Samuel Schlesinger:** Yeah, so I think if- if people want to respond to Chris's question about what use cases remain, we can sit on this topic just briefly a little bit more um, but we probably do want to have this discussion on the list.

**Christopher Patton:** I can ask the question on the list. Um, like the- the- the approach that most working groups take nowadays is like, if there's no one using uh, or implementing a particular thing, we should just park the draft and wait for that, like, use case to come about. Um, my understanding was that the expiration was, like, the- the use case that was motivating this um, and uh, so I don't know, I'm not really interested in doing work for the sake of doing work. We should, if there is someone who uh, has a use case for this, that's great, but like, let's- let's try to assess that out.

**Benjamin Schwartz:** Yeah, so we did get two comments on the mailing list uh, that indicated that these two drafts are implemented and uh, running in production systems. Uh, I saw that, but like, these two drafts are like, not important. What's important is the extension you're actually negotiating and which actually provides public metadata. So like, it's great that they are—yeah. It's not clear to me what that—what the- the deployment or deployments in question are actually putting in the public metadata. I imagine it might be the expiration extension, but I don't know. I'll ask.

**Samuel Schlesinger:** Thanks. All right, um, let's move on to our uh, regularly scheduled agenda. And uh, let's see. Whoops. I believe—so, we were going to do—so, Chris or Kathy, I don't know if you had proposed any slides. Do you have any updates uh, for ACT that you wanted to give? Okay. Chris says, "No updates. PQ is the update." So, we will move on to the late binding with PQ unlinkability. And uh, I believe Chris Patton, I can give you control of the slides, and you can take it away.

**Christopher Patton:** Okay. Hi, everybody. Sorry, let me adjust my headphones. Can everyone hear me just fine? All right, thanks Thibault. Okay, um, all right, um, where do I start here? So, um, okay. All right, so um, okay. All right, so um, okay, so I think, as everyone knows, um, Privacy Pass um, as it exists today, so Blind RSA and VOPRF, these um, have, in terms of their post-quantum security, it's sort of a mixed bag. So, um, on the one hand, they're vulnerable—they're secure against like, store-now-decrypt-later style attacks where an attacker who sees like, some presentation in the past wants to be able to link it to—try to link it to an issuance. This is impossible with both Blind RSA and VOPRFs, um, given how they provide their- their privacy guarantees. Uh, uh, so that means even after a quantum computer is built, um, these things remain private. They are, of course, vulnerable to forgeries um, because the- the unforgeability of these tokens is sort of based on computational assumptions that we know uh, can be broken by a quantum computer. So, um, the reason I bring this up today is, um, kind of two things. One is, during the adoption call for ARC (draft-ietf-privacypass-arc-protocol / draft-ietf-privacypass-arc-crypto), we—there was, I think there was general consensus that we don't need to wait for ARC to be fully—to be—it's never going to be fully PQ, um, but we thought—we talked about whether it should be at least PQ private. Uh, I- I- I was one of the people that said, uh, "Let's not worry about like, any PQ requirements. Let's not let that block adoption." Um, I've come around to a different view, and part of this is because of um, several companies, including my own, have kind of updated their- their timelines for migrating to PQ. So, my- my personal view, and I think this view is shared by others, is that um, we need to be developing post-quantum alternatives for Privacy Pass. Um, I think there are some solutions on the horizon. They're bigger, just like, you know, digital signatures are bigger, um, but um, I think we will see solutions be developed in the next year—year—year or two. But in the meantime, um, but in the meantime, um, I think anything we- we- we design today should be at least PQ unlinkable. Uh, Martin asks in the chat, "PQ private or PQ unlinkable? I mean PQ unlinkable" specifically. Um, sorry, that was a little—a little rambly, I'm—I'm sort of changing context here. Um, okay. So, Blind RSA, VOPRF, they're—they're—they—they kind of meet this goal. They're—they're unlinkable to a quantum attacker because of the techniques—the information-theoretic techniques they use to—to provide privacy. ACT is in a similar boat. So, there is um, a nullifier that is revealed during presentation um, uh, for double-spend protection. During issuance, the uh, issuer only sees a commitment to this nullifier, and that commitment is perfectly hiding. Even though we're like, working with elliptic curves, this equation we see here um, for random $r$ perfectly hides, prevents any—any attacker, even—even a quantum attacker, from learning—learning $K$. Um, there's also, but of course, there's like, there's obvious attacks against uh, uh, a forgery, forgery, uh, specifically, cracking the issuer's algebraic MAC key. Um, and as I already alluded to, ARC is not quite in the same boat. So, um, ARC uses uh, this—has this fancy feature that we quite like called late context binding. So this—by context, I mean the presentation context. Um, sorry, I'm trying to monitor the chat. I'm going to ignore the chat unless if someone wants to speak up, please raise your hand and correct anything that I'm saying. Um, so, the—the tag that we use for double-spend protection in ARC is computed, um, by this function here. This is called the DY—DYPRF, DY stands for uh, the—the names of the authors, um, that designed this. So we have, um, a key $K$ that's used across presentations, we have a nonce, and we have our presentation context. These are—the uh, nonce and context are unique for the presentation. Uh, the—the PRF key is used across presentations. And then we have a hash-to-curve thing, so we have, you know, we just—we just get a base point for this equation uh, from uh, hashing the context to the elliptic curve. So the attack is if um, I can solve a discrete log of $T$ relative to this base point, then we can correlate presentations uh, from the same credential holder. So specifically, I solve this discrete log, I compute the inverse, and then I get $K$ uh, $K$ plus some nonce. And then, I can start looking for um, other nonces that um, match tags that I've seen in the past. And this would allow me to—to link presentations using the same credential, uh, for the same uh, for the same—uh, for the same uh, credential holder. Okay. Um, any questions about this? I see there's a robust conversation, um, and I just want to make sure everyone agrees with what I'm saying before I move on. Okay. Okay, moving on then. Um, okay. So, um, the goal then is to um, instantiate this late context binding thing, uh, with information-theoretic techniques, and the question is how do we do that? Um, so, Michael Rosenberg and Michele Orrù have—have—have made—made—made an idea using universal hash functions. Um, I credit this—I credit them with this idea just because they've done, like, an actual write-up, but this is, like, based on like, um, there's like a crypto paper, "Everlasting Credentials" that is related to this. Um, I also think Watson Ladd at some point relate—brought up a related idea on the list, but this was before at least I personally had the full context for this. By the way, the only reason—reason I'm presenting this is, um, Michael uh, is no longer uh, at Cloudflare, um, the company that I work, and so that's why um, um, I'm—I'm sort of filling in for him. I wa—I just wanted to make sure today that we—we—we had time to—to discuss this. So the key idea is that we're going to replace the DYPRF with a universal hash function. A universal hash function is just a—a hash function that is guaranteed to, um, uh, I guess, the way I—the way I would think about it is we have, uh, it's a—it's a polynomial with of degree $N$, large degree $N$, uh, with random coefficients, and random and known to the—to the credential holder, but not the issuer/verifier. Um, and so during presentation, I just evaluate this, um, this, um, this polynomial with random coefficients at a point that is computed from um, my presentation context and my nonce. And that's how I get my tag. So, um, this is perfectly hiding um, up to the presentation limit, so the math of polynomials basically guarantees that, um, as long as the number of points I evaluate this polynomial at doesn't exceed the presentation limit, then, um, every—every tag is—is—perfectly hides the uh, point at which it was evaluated. Uh, yes. Um, so, that's the kind of the basic idea. So, during credential issuance, we, um, we commit to the coefficients of this polynomial. This commitment is, um, like one group element, so it's very, very cheap in terms of communication cost. This is accomplished with uh, a KZG commitments, there's details in the—in Michele's paper that I'm—I'm referring to here. Um, and then we have to add some additional constraints to the sigma proofs. Um, the—the major cost of this is that, um, the computation is now linear in the presentation limit, because I have to evaluate this degree $N$ polynomial, um, whereas with DYPRF, it's—it's—it's sublinear in the presentation limit. Uh, okay. So, um, just to mention some caveats, I kind of already mentioned one, so one is that this is a little looser than we gener—like, tend to think of this, like, the limit is really the number, I believe, and- and I- I- I could be wrong about this, um, I'm—I'm not 100% confident on this, but, uh, the limit is the number of unique nonce/presentation context pairs, not the number of nonces per context. So, that is a significant difference between, um, ARC and, uh, ARC if we modified it this way. Um, so, um, with that—with that in mind, um, the computational cost is probably the main downside for this, so if you're—if you're going to use ARC for, like, a presentation limit of 1000, then, uh, I think, I—I—I don't—Sam put together some benchmarks at some point, I don't remember the—the—the concrete numbers, but, um, it's, uh, you know, uh, issuance, issuance and presentation computation time is going to—is going to go up quite a bit. Um, that said, I—I—I do think, um, one thing I believe we've talked about in the past is adding something like late binding to ACT. Um, this, to me, actually seems like a fairly reasonable application. Imagine you used, uh, a universal hash function to derive the first nullifier, um, for a given presentation context, and thereafter you just use ACT as normal. I think this sort of thing, uh, could, uh, basically, your—your—your presentation limit is not going to be that high, it's not going to be as high as it would be for ARC, and also, um, most of the, you know, all most of the costs you don't actually, uh, is not carried over for every ACT presentation that you do. Um, another thing, another kind of nuance is, um, Michael's write-up uses BBS rather than CMZ for the algebraic MAC. And, um, I think this is probably because it's more friendly with KZG, but I'm not actually 100% sure. It might be possible that you can continue to use CMZ. Um, finally, I just wanted to note that, like, uh, just from talking to Michael, he seems pretty confident in this design, but I do think, uh, you know, this is a substantial change, either to ARC or ACT, and we would want to do some new security analysis. Um, and just incidentally, I—I wanted to mention that there are differences between the security analysis for ARC and ACT that need a—that do matter for things like how do we pick a curve, how do we pick, um, parameters for this—for this scheme. Uh, and I just wanted to call out that, like, um, the—they're not on the same footing right now, and this might lead us to the wrong conclusions about, you know, picking curves for one or the other. And that's something, uh, we need to—we need to—to solve for, that's related here. Um, I think that's the end of my slides. I can get into details of, uh, these are just screenshots from—from Michael Rosenberg's write-up. Um, so I'll leave it there. Um, in terms of what we should consider, um, I think I'd be in favor of, I personally don't want to, uh, deploy ARC as it is today, I would want it to make sure it's at least PQ unlinkable. Um, uh, so, if, if we want to continue ARC, that's something I—I would suggest we consider, um, and then, um, yeah, and I'm not sure if it's relevant for ACT right now, but, um, that's—that's—that's, I guess, what I would like us to talk about. Go ahead, Sam.

**Benjamin VanderSloot:** Hello, um, I—I was just hoping to understand from your perspective where this beats out like batch VOPRF, because that—from my end, I just can't figure out where I would use this instead of batch VOPRF.

**Christopher Patton:** Um, yeah, so the—the—it's—it has to do with this, uh, this late context binding feature. Um, the—so I guess the way I would use, um, um, yeah, I—I—I—yeah, it—it depends on the use case, I guess. What—what use case specifically do you have in mind?

**Benjamin VanderSloot:** I guess I'm just imagining anything where the issuer and the redeemer are the same party, which is all the places where you can use ARC, batch VOPRF seems—like, it's better. Um, because that—it would be, I think, it would be different if this was publicly verifiable. Um, I think I could imagine late origin binding being—being helpful there, but because the issuer is—

**Christopher Patton:** Oh, so you're—you're thinking specifically, you're thinking specifically of like, I can in an application, I can emulate late origin binding in a different way. Yeah, I don't—that is a perspective.

**Benjamin VanderSloot:** Yeah, like, in particular, like, you—you say, in particular, like, I have my VOPRF, I—I present it, like, I just hand it back, which is great because the client doesn't need to do any computation, and then, um, I just scope it to that particular—like, let's say I'm a—I'm an issuer and I work for a bunch of different origins, right? I'll just say this one's used, right? And, and I don't need late origin binding because I've used that one spend anyway, and it can't get used again. So, yeah.

**Christopher Patton:** Got it. Yeah, I—I—I don't—I have, um, I have nothing substantial to say, uh, in response to that besides, um, this is a feature, this is like a—it's like an ugly corner—corner of ARC that, um, if it, you know, if it turns out to be useful, um, I would want to make sure that we implement it in a different way. Um, so, yeah, maybe that's—maybe that—that broader question, I think, is important to ask ourselves, is do we actually want this feature?

**Benjamin VanderSloot:** I—I want to clarify that I do want this feature, but—but I think if we're going to have it, we should implement it by doing a proof of a PQ secure cryptographic hash function, and—and I think that this approach is—is—of—of—the universal hash function here, I think—I think it's a dead end, um, and I want to encourage the group to, if it's not a dead end, convince ourselves of that today, otherwise, try to, you know, explore new—

**Christopher Patton:** What—what is a PQ secure hash function? What do you mean by that?

**Benjamin VanderSloot:** Like, like, so, DY can be inverted with a quantum computer, right? Yep. But something which is actually a one-way function in the presence of a quantum computer would be a PQ—PQ secure hash function. I- maybe this—this word is not right, but I think—I think you get my idea.

**Christopher Patton:** I don't quite, but I, um, let me—let me—let me try to put that, let me try to, um, rephrase. Um, so, the—the reason you think that universal hash, UHF, is dead is because of the computational cost? Or is there a different reason?

**Benjamin VanderSloot:** Um, I don't think it's better than the simpler things we have on tap. I think it's worse. And, the thing that I want is a compressed credential that I can present a large number of times, potentially trading off some computational cost at presentation time. And, this doesn't give me that because batch VOPRF is basically, asymptotically at least, the same storage space. And, with batch VOPRF, I don't need to do any computation at presentation, whereas if I had something that was, um, like similar to this DY idea, but instead of proving DY, I prove Poseidon or something like this, which is, I believe, thought to be secure in the presence of a—or thought to be one-way in the presence of a quantum computer, then I can still have a compressed credential and I can use it for a long time, and I can save my client lots of storage space by doing so.

**Christopher Patton:** Uh, but this is compressed. I mean, the—the cost of this is—is in terms of communication cost is not—

**Benjamin VanderSloot:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin VanderSloot:** No, no, no, that's not true. The—if I had like some 32-byte nonces and I prove the evaluation of the PQ PRF, I'm calling it, um, with that nonces as input and some counter $I$, and some context, and then I prove that $I$ is less than or equal to the rate limit—

**Christopher Patton:** So, your—your concern is—is with the client storage cost as it holds the credential.

**Benjamin VanderSloot:** That's exactly right. That's exactly right.

**Christopher Patton:** Okay. Um, this is bad for that. Um, why is that in particular—why is that particularly a concern?

**Benjamin VanderSloot:** That's the whole reason that I—I—so, we were going to deploy something very similar to this called private proofs, and—and—the reason that I wanted to do it was because of the fact that I can store a small credential, but present it a large number of times. And, that's nice for two reasons. One is that I don't have to go back to the issuer very often, I can just present it in various contexts where I don't have all the information to get the issuance, and then, two, um, I can present it a large number of times, right? Um, or sorry, then—

**Christopher Patton:** Or sorry, and it's small, sorry. The—the second thing I said was the same as the first thing, but it's small, and I don't have to go back to the issuer for—for issuance very often. Okay. Cool. Uh, we—there is a long queue, so I um, let's uh, yeah. Go ahead, Watson.

**Watson Ladd:** Yeah, this is interesting. Um, you know, the—the—there—there are some parts of this I don't quite get, like, why the everlasting paper had to go through and use multiple of these, uh, polynomials and add them together. But, I—I do think that something like the Legendre PRF is worth considering, where what we're, you know, per bit, we have to check whether or not something is quadratic residue, and that proof is very easy to do. And, yeah, the showing is going to be a bit bigger, it's going to come down to how much you can compress proving a bunch of things with either squares or not squares or, you know, some mix of both, but that would solve the quest—that would be a—again, a computational hardness assumption for unlinkability that's plausibly PQ. Um, I think every approach like this with an information-theoretic one, where you're just trying to evaluate some big thing, it gets really messy. And, I've looked at ways to try, and how do you do these lookups, how do you do things, and there's—it's not—there's none of them are very good.

**Christopher Patton:** Okay. Um, can you provide a reference to that paper or, if you're just talking about Longfellow, could you put it in the chat?

**Watson Ladd:** Yeah, I—I—I'll go uh, send—send some emails to the list.

**Christopher Patton:** Cool. Chris?

**Christopher Wood:** Um, to the point of, um, or to Sam's point, I guess, um, I guess about this being potentially dead in the water, um, we don't have to have the discussion now, but I think like once we get through the- the- the other presentations, we should have some discussion around like what the fate, the future of ARC is as it pertains to um, um, I guess other types of credentials that might be um, more widely sought after by users. Um, it is no longer clear to me that ARC is the- the thing that people want, um, if you've been ignoring the PQ um, problem space, so, um, let's- let's make sure we accommodate some time at the end for that discussion.

**Christopher Patton:** I agree. Thibault?

**Thibault Meunier:** Yeah, uh, I won't be long, I was going to make the same comment that I have for Chris, I really like the property of like client binding, but I don't know if like this solves a real use case that we have at the moment. Defeating the work, like on the PQ story, would be important if we go there, but like having the discussion would be good.

**Christopher Patton:** Cool. That's the end of the queue. Um, if anybody else has anything to they want to mention, I think my takeaway is, um, I mean, one thing I didn't hear is like, PQ—PQ unlinkability, like, like, it's not worth blocking on this, like, deploying things. I mean, it would—it would—it would be nice to know at least that there's consensus there. Um, other than that, uh, yeah, I'm super happy to find other path-ways to doing this. Um, um, I do feel like for the use cases like we, at least Thibault and I have talked about, I—so I was—I did not make PACT, unfortunately, um, so I don't know, I—I—I'm—I'm looking forward to hearing what Sam, uh, has to say about that. But, um, my—the question that I have is like is late binding uh, a feature that we still—still actually need? If we can emulate it in other ways, I think we're much better off. Um, but, yeah, just something to consider. That's—that's the end of this, so, um, we can move on if the chairs want to move on. Go ahead, Sam.

**Samuel Schlesinger:** Yeah, I—I just want to emphasize that, that I—I really like late binding. Um, oops, my camera—I really like late binding. I think we should keep—keep the work to get something like this going, um, maybe not on ARC with the DY construction, etc., but like, I think it's good, especially in the context of like, um, there's a bunch of work on publicly verifiable credentials and like, they need something like this, right? And so, yeah, I think this general work stream is good, maybe a little further out in terms of like getting something workable. Sounds good. Thanks everybody.

All right, yeah, thank you. I think, um, next we have, uh, Thibault, you're up, and this is Privacy Pass reverse flow draft (draft-ietf-privacypass-reverse-flow) update. Let me make sure—are you asked for presenting?

**Thibault Meunier:** Yeah, I've asked for control of the slide, but—

**Samuel Schlesinger:** You should have control now.

**Thibault Meunier:** Perfect. Okay, um, so, yeah. Hey everyone, uh, and I'm going to present Privacy Pass reverse flow, uh, the like draft version of the draft (draft-ietf-privacypass-reverse-flow), um, interestingly, like the last time I presented, I think was in March 2025, and like the draft kind of has evolved, along with like some changes that like happened in the working group, and I wanted to like regroup, um, because this seems like, like relevant to some of the work that will be presented today. Um, so, overall, the context for the reverse flow is like, um, the architecture that like we know and love, like which is, like, standardized in the RFC, where like you have a client going to an origin, being challenged, working with like an attester and an issuer, to—to attest, get, uh, like send a token request, get a token response, finalizing the token locally, and then, once it has a token, the client would go to the origin with a request and present the token, um, to actually be redeemed and, uh, validate and authenticate, uh, as Privacy Pass. There's a couple of limitations should be to aid, to move of like the rate limiting in term of like, um, what if like we—like the client needs to like keep carry on, uh, like contacting the origin, and so that, uh, like started like the reverse flow, um, that that we presented um, in March last year. And so, the idea is it's exactly the same thing as like Privacy Pass, and so that's why like the diagram on the right, um, like the origin, the client, the attester, and the issuer, is like exactly the same. The only trick, um, that happened is like instead of like simply presenting, um, the token, the client would like present a token plus request a new token, for an issuer which is in control of the origin. And so that's what is illustrated in this diagram, where like the client makes a request with a token, uh, redemption, and a new token request. Once the origin like processes, the, um, like the full request, it—the origin may send the token request to like its own, like, a new issuer, get the token response, and like forwards it—the forwards the token response, along with like the normal response, to the client. Since then, um, has like evolved a bit, um, to like include, um, a couple of, um, like new steps, um, it was important, uh, specifically with like the credential work, um, to like distinguish, um, finalization and presentation, which were like two distinct steps, um, that—that—that were being conducted, should be with like ARC, should be with ACT. And so, like, these have been like clearly distinguished, um, in the, the, the diagram. Um, another thing that has been, uh, made different is like even though the architecture of Privacy Pass, um, as defined in the RFC, does not specify what a token response or token request looks like, this is defined by like further RFC, it felt a bit wrong to say that like the client sends a token request and a token response, while it's actually like a credential request and a credential response, and therefore, the diagram has been updated accordingly. In term of like brief, um, changelog, and you can see like all the changelog on the draft, um, we've expanded, uh, the modi—the motivation section, um, to like, for instance, could be used to like preserve rate limiting, to have like some bootstrap of, like, new origin that like would have its own, like, private issuer, um, allow for like credential conversion, for instance, from like Blind RSA to like a couple of, like, batch VOPRF, or like Blind RSA to a, a, a credential or etc. There's the move that I mentioned before, we move like the terminology from like token to credential, and have added a few steps, um, there's a request, response, the finalization that we know, and also added the presentation step, which is important, um, for—for—for the credential work, uh, that—that is being conducted. Um, we've also sharpened a bit, uh, the privacy guidance, should be in term of like the metadata, the number of bits per request, and how like conversion work, and like how that might affect like the privacy guarantees which are provided to user. And finally, um, one of the things which was discussed in the, like—like the previous time and was discussed with a few folks, um, is we've added like a concrete HTTP header, uh, which is like Privacy-Pass-Reverse, uh, which is using ACT, for instance, to convey, um, the credential and like be able to get the response. So overall, I still have some open questions with regards to this draft, um, like the main question that I have and like that is, like, kind of, like, one of the main contributions of this work is, like, um, do anonymous credential work need some architecture guidance in Privacy Pass, or is the architecture guidance that we have sufficient? I do feel that at least being able to like define like the steps, um, especially like distinguish between finalization and presentation, is like important, and would be required here. Um, some other questions I have is like the client state is not mentioned anywhere, but seems to be very key. It's been mentioned in like the previous discussion, uh, like about ARC, will be mentioned in like ACT down the line. It seems to be key but is not mentioned anywhere. Maybe that's out of scope for Privacy Pass, but that's something that I think we need to like be able to consider as part of the architecture, because it has quite like some important step, and like the architecture and deployment guidance that we provide. Another question I have is, um, what is the right way to pass a credential request and convey the credential response that would come from the origin? HTTP headers seem convenient to like prototype at this point, but maybe we need to like start considering something else, maybe have some body wrapping, or something else. I don't know what's the nicest method, but that's definitely an open question here. Um, and finally, a big question, um, that we have through this architecture is, like, how do we ensure privacy guarantees? Um, having a bigger deployment, like, opens and like multiplies the surface for, like, the privacy risks. Um, I think one of the things that will be discussed, uh, like—like, and that comes out of like the PACT workshop, that Sam will like present down the line, is even though with our, like, multiple blocks, it would be nice to really tighten them, to like clearly understand, uh, the privacy guarantees that like such systems are providing. Um, yeah. So, I will stop here, um, and happy to have like opinions or questions, um, on that work. Yes, Tommy.

**Tommy Pauly:** All right, hello. Um, yeah, this—so, I I continue to think this is useful to write down. Um, it—it's a case I see. I don't have um, a particular opinion for the relevance in anonymous credentials, but I think other cases still use this, and I think it's useful to uh, specify. Regarding how you pass the credential request and response, or like, essentially how you actually communicate the reverse flow, I- I would suggest we do it similar to how we did the base Privacy Pass uh, redemption flow, where we, you know, we have a specification for, you know, there's—there's the actual interaction that needs to happen. And then we define HTTP headers, and in that case, it was the auth method, but you, know, this—this wouldn't be the auth method, this—this would be something else, but let's have some HTTP headers defined, uh, but they should not be the only way to do this. That if someone is embedding this in some JSON, Protobuf, whatever else they have communicating to the uh, entity that they're doing reverse flow with, they can do that, but there is still a standard default that we can fall back to.

**Thibault Meunier:** Yeah, that totally makes sense, um, and maybe to give another example, like the way we integrate the reverse flow in like Media over QUIC, is not via HTTP header because it's like Media over QUIC, and and therefore, I do agree having like probably like a separate one would like—would be interesting. Um, yes, Ben.

**Benjamin Schwartz:** Hi, uh, so I've just been trying to understand the situation where you need this. Um, I think in the beginning of Privacy Pass, the- the sort of simple expectation of how this situation was handled was that the server's—the origin response would have a Set-Cookie header, and it would set a—a first-party cookie. And so that would become your—you would sort of bootstrap from Privacy Pass into a cookie authentication, and then that would be your—your ongoing cert- uh, certificate or, um, credential. Um, so I guess this would be for cases where, essentially, like ongoing privacy is required after that transition. Is that basically right?

**Thibault Meunier:** Yes, exactly. And, like, again, that's why the lines was with the work being done with credentials, or work being done with like batch, where you probably need to like carry on. It's like when you need actually the unlinkability between the different requests.

**Benjamin Schwartz:** Okay. Um, that's uh, that's helpful to understand. It does seem like there might be a clearer way to model this, uh, as like a new issuance flow, like, it sounds to me like essentially what's happening here is, um, we're using one credential as the, as the permission to access a new issuer, which is then issuing a new credential for a different purpose.

**Thibault Meunier:** Yes, basically, it's exactly that.

**Benjamin Schwartz:** Um, so, maybe we could, if the—if in terms of how this is encoded, if we could match the encodings to the issuance flow, um, maybe that would be a little clearer. Um, my other question about this was, uh, you've talked a lot about using uh, issuing a new credential that replaces the one you were using. Um, what happens in a failure case? I hand over my—my credential, and then the reissuance fails.

**Thibault Meunier:** Uh, yes. I think it's like very similar to what happened when you like present and like redeem, uh, like a Privacy Pass token, and somehow it fails because of like network connection, is like it's a policy which is like left to like how the client is configured. If you think that like it's okay, and like you won't be like linked if you like represent the token, then you can represent it, but like this is like one of the failures—failure cases for like credentials at this point. And again, like, probably like an architecture could help like—like to think that through. So, I don't have all the answers, but like—like for now, that's a client policy and deployment policy.

**Benjamin Schwartz:** Thank you.

**Samuel Schlesinger:** Sam?

**Samuel Schlesinger:** Yeah, um, just to give a little context to Ben, um, some of these reverse flow instantiations are not—so, like, the—the simplest ones are like an interleave redemption and, and, um, issuance, but then some of them like ACT (draft-ietf-privacypass-arc-protocol / draft-ietf-privacypass-arc-crypto), actually, are distinct. So, in particular, the request for the new issuance contains a proof about the redeemed previous credential. And so, it's not exactly like easily, uh, separable, which is why this new architecture is very helpful to like standardize, such that when we instantiate it again and again and again, we can describe it in one place, um, rather than describing this flow in each individual document like in ACT or reverse flow, whatever. Um, and I don't think we can standardize the—like, because of the fact that sometimes they're interlinked, I don't think we can just use the previous standard for, for the responses and the requests, etc.

**Benjamin Schwartz:** Oh, so you're—you're thinking specifically, you're thinking specifically of like, "I can, in an application, I can emulate late origin binding in a different way." Yeah, I don't—that is a perspective.

**Samuel Schlesinger:** Yeah, like, in particular, like, you—you say, in particular, like, "I have my VOPRF, I—I present it, like, I just hand it back," which is great because the client doesn't need to do any computation. And then, um, I just scope it to that particular—like, let's say I'm a—I'm an issuer and I work for a bunch of different origins, right? I'll just say, "This one's used," right? And, and I don't need late origin binding because I've used that one spend anyway, and it can't get used again. So, yeah. Got it. Yeah, I—I—I don't—I have, um, I have nothing substantial to say, uh, in response to that besides, um, this is a feature, this is like a—it's like an ugly corner—corner of ARC (draft-ietf-privacypass-arc-protocol / draft-ietf-privacypass-arc-crypto) that, um, if it, you know, if it turns out to be useful, um, I would want to make sure that we implement it in a different way. Um, so, yeah, maybe that's—maybe that—that broader question, I think, is important to ask ourselves, is do we actually want this feature?

**Benjamin Schwartz:** I—I want to clarify that I do want this feature, but—but I think if we're going to have it, we should implement it by doing a proof of a PQ secure cryptographic hash function, and—and I think that this approach is—is—of—of—the universal hash function here, I think—I think it's a dead end, um, and I want to encourage the group to, if it's not a dead end, convince ourselves of that today, otherwise, try to, you know, explore new—

**Christopher Patton:** What—what is a PQ secure hash function? What do you mean by that?

**Benjamin Schwartz:** Like, like, so, DY can be inverted with a quantum computer, right? Yep. But something which is actually a one-way function in the presence of a quantum computer would be a PQ—PQ secure hash function. I- maybe this—this word is not right, but I think—I think you get my idea.

**Christopher Patton:** I don't quite, but I, um, let me—let me—let me try to put that, let me try to, um, rephrase. Um, so, the—the reason you think that universal hash, UHF, is dead is because of the computational cost? Or is there a different reason?

**Benjamin Schwartz:** Um, I don't think it's better than the simpler things we have on tap. I think it's worse. And, the thing that I want is a compressed credential that I can present a large number of times, potentially trading off some computational cost at presentation time. And, this doesn't give me that because batch VOPRF is basically, asymptotically at least, the same storage space. And, with batch VOPRF, I don't need to do any computation at presentation, whereas if I had something that was, um, like similar to this DY idea, but instead of proving DY, I prove Poseidon or something like this, which is, I believe, thought to be secure in the presence of a—or thought to be one-way in the presence of a quantum computer, then I can still have a compressed credential and I can use it for a long time, and I can save my client lots of storage space by doing so.

**Christopher Patton:** Uh, but this is compressed. I mean, the—the cost of this is—is in terms of communication cost is not—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, that's not true. The—if I had like some 32-byte nonces and I prove the evaluation of the PQ PRF, I'm calling it, um, with that nonces as input and some counter $I$, and some context, and then I prove that $I$ is less than or equal to the rate limit—

**Christopher Patton:** So, your—your concern is—is with the client storage cost as it holds the credential.

**Benjamin VanderSloot:** That's exactly right. That's exactly right.

**Christopher Patton:** Okay. Um, this is bad for that. Um, why is that in particular—why is that particularly a concern?

**Benjamin VanderSloot:** That's the whole reason that I—I—so, we were going to deploy something very similar to this called private proofs, and—and—the reason that I wanted to do it was because of the fact that I can store a small credential, but present it a large number of times. And, that's nice for two reasons. One is that I don't have to go back to the issuer very often, I can just present it in various contexts where I don't have all the information to get the issuance, and then, two, um, I can present it a large number of times, right? Um, or sorry, then—

**Christopher Patton:** Or sorry, and it's small, sorry. The—the second thing I said was the same as the first thing, but it's small, and I don't have to go back to the issuer for—for issuance very often. Okay. Cool. Uh, we—there is a long queue, so I um, let's uh, yeah. Go ahead, Watson.

**Watson Ladd:** Yeah, this is interesting. Um, you know, the—the—there—there are some parts of this I don't quite get, like, why the everlasting paper had to go through and use multiple of these, uh, polynomials and add them together. But, I—I do think that something like the Legendre PRF is worth considering, where what we're, you know, per bit, we have to check whether or not something is quadratic residue, and that proof is very easy to do. And, yeah, the showing is going to be a bit bigger, it's going to come down to how much you can compress proving a bunch of things with either squares or not squares or, you know, some mix of both, but that would solve the quest—that would be a—again, a computational hardness assumption for unlinkability that's plausibly PQ. Um, I think every approach like this with an information-theoretic one, where you're just trying to evaluate some big thing, it gets really messy. And, I've looked at ways to try, and how do you do these lookups, how do you do things, and there's—it's not—there's none of them are very good.

**Christopher Patton:** Okay. Um, can you provide a reference to that paper or, if you're just talking about Longfellow, could you put it in the chat?

**Watson Ladd:** Yeah, I—I—I'll go uh, send—send some emails to the list.

**Christopher Patton:** Cool. Chris?

**Christopher Wood:** Um, to the point of, um, or to Sam's point, I guess, um, I guess about this being potentially dead in the water, um, we don't have to have the discussion now, but I think like once we get through the- the- the other presentations, we should have some discussion around like what the fate, the future of ARC is as it pertains to um, um, I guess other types of credentials that might be um, more widely sought after by users. Um, it is no longer clear to me that ARC is the- the thing that people want, um, if you've been ignoring the PQ um, problem space, so, um, let's- let's make sure we accommodate some time at the end for that discussion.

**Christopher Patton:** I agree. Thibault?

**Thibault Meunier:** Yeah, uh, I won't be long, I was going to make the same comment that I have for Chris, I really like the property of like client binding, but I don't know if like this solves a real use case that we have at the moment. Defeating the work, like on the PQ story, would be important if we go there, but like having the discussion would be good.

**Christopher Patton:** Cool. That's the end of the queue. Um, if anybody else has anything to they want to mention, I think my takeaway is, um, I mean, one thing I didn't hear is like, PQ—PQ unlinkability, like, like, it's not worth blocking on this, like, deploying things. I mean, it would—it would—it would be nice to know at least that there's consensus there. Um, other than that, uh, yeah, I'm super happy to find other path-ways to doing this. Um, um, I do feel like for the use cases like we, at least Thibault and I have talked about, I—so I was—I did not make PACT, unfortunately, um, so I don't know, I—I—I'm—I'm looking forward to hearing what Sam, uh, has to say about that. But, um, my—the question that I have is like is late binding uh, a feature that we still—still actually need? If we can emulate it in other ways, I think we're much better off. Um, but, yeah, just something to consider. That's—that's the end of this, so, um, we can move on if the chairs want to move on. Go ahead, Sam.

**Samuel Schlesinger:** Yeah, I—I just want to emphasize that, that I—I really like late binding. Um, oops, my camera—I really like late binding. I think we should keep—keep the work to get something like this going, um, maybe not on ARC with the DY construction, etc., but like, I think it's good, especially in the context of like, um, there's a bunch of work on publicly verifiable credentials and like, they need something like this, right? And so, yeah, I think this general work stream is good, maybe a little further out in terms of like getting something workable. Sounds good. Thanks everybody.

**Thibault Meunier:** Yes, yes, I agree.

**Samuel Schlesinger:** All right, yeah. Thank you. I think, um, next we have, uh, Sam, you're up, and this is ACT update.

**Samuel Schlesinger:** Awesome, yep. Um, requests slides, is that what I do to get control? You should have control now. Awesome, okay. Believe I have control. Okay, amazing. So, just wanted to share, um, like what's—what's been going on with ACTs, um, progress on the draft, and then, you know, where we're headed, um, in terms of what we're—what we're building and thinking about. So, just to remind everybody what ACTs are, um, they're a two-party protocol between a user and an issuer, and the user holds some anonymous credential, very much in the same style of ARC, like we use very similar types of credentials, and it carries a hidden balance $B$. And then the user presents an unlinkable spend proof to every other instance of redemption and issuance of of that credential, um, basically saying, "I have enough balance here in order to spend $S$ credits." And then the issuer returns a refreshed credential where they've taken away some credits up to $S$. And when we talk about, sort of, like this state machine or—or this, um, sort of, like, long-lived token, um, it's really a sequence of refreshed credentials. It's like this chain of of anonymous credentials.

And what's changed since last time? Well, we've—we haven't actually published a draft. I missed the deadline by like two minutes, and then I I then I realized Sigma-Proofs (draft-ietf-privacypass-arc-crypto) was updated, so by 1/26 we'll have a new draft published, uh, where the sigma-proofs, um, will be migrating to the—the CFRG draft. Um, that means that we've migrated to using SHA-128 for hash to scalar and Fiat-Shamir. And then we've also added flexible refunds, which was an idea that Kathy had, where we can actually, um, if you prove that you can spend $S$, then you can, um, add back in anything between 0 and $S$, and basically say, "Well, okay, maybe you asked to stream a 60-minute video, but you only watched 20 minutes. So I'm going to refund you 40 minutes."

And what I want to talk about a little bit today, and this is going to be a short one, the- the next one's going to be a little longer, um, is is where—where I think we- we should be headed with—with this type of work. Um, ACTs are nice if you want to rate limit something, um, but it doesn't provide every capability you want to express authorization policies, uh, in a flexible way. So, like, what we might want in general, and this is actually not quite, um, as complex as you can get, but, like, here's an example where you could—you could generalize to—to an affine step, where we multiply a state vector by some matrix, and then we add some, um, vector $u$ to it, um, and then we prove that every component of that vector $u$ is correct, so, like, if- if it's either chosen by the user, or it's chosen by the server, or jointly determined in some way with some ranges or equality bounds. And then we can prove that, like, you know, $S$ satisfies some conjunction of of range and equality predicates over some combinations of its entries. And, and, like, why would we do this? This sounds complicated, um. One example is, like, epochs, you know, you might want to say, like, "you know, during this epoch, you get this rate limit, and then in the next epoch, you get your—your epoch ticked up, and then you get more rate limit." Um, you might want to say that you have some sort of, like, tiering where, like, you know, certain users who have paid for the, you know, Express Plus tier, they get like slightly larger request sizes or or whatever it may be. But in general, it's to express richer authorization policies in a privacy-preserving way, um, exactly so that we don't have to always, in every case, upgrade our users to some cookie or something, um, they can remain unlinkable, but we can still have expressive policies.

And, and I wanted to give one specific example, um, which is like a—a balance with some access tier baked in at issuance. Um, here we have these policy constants $\alpha$ and $\beta$, uh, where basically, we—we prove that our spend is less than or equal to $\alpha$ times, um, $L$, which is the—the tier, plus $\beta$, which is some, like, base level of of access that's provided, um. And so this is just like a simple example of of our policy also being hidden—or not the policy, but the—the access tier being hidden from the server. So, it knows that the user can access this—this tier of of thing, but for instance, like let's say you have the high tier, but you're making like a—a request that a lower tier could also do, then you won't be identified as being in the higher tier of access. Um, so, it enables higher levels of privacy. Um, this is like the simplest example I could come up with that seemed motivated. Uh, there are other examples that are more motivated in practice. Okay. Um, questions? This is basically it for the ACT side of things. Yeah, Nikita.

**Nikita Borisov:** So, I mean, you- you are kind of uh, skirting with this notion of general state machines versus things that are uh, motivated by specific use cases. And I mean, if you go to the general state machine level, you could essentially just have some sort of, you know, zero-knowledge virtual machine to- to have fully general computation that you can express. My question is how do you decide what to pursue, you know, like, what level of generality to explore?

**Samuel Schlesinger:** Yeah, it's a great question. So, on—on my end, it's very practically motivated, where, um, these—these particular things, um, as long as we are able to deploy them, right, they're—they are PQ private, and so we can avoid having like 80-kilobyte proofs. We can have, you know, 1 or 2-kilobyte proofs for pretty substantially interesting state machines. And so for me, it's—it's just like a practical question of, like, what are the performance characteristics? Can they be deployed at scale on the open web? Um, maybe in 10 years, everything we do will be like some sort of, um, fast but slightly big post-quantum zero-knowledge proof, but for now, I—I am forced to pursue options which have, uh, better bandwidth qualities. Um, the VOLE in the head stuff in the comments is something that I didn't know about. I should look into that, might be that there are like, sort of, best of both worlds type situations. Um, yeah.

**Nikita Borisov:** Uh, well, I guess, my- the- in some sense, I feel like, uh, this should be the- the real question is, uh, this should be driven by use cases, right? And I think this is something that's been expressed a bunch of times in this meeting, and so, I think that, uh, it's the—uh, I think, you know, I think definitely it's really interesting what kind of generality things you could do efficiently, but I think the- from this meeting, the question really should be what kind of use cases do we need to support and how do we- we best do them? So, uh, and I think the use cases part of your presentation was a little under-developed, right? So...

**Samuel Schlesinger:** Yeah, I should—I should clarify that that, um, the next presentation will, will, I think, um, use—be—be helpful there. We—we have an architecture of sorts that we'd like to propose that, um, will hopefully help users have less friction on the web, and we believe that the bandwidth characteristics of these types of proofs will be very helpful in deploying this on the web as like a web API or something like that. And I agree that that, um, this wasn't sufficiently motivated and it is complex and scary. So, I'm not—yeah. Let's—let's make sure we accommodate some time at the end for that discussion. I agree. Thibault?

**Thibault Meunier:** Yeah, uh, I won't be long, I was going to make the same comment that I have for Chris, I really like the property of like client binding, but I don't know if like this solves a real use case that we have at the moment. Defeating the work, like on the PQ story, would be important if we go there, but like having the discussion would be good.

**Samuel Schlesinger:** Cool. That's the end of the queue, um, if anybody else has anything they want to mention. I think my takeaway is, um, I mean, one thing I didn't hear is like, PQ—PQ unlinkability, like, like, it's not worth blocking on this, like, deploying things. I mean, it would—it would—it would be nice to know at least that there's consensus there. Um, other than that, uh, yeah, I'm super happy to find other path-ways to doing this. Um, um, I do feel like for the use cases like we, at least Thibault and I have talked about, I—so I was—I did not make PACT, unfortunately, um, so I don't know, I—I—I'm—I'm looking forward to hearing what Sam, uh, has to say about that. But, um, my—the question that I have is like is late binding uh, a feature that we still—still actually need? If we can emulate it in other ways, I think we're much better off. Um, but, yeah, just something to consider. That's—that's the end of this, so, um, we can move on if the chairs want to move on. Go ahead, Sam.

**Samuel Schlesinger:** Yeah, I—I just want to emphasize that, that I—I really like late binding. Um, oops, my camera—I really like late binding. I think we should keep—keep the work to get something like this going, um, maybe not on ARC with the DY construction, etc., but like, I think it's good, especially in the context of like, um, there's a bunch of work on publicly verifiable credentials and like, they need something like this, right? And so, yeah, I think this general work stream is good, maybe a little further out in terms of like getting something workable. Sounds good. Thanks everybody.

All right, yeah, thank you. I think, um, next we have, uh, Thibault, you're up, and this is Privacy Pass reverse flow draft (draft-ietf-privacypass-reverse-flow) update. Let me make sure—are you asked for presenting?

**Thibault Meunier:** Yeah, I've asked for control of the slide, but—

**Samuel Schlesinger:** You should have control now.

**Thibault Meunier:** Perfect. Okay, um, so, yeah. Hey everyone, uh, and I'm going to present Privacy Pass reverse flow, uh, the like draft version of the draft, um, interestingly, like the last time I presented, I think was in March 2025, and like the draft kind of has evolved, along with like some changes that like happened in the working group, and I wanted to like regroup, um, because this seems like, like relevant to some of the work that will be presented today. Um, so, overall, the context for the reverse flow is like, um, the architecture that like we know and love, like which is, like, standardized in the RFC, where like you have a client going to an origin, being challenged, working with like an attester and an issuer, to—to attest, get, uh, like send a token request, get a token response, finalizing the token locally, and then, once it has a token, the client would go to the origin with a request and present the token, um, to actually be redeemed and, uh, validate and authenticate, uh, as Privacy Pass. There's a couple of limitations should be to aid, to move of like the rate limiting in term of like, um, what if like we—like the client needs to like keep carry on, uh, like contacting the origin, and so that, uh, like started like the reverse flow, um, that that we presented um, in March last year. And so, the idea is it's exactly the same thing as like Privacy Pass, and so that's why like the diagram on the right, um, like the origin, the client, the attester, and the issuer, is like exactly the same. The only trick, um, that happened is like instead of like simply presenting, um, the token, the client would like present a token plus request a new token, for an issuer which is in control of the origin. And so that's what is illustrated in this diagram, where like the client makes a request with a token, uh, redemption, and a new token request. Once the origin like processes, the, um, like the full request, it—the origin may send the token request to like its own, like, a new issuer, get the token response, and like forwards it—the forwards the token response, along with like the normal response, to the client. Since then, um, has like evolved a bit, um, to like include, um, a couple of, um, like new steps, um, it was important, uh, specifically with like the credential work, um, to like distinguish, um, finalization and presentation, which were like two distinct steps, um, that—that—that were being conducted, should be with like ARC, should be with ACT. And so, like, these have been like clearly distinguished, um, in the, the, the diagram. Um, another thing that has been, uh, made different is like even though the architecture of Privacy Pass, um, as defined in the RFC, does not specify what a token response or token request looks like, this is defined by like further RFC, it felt a bit wrong to say that like the client sends a token request and a token response, while it's actually like a credential request and a credential response, and therefore, the diagram has been updated accordingly. In term of like brief, um, changelog, and you can see like all the changelog on the draft, um, we've expanded, uh, the modi—the motivation section, um, to like, for instance, could be used to like preserve rate limiting, to have like some bootstrap of, like, new origin that like would have its own, like, private issuer, um, allow for like credential conversion, for instance, from like Blind RSA to like a couple of, like, batch VOPRF, or like Blind RSA to a, a, a credential or etc. There's the move that I mentioned before, we move like the terminology from like token to credential, and have added a few steps, um, there's a request, response, the finalization that we know, and also added the presentation step, which is important, um, for—for—for the credential work, uh, that—that is being conducted. Um, we've also sharpened a bit, uh, the privacy guidance, should be in term of like the metadata, the number of bits per request, and how like conversion work, and like how that might affect like the privacy guarantees which are provided to user. And finally, um, one of the things which was discussed in the, like—like the previous time and was discussed with a few folks, um, is we've added like a concrete HTTP header, uh, which is like Privacy-Pass-Reverse, uh, which is using ACT, for instance, to convey, um, the credential and like be able to get the response. Overall, I still have some open questions with regards to this draft, um, like the main question that I have and like that is, like, kind of, like, one of the main contributions of this work is, like, um, do anonymous credential work need some architecture guidance in Privacy Pass, or is the architecture guidance that we have sufficient? I do feel that at least being able to like define like the steps, um, especially like distinguish between finalization and presentation, is like important, and would be required here. Um, some other questions I have is like the client state is not mentioned anywhere, but seems to be very key. It's been mentioned in like the previous discussion, uh, like about ARC, will be mentioned in like ACT down the line. It seems to be key but is not mentioned anywhere. Maybe that's out of scope for Privacy Pass, but that's something that I think we need to like be able to consider as part of the architecture, because it has quite like some important step, and like the architecture and deployment guidance that we provide. Another question I have is, um, what is the right way to pass a credential request and convey the credential response that would come from the origin? HTTP headers seem convenient to like prototype at this point, but maybe we need to like start considering something else, maybe have some body wrapping, or something else. I don't know what's the nicest method, but that's definitely an open question here. Um, and finally, a big question, um, that we have through this architecture is, like, how do we ensure privacy guarantees? Um, having a bigger deployment, like, opens and like multiplies the surface for, like, the privacy risks. Um, I think one of the things that will be discussed, uh, like—like, and that comes out of like the PACT workshop, that Sam will like present down the line, is even though with our, like, multiple blocks, it would be nice to really tighten them, to like clearly understand, uh, the privacy guarantees that like such systems are providing. Um, yeah. So, I will stop here, um, and happy to have like opinions or questions, um, on that work. Yes, Tommy.

**Tommy Pauly:** All right, hello. Um, yeah, this—so, I I continue to think this is useful to write down. Um, it—it's a case I see. I don't have um, a particular opinion for the relevance in anonymous credentials, but I think other cases still use this, and I think it's useful to uh, specify. Regarding how you pass the credential request and response, or like, essentially how you actually communicate the reverse flow, I- I would suggest we do it similar to how we did the base Privacy Pass uh, redemption flow, where we, you know, we have a specification for, you know, there's—there's the actual interaction that needs to happen. And then we define HTTP headers, and in that case, it was the auth method, but you, know, this—this wouldn't be the auth method, this—this would be something else, but let's have some HTTP headers defined, uh, but they should not be the only way to do this. That if someone is embedding this in some JSON, Protobuf, whatever else they have communicating to the uh, entity that they're doing reverse flow with, they can do that, but there is still a standard default that we can fall back to.

**Thibault Meunier:** Yeah, that totally makes sense, um, and maybe to give another example, like the way we integrate the reverse flow in like Media over QUIC, is not via HTTP header because it's like Media over QUIC, and and therefore, I do agree having like probably like a separate one would like—would be interesting. Um, yes, Ben.

**Benjamin Schwartz:** Hi, uh, so I've just been trying to understand the situation where you need this. Um, I think in the beginning of Privacy Pass, the- the sort of simple expectation of how this situation was handled was that the server's—the origin response would have a Set-Cookie header, and it would set a—a first-party cookie. And so that would become your—you would sort of bootstrap from Privacy Pass into a cookie authentication, and then that would be your—your ongoing cert- uh, certificate or, um, credential. Um, so I guess this would be for cases where, essentially, like ongoing privacy is required after that transition. Is that basically right?

**Thibault Meunier:** Yes, exactly. And, like, again, that's why the lines was with the work being done with credentials, or work being done with like batch, where you probably need to like carry on. It's like when you need actually the unlinkability between the different requests.

**Benjamin Schwartz:** Okay. Um, that's uh, that's helpful to understand. It does seem like there might be a clearer way to model this, uh, as like a new issuance flow, like, it sounds to me like essentially what's happening here is, um, we're using one credential as the, as the permission to access a new issuer, which is then issuing a new credential for a different purpose.

**Thibault Meunier:** Yes, basically, it's exactly that.

**Benjamin Schwartz:** Um, so, maybe we could, if the—if in terms of how this is encoded, if we could match the encodings to the issuance flow, um, maybe that would be a little clearer. Um, my other question about this was, uh, you've talked a lot about using uh, issuing a new credential that replaces the one you were using. Um, what happens in a failure case? I hand over my—my credential, and then the reissuance fails.

**Thibault Meunier:** Uh, yes. I think it's like very similar to what happened when you like present and like redeem, uh, like a Privacy Pass token, and somehow it fails because of like network connection, is like it's a policy which is like left to like how the client is configured. If you think that like it's okay, and like you won't be like linked if you like represent the token, then you can represent it, but like this is like one of the failures—failure cases for like credentials at this point. And again, like, probably like an architecture could help like—like to think that through. So, I don't have all the answers, but like—like for now, that's a client policy and deployment policy.

**Benjamin Schwartz:** Thank you.

**Samuel Schlesinger:** Sam?

**Samuel Schlesinger:** Yeah, um, just to give a little context to Ben, um, some of these reverse flow instantiations are not—so, like, the—the simplest ones are like an interleave redemption and, and, um, issuance, but then some of them like ACT (draft-ietf-privacypass-arc-protocol / draft-ietf-privacypass-arc-crypto), actually, are distinct. So, in particular, the request for the new issuance contains a proof about the redeemed previous credential. And so, it's not exactly like easily, uh, separable, which is why this new architecture is very helpful to like standardize, such that when we instantiate it again and again and again, we can describe it in one place, um, rather than describing this flow in each individual document like in ACT or reverse flow, whatever. Um, and I don't think we can standardize the—like, because of the fact that sometimes they're interlinked, I don't think we can just use the previous standard for, for the responses and the requests, etc.

**Benjamin Schwartz:** Oh, so you're—you're thinking specifically, you're thinking specifically of like, "I can, in an application, I can emulate late origin binding in a different way." Yeah, I don't—that is a perspective.

**Samuel Schlesinger:** Yeah, like, in particular, like, you—you say, in particular, like, "I have my VOPRF, I—I present it, like, I just hand it back," which is great because the client doesn't need to do any computation. And then, um, I just scope it to that particular—like, let's say I'm a—I'm an issuer and I work for a bunch of different origins, right? I'll just say, "This one's used," right? And, and I don't need late origin binding because I've used that one spend anyway, and it can't get used again. So, yeah. Got it. Yeah, I—I—I don't—I have, um, I have nothing substantial to say, uh, in response to that besides, um, this is a feature, this is like a—it's like an ugly corner—corner of ARC (draft-ietf-privacypass-arc-protocol / draft-ietf-privacypass-arc-crypto) that, um, if it, you know, if it turns out to be useful, um, I would want to make sure that we implement it in a different way. Um, so, yeah, maybe that's—maybe that—that broader question, I think, is important to ask ourselves, is do we actually want this feature?

**Benjamin Schwartz:** I—I want to clarify that I do want this feature, but—but I think if we're going to have it, we should implement it by doing a proof of a PQ secure cryptographic hash function, and—and I think that this approach is—is—of—of—the universal hash function here, I think—I think it's a dead end, um, and I want to encourage the group to, if it's not a dead end, convince ourselves of that today, otherwise, try to, you know, explore new—

**Christopher Patton:** What—what is a PQ secure hash function? What do you mean by that?

**Benjamin Schwartz:** Like, like, so, DY can be inverted with a quantum computer, right? Yep. But something which is actually a one-way function in the presence of a quantum computer would be a PQ—PQ secure hash function. I- maybe this—this word is not right, but I think—I think you get my idea.

**Christopher Patton:** I don't quite, but I, um, let me—let me—let me try to put that, let me try to, um, rephrase. Um, so, the—the reason you think that universal hash, UHF, is dead is because of the computational cost? Or is there a different reason?

**Benjamin Schwartz:** Um, I don't think it's better than the simpler things we have on tap. I think it's worse. And, the thing that I want is a compressed credential that I can present a large number of times, potentially trading off some computational cost at presentation time. And, this doesn't give me that because batch VOPRF is basically, asymptotically at least, the same storage space. And, with batch VOPRF, I don't need to do any computation at presentation, whereas if I had something that was, um, like similar to this DY idea, but instead of proving DY, I prove Poseidon or something like this, which is, I believe, thought to be secure in the presence of a—or thought to be one-way in the presence of a quantum computer, then I can still have a compressed credential and I can use it for a long time, and I can save my client lots of storage space by doing so.

**Christopher Patton:** Uh, but this is compressed. I mean, the—the cost of this is—is in terms of communication cost is not—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Wood:** I see.

**Christopher Patton:** Anyway, we'll talk about this on the list, so, um, we can move on if the chairs want to move on. Go ahead, Sam.

**Samuel Schlesinger:** All right, yeah. Thank you. I think, um, next we have, uh, Thibault, you're up, and this is Privacy Pass reverse flow draft (draft-ietf-privacypass-reverse-flow) update. Let me make sure—are you asked for presenting?

**Thibault Meunier:** Yeah, I've asked for control of the slide, but—

**Samuel Schlesinger:** You should have control now.

**Thibault Meunier:** Perfect. Okay, um, so, yeah. Hey everyone, uh, and I'm going to present Privacy Pass reverse flow, uh, the like draft version of the draft, um, interestingly, like the last time I presented, I think was in March 2025, and like the draft kind of has evolved, along with like some changes that like happened in the working group, and I wanted to like regroup, um, because this seems like, like relevant to some of the work that will be presented today. Um, so, overall, the context for the reverse flow is like, um, the architecture that like we know and love, like which is, like, standardized in the RFC, where like you have a client going to an origin, being challenged, working with like an attester and an issuer, to—to attest, get, uh, like send a token request, get a token response, finalizing the token locally, and then, once it has a token, the client would go to the origin with a request and present the token, um, to actually be redeemed and, uh, validate and authenticate, uh, as Privacy Pass. There's a couple of limitations should be to aid, to move of like the rate limiting in term of like, um, what if like we—like the client needs to like keep carry on, uh, like contacting the origin, and so that, uh, like started like the reverse flow, um, that that we presented um, in March last year. And so, the idea is it's exactly the same thing as like Privacy Pass, and so that's why like the diagram on the right, um, like the origin, the client, the attester, and the issuer, is like exactly the same. The only trick, um, that happened is like instead of like simply presenting, um, the token, the client would like present a token plus request a new token, for an issuer which is in control of the origin. And so that's what is illustrated in this diagram, where like the client makes a request with a token, uh, redemption, and a new token request. Once the origin like processes, the, um, like the full request, it—the origin may send the token request to like its own, like, a new issuer, get the token response, and like forwards it—the forwards the token response, along with like the normal response, to the client. Since then, um, has like evolved a bit, um, to like include, um, a couple of, um, like new steps, um, it was important, uh, specifically with like the credential work, um, to like distinguish, um, finalization and presentation, which were like two distinct steps, um, that—that—that were being conducted, should be with like ARC, should be with ACT. And so, like, these have been like clearly distinguished, um, in the, the, the diagram. Um, another thing that has been, uh, made different is like even though the architecture of Privacy Pass, um, as defined in the RFC, does not specify what a token response or token request looks like, this is defined by like further RFC, it felt a bit wrong to say that like the client sends a token request and a token response, while it's actually like a credential request and a credential response, and therefore, the diagram has been updated accordingly. In term of like brief, um, changelog, and you can see like all the changelog on the draft, um, we've expanded, uh, the modi—the motivation section, um, to like, for instance, could be used to like preserve rate limiting, to have like some bootstrap of, like, new origin that like would have its own, like, private issuer, um, allow for like credential conversion, for instance, from like Blind RSA to like a couple of, like, batch VOPRF, or like Blind RSA to a, a, a credential or etc. There's the move that I mentioned before, we move like the terminology from like token to credential, and have added a few steps, um, there's a request, response, the finalization that we know, and also added the presentation step, which is important, um, for—for—for the credential work, uh, that—that is being conducted. Um, we've also sharpened a bit, uh, the privacy guidance, should be in term of like the metadata, the number of bits per request, and how like conversion work, and like how that might affect like the privacy guarantees which are provided to user. And finally, um, one of the things which was discussed in the, like—like the previous time and was discussed with a few folks, um, is we've added like a concrete HTTP header, uh, which is like Privacy-Pass-Reverse, uh, which is using ACT, for instance, to convey, um, the credential and like be able to get the response. Overall, I still have some open questions with regards to this draft, um, like the main question that I have and like that is, like, kind of, like, one of the main contributions of this work is, like, um, do anonymous credential work need some architecture guidance in Privacy Pass, or is the architecture guidance that we have sufficient? I do feel that at least being able to like define like the steps, um, especially like distinguish between finalization and presentation, is like important, and would be required here. Um, some other questions I have is like the client state is not mentioned anywhere, but seems to be very key. It's been mentioned in like the previous discussion, uh, like about ARC, will be mentioned in like ACT down the line. It seems to be key but is not mentioned anywhere. Maybe that's out of scope for Privacy Pass, but that's something that I think we need to like be able to consider as part of the architecture, because it has quite like some important step, and like the architecture and deployment guidance that we provide. Another question I have is, um, what is the right way to pass a credential request and convey the credential response that would come from the origin? HTTP headers seem convenient to like prototype at this point, but maybe we need to like start considering something else, maybe have some body wrapping, or something else. I don't know what's the nicest method, but that's definitely an open question here. Um, and finally, a big question, um, that we have through this architecture is, like, how do we ensure privacy guarantees? Um, having a bigger deployment, like, opens and like multiplies the surface for, like, the privacy risks. Um, I think one of the things that will be discussed, uh, like—like, and that comes out of like the PACT workshop, that Sam will like present down the line, is even though with our, like, multiple blocks, it would be nice to really tighten them, to like clearly understand, uh, the privacy guarantees that like such systems are providing. Um, yeah. So, I will stop here, um, and happy to have like opinions or questions, um, on that work. Yes, Tommy.

**Tommy Pauly:** All right, hello. Um, yeah, this—so, I I continue to think this is useful to write down. Um, it—it's a case I see. I don't have um, a particular opinion for the relevance in anonymous credentials, but I think other cases still use this, and I think it's useful to uh, specify. Regarding how you pass the credential request and response, or like, essentially how you actually communicate the reverse flow, I- I would suggest we do it similar to how we did the base Privacy Pass uh, redemption flow, where we, you know, we have a specification for, you know, there's—there's the actual interaction that needs to happen. And then we define HTTP headers, and in that case, it was the auth method, but you, know, this—this wouldn't be the auth method, this—this would be something else, but let's have some HTTP headers defined, uh, but they should not be the only way to do this. That if someone is embedding this in some JSON, Protobuf, whatever else they have communicating to the uh, entity that they're doing reverse flow with, they can do that, but there is still a standard default that we can fall back to.

**Thibault Meunier:** Yeah, that totally makes sense, um, and maybe to give another example, like the way we integrate the reverse flow in like Media over QUIC, is not via HTTP header because it's like Media over QUIC, and and therefore, I do agree having like probably like a separate one would like—would be interesting. Um, yes, Ben.

**Benjamin Schwartz:** Hi, uh, so I've just been trying to understand the situation where you need this. Um, I think in the beginning of Privacy Pass, the- the sort of simple expectation of how this situation was handled was that the server's—the origin response would have a Set-Cookie header, and it would set a—a first-party cookie. And so that would become your—you would sort of bootstrap from Privacy Pass into a cookie authentication, and then that would be your—your ongoing cert- uh, certificate or, um, credential. Um, so I guess this would be for cases where, essentially, like ongoing privacy is required after that transition. Is that basically right?

**Thibault Meunier:** Yes, exactly. And, like, again, that's why the lines was with the work being done with credentials, or work being done with like batch, where you probably need to like carry on. It's like when you need actually the unlinkability between the different requests.

**Benjamin Schwartz:** Okay. Um, that's uh, that's helpful to understand. It does seem like there might be a clearer way to model this, uh, as like a new issuance flow, like, it sounds to me like essentially what's happening here is, um, we're using one credential as the, as the permission to access a new issuer, which is then issuing a new credential for a different purpose.

**Thibault Meunier:** Yes, basically, it's exactly that.

**Benjamin Schwartz:** Um, so, maybe we could, if the—if in terms of how this is encoded, if we could match the encodings to the issuance flow, um, maybe that would be a little clearer. Um, my other question about this was, uh, you've talked a lot about using uh, issuing a new credential that replaces the one you were using. Um, what happens in a failure case? I hand over my—my credential, and then the reissuance fails.

**Thibault Meunier:** Uh, yes. I think it's like very similar to what happened when you like present and like redeem, uh, like a Privacy Pass token, and somehow it fails because of like network connection, is like it's a policy which is like left to like how the client is configured. If you think that like it's okay, and like you won't be like linked if you like represent the token, then you can represent it, but like this is like one of the failures—failure cases for like credentials at this point. And again, like, probably like an architecture could help like—like to think that through. So, I don't have all the answers, but like—like for now, that's a client policy and deployment policy.

**Benjamin Schwartz:** Thank you.

**Samuel Schlesinger:** Sam?

**Samuel Schlesinger:** Yeah, um, just to give a little context to Ben, um, some of these reverse flow instantiations are not—so, like, the—the simplest ones are like an interleave redemption and, and, um, issuance, but then some of them like ACT (draft-ietf-privacypass-arc-protocol / draft-ietf-privacypass-arc-crypto), actually, are distinct. So, in particular, the request for the new issuance contains a proof about the redeemed previous credential. And so, it's not exactly like easily, uh, separable, which is why this new architecture is very helpful to like standardize, such that when we instantiate it again and again and again, we can describe it in one place, um, rather than describing this flow in each individual document like in ACT or reverse flow, whatever. Um, and I don't think we can standardize the—like, because of the fact that sometimes they're interlinked, I don't think we can just use the previous standard for, for the responses and the requests, etc.

**Benjamin Schwartz:** Oh, so you're—you're thinking specifically, you're thinking specifically of like, "I can, in an application, I can emulate late origin binding in a different way." Yeah, I don't—that is a perspective.

**Samuel Schlesinger:** Yeah, like, in particular, like, you—you say, in particular, like, "I have my VOPRF, I—I present it, like, I just hand it back," which is great because the client doesn't need to do any computation. And then, um, I just scope it to that particular—like, let's say I'm a—I'm an issuer and I work for a bunch of different origins, right? I'll just say, "This one's used," right? And, and I don't need late origin binding because I've used that one spend anyway, and it can't get used again. So, yeah. Got it. Yeah, I—I—I don't—I have, um, I have nothing substantial to say, uh, in response to that besides, um, this is a feature, this is like a—it's like an ugly corner—corner of ARC (draft-ietf-privacypass-arc-protocol / draft-ietf-privacypass-arc-crypto) that, um, if it, you know, if it turns out to be useful, um, I would want to make sure that we implement it in a different way. Um, so, yeah, maybe that's—maybe that—that broader question, I think, is important to ask ourselves, is do we actually want this feature?

**Benjamin Schwartz:** I—I want to clarify that I do want this feature, but—but I think if we're going to have it, we should implement it by doing a proof of a PQ secure cryptographic hash function, and—and I think that this approach is—is—of—of—the universal hash function here, I think—I think it's a dead end, um, and I want to encourage the group to, if it's not a dead end, convince ourselves of that today, otherwise, try to, you know, explore new—

**Christopher Patton:** What—what is a PQ secure hash function? What do you mean by that?

**Benjamin Schwartz:** Like, like, so, DY can be inverted with a quantum computer, right? Yep. But something which is actually a one-way function in the presence of a quantum computer would be a PQ—PQ secure hash function. I- maybe this—this word is not right, but I think—I think you get my idea.

**Christopher Patton:** I don't quite, but I, um, let me—let me—let me try to put that, let me try to, um, rephrase. Um, so, the—the reason you think that universal hash, UHF, is dead is because of the computational cost? Or is there a different reason?

**Benjamin Schwartz:** Um, I don't think it's better than the simpler things we have on tap. I think it's worse. And, the thing that I want is a compressed credential that I can present a large number of times, potentially trading off some computational cost at presentation time. And, this doesn't give me that because batch VOPRF is basically, asymptotically at least, the same storage space. And, with batch VOPRF, I don't need to do any computation at presentation, whereas if I had something that was, um, like similar to this DY idea, but instead of proving DY, I prove Poseidon or something like this, which is, I believe, thought to be secure in the presence of a—or thought to be one-way in the presence of a quantum computer, then I can still have a compressed credential and I can use it for a long time, and I can save my client lots of storage space by doing so.

**Christopher Patton:** Uh, but this is compressed. I mean, the—the cost of this is—is in terms of communication cost is not—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Wood:** I see.

**Samuel Schlesinger:** Any more question? Okay, if no more question, I will, like, try to get back to you, Ben, about the issuance flow on the list. And, yeah, I will pass to Sam, I think, for the next presentation.

**Samuel Schlesinger:** Okay, so Sam, you're up, and this is the PACT Workshop Update.

**Samuel Schlesinger:** Dennis also said in the chat that something that I think is relevant, which is like, "time to standardization is like an important aspect of all of this, and ZKVMs are not easy to standardize."

Okay, so, here's a presentation that is about a workshop that we held last week in the Cloudflare London office, under the auspices of the Anti-Fraud Community Group in the W3C. This is work by a lot of people, but me, Dennis, and Thibault collaborated on these slides, and I'll present them and we'll, you know, we'll direct questions to whoever can answer them best.

So, what—what is PACT? Like, what are we talking about? Basically, it's a problem statement that Dennis, Eric Trautman, and I—Eric is also from Google, sorry, I'm from Google, for context, wrote up in the proposals repository of the Anti-Fraud Community Group's GitHub organization. Basically, it's a set of guardrails and requirements for a cross-browser private token API that we think would be helpful to reduce user friction on the web.

Why is it relevant here? Well, we are chartered to produce a browser API for private tokens on the web, and so I figured mentioning it to you guys was a good idea. And again, we convened a workshop last week.

And I'll just go over what we did each day. So, in the first day, we talked about use cases. And it really turned out that the primary use case, like the one that we want to spend most of our energy on, is reducing friction for user agents on the web, primarily by reusing friction across origins in a privacy-preserving way.

And there was some other use cases in the original document, so private access control tokens, of course, implies that there's some private access control involved. We would like to do that, but we don't want to focus on it, we really want this use case to be what guides our efforts here.

And the point of this is that users deal with the same friction all the time. So, like, they'll get the same CAPTCHA site to site. They'll have to log in to their accounts, give a phone number, whatever, lots of different sites. Also, device attestation and various device signals are permeating the web in various different vectors of entry. And we'd like to minimize that as much as possible.

And so on the second day, we discussed an architecture that we think could solve this, a three-party architecture with a client—well, really it's four-party if you count the origin—there's a client which holds credentials, you know, they're like the browser or whatever, and they produce presentations of those credentials.

There's an anchor that has maybe some relationship with a user. They don't necessarily have to, but in a lot of the cases we consider, they have some relationship with the user, maybe an account or whatever, and they provide a limited number of endorsements per user. And their role is really to provide some limited amount of Sybil resistance.

Chris Patton said, "anchor equals Privacy Pass attester." There's some messy hybrid of an attester and an issuer. That's basically right. Yeah, Martin's point is correct as well, that this isn't exactly meant to fit directly into Privacy Pass. I just figured we'd talk about it here because we're chartered to deliver something very similar on the web, so this is the thing that we think might work for that.

Okay, and so then the moderator is the party which actually helps the origin or the site—I used origin here, but I should have used site—protect their site with some policy. So, for ACTs, it might be that they have some rate-limited amount of access to use the site. For the tiered rate-limited access, you know, you could imagine something like that. You can imagine a lot of different things, and we can talk about specific examples. We talked about a bunch of specific ideas in the workshop, but they would take a little longer to describe, so I didn't here.

And the idea is that they convert, they transfer an anchor credential to a moderator credential, where that moderator credential is a stateful credential in that style of ACT state machines that I talked about earlier. And they gate origin-level updates and queries, so, like, you know, you want to get some resource from an origin, well, maybe you need to spend credits, or maybe you need to prove that your credential has some particular property to get that.

Okay, and then moving on, we demand some privacy properties of this system, moderator credential unlinkability. So, an origin should not be able to—or a site, I said origin all over here, a site should not be able to link two valid credential presentations to the same client. It also shouldn't be able to link the issuance as well.

We also want anchor credential unlinkability, so a moderator shouldn't be able to link an endorsement presentation, which is that anchor credential, to its issuance, nor link two endorsement presentations to each other.

And then we want issuer hiding, which is something that we haven't really explored here, which is the idea that the transfer of the endorsement to the moderator should not reveal which specific anchor that you came from. It should just reveal that you are—you hold an anchor credential from a specific set $A$ and not which one.

And it's important to mention here that post-quantum adversaries are in scope for everything here. And so things like ARC, though they are lovely from a performance perspective, are are not viable for our threat model.

Okay, so now we'll just go through the architecture as we described it and whiteboarded it out. Please let me know if there are things that are wrong here, you know, we tried our best, but feedback is going to be good. So, anchor issuance is what the client does to get an issuance from this anchor that has some relationship with them, potentially. This should look a lot like regular old blind signature issuance, right? So, you make some context, which is some client secrets. You build a request from those client secrets and the public key of the anchor. Then you send those requests with some blob of authorization data. The anchor will authorize that blob, you know, maybe it's checking some sort of account cookie or something, lots of things could happen here. And then they'll produce some response along with a status of whether it succeeded or not, and send it back to the client, which will then finalize that credential into an endorsement, which then they will transfer when they want to access a specific site. So, that site will say, "I am protected by moderator $M$." Or sorry, that's the wrong letter, moderator $M$, okay? And then the client will go and transfer the anchor credential to a moderator credential.

So, this should look a lot like Thibault's reverse flow Privacy Pass. It's an interleaved issuance and redemption. And the idea is that we're presenting the endorsement in an issuer-hiding way, where we prove that we have a valid endorsement from one of the anchors in the set $A$ that the moderator accepts. Then the moderator verifies that the anchor presentation is actually correct. I think "request" should also be a parameter here. Then it computes some diff that it wants to, based on the stuff that the origin sent it, and whatever, you know, things in the world that it thinks are relevant at that particular moment. And then it will create a response for that client, along with whether or not it succeeded. So, in the ACT drafts as they as they exist in the repository and will be published before 1/26, $D$ here would be the amount that it wants to, like, refund, for example, like if you promised you could spend 60 minutes, but you only spent 20 minutes, $D$ would be 40. And then we respond to the moderator credential, or with the updated moderator credential. And then the origin will get the status of that, they will integrate it with the original, sort of, semantic client request into the semantic response to that client for that—for that origin. And then they'll send it all back, and then the credential will be finalized on the client side, and then stored for later. I saw a question from Chris. Let's, I think, let's do questions inline here.

**Christopher Patton:** Um, is it a goal that the moderator not know who the—what are they called—the anchor is?

**Samuel Schlesinger:** That's right.

**Christopher Patton:** So, the—so the client has a credential issued from the anchor. The moderator will verify that credential. It's going to verify that anchor-issued credential before issuing its own credential.

**Samuel Schlesinger:** That's right. It's going to verify a presentation of that credential, which is issuer-hiding.

**Christopher Patton:** How is it issuer-hiding?

**Samuel Schlesinger:** Through some yet-unspecified thing, an example would be like if we were able to use pairings, we could use some BBS-type approach using pairings. We are—we are, due to various constraints of various parties, not—not going to go down that pairing route, and so we need to do something slightly different. We can talk about this, but I think moving through here first is probably a good idea.

**Christopher Patton:** Okay, okay, thanks.

**Samuel Schlesinger:** Yep, yep.

**Samuel Schlesinger:** Yeah, blind ring signature, you know, lots of different things you could imagine. The problem with a ring signature, if I understand it correctly, is that you would need to know in advance what the ring is, whereas we would like users to be able to come to their—like, like, you're not supposed to go back to your anchor at this transfer flow. If you have not met that anchor before, if you've not met any anchor in that set, you're just supposed to say, "I have nothing for you." And that's like important for timing attacks and other such things.

Okay, so, um, with that—with that in mind, the goal then is to instantiate this late context binding thing with information-theoretic techniques, and the question is how do we do that? So, Michael Rosenberg and Michele Orrù have have have made an idea using universal hash functions. I credit this—I credit them with this idea just because they've done, like, an actual write-up, but this is, like, based on like, there's like a crypto paper, "Everlasting Credentials" that is related to this. I also think Watson Ladd at some point brought up a related idea on the list, but this was before at least I personally had the full context for this. By the way, the only reason I'm presenting this is, Michael is no longer at Cloudflare, the company that I work, and so that's why, um, I'm—I'm sort of filling in for him. I just wanted to make sure today that we had time to discuss this. So the key idea is that we're going to replace the DYPRF with a universal hash function. A universal hash function is just a hash function that is guaranteed to, um, I guess, the way I would think about it is we have, it's a polynomial with of degree $N$, large degree $N$, with random coefficients, and random and known to the—to the credential holder, but not the issuer/verifier. And so during presentation, I just evaluate this polynomial with random coefficients at a point that is computed from my presentation context and my nonce. And that's how I get my tag. So, um, this is perfectly hiding up to the presentation limit, so the math of polynomials basically guarantees that, as long as the number of points I evaluate this polynomial at doesn't exceed the presentation limit, then, every tag perfectly hides the point at which it was evaluated.

Yes. Um, so, that's the kind of the basic idea. So, during credential issuance, we, um, we commit to the coefficients of this polynomial. This commitment is, um, like one group element, so it's very, very cheap in terms of communication cost. This is accomplished with a KZG commitments, there's details in Michele's paper that I'm referring to here. Um, and then we have to add some additional constraints to the sigma proofs. Um, the major cost of this is that, um, the computation is now linear in the presentation limit, because I have to evaluate this degree $N$ polynomial, um, whereas with DYPRF, it's—it's—it's sublinear in the presentation limit.

Okay. So, um, just to mention some caveats, I kind of already mentioned one, so one is that this is a little looser than we gener—like, tend to think of this, like, the limit is really the number, I believe, and- and I- I- I could be wrong about this, um, I'm—I'm not 100% confident on this, but, the limit is the number of unique nonce/presentation context pairs, not the number of nonces per context. So, that is a significant difference between, um, ARC and, ARC if we modified it this way. Um, so, with that—with that in mind, the computational cost is probably the main downside for this, so if you're going to use ARC for, like, a presentation limit of 1000, then, I think, Sam put together some benchmarks at some point, I don't remember the concrete numbers, but, it's, you know, issuance, issuance and presentation computation time is going to—is going to go up quite a bit. Um, that said, I do think, um, one thing I believe we've talked about in the past is adding something like late binding to ACT. This, to me, actually seems like a fairly reasonable application. Imagine you used, a universal hash function to derive the first nullifier, um, for a given presentation context, and thereafter you just use ACT as normal. I think this sort of thing, could, basically, your presentation limit is not going to be that high, it's not going to be as high as it would be for ARC, and also, um, most of the, you know, all most of the costs you don't actually, is not carried over for every ACT presentation that you do. Um, another thing, another kind of nuance is, um, Michael's write-up uses BBS rather than CMZ for the algebraic MAC. And, um, I think this is probably because it's more friendly with KZG, but I'm not actually 100% sure. It might be possible that you can continue to use CMZ.

Finally, I just wanted to note that, like, uh, just from talking to Michael, he seems pretty confident in this design, but I do think, uh, you know, this is a substantial change, either to ARC or ACT, and we would want to do some new security analysis. Um, and just incidentally, I wanted to mention that there are differences between the security analysis for ARC and ACT that need a—that do matter for things like how do we pick a curve, how do we pick, um, parameters for this—for this scheme. Uh, and I just wanted to call out that, like, the—they're not on the same footing right now, and this might lead us to the wrong conclusions about, you know, picking curves for one or the other. And that's something, we need to—we need to—to solve for, that's related here.

Um, I think that's the end of my slides. I can get into details of, uh, these are just screenshots from Michael Rosenberg's write-up. Um, so I'll leave it there. Um, in terms of what we should consider, um, I think I'd be in favor of, I personally don't want to, uh, deploy ARC as it is today, I would want it to make sure it's at least PQ unlinkable. Um, uh, so, if, if we want to continue ARC, that's something I suggest we consider, um, and then, um, yeah, and I'm not sure if it's relevant for ACT right now, but, that's—that's—that's, I guess, what I would like us to talk about. Go ahead, Sam.

**Benjamin VanderSloot:** Hello, um, I was just hoping to understand from your perspective where this beats out like batch VOPRF. Because that, from my end, I just can't figure out where I would use this instead of batch VOPRF.

**Christopher Patton:** Um, yeah, so the—the—it's—it has to do with this, uh, this late context binding feature. Um, the—so I guess the way I would use, um, um, yeah, I—I—I—yeah, it—it depends on the use case, I guess. What—what use case specifically do you have in mind?

**Benjamin VanderSloot:** I guess I'm just imagining anything where the issuer and the redeemer are the same party, which is all the places where you can use ARC, batch VOPRF seems, like, it's better. Um, because that, it would be, I think, it would be different if this was publicly verifiable. Um, I think I could imagine late origin binding being—being helpful there, but because the issuer is—

**Christopher Patton:** Oh, so you're—you're thinking specifically, you're thinking specifically of like, "I can, in an application, I can emulate late origin binding in a different way." Yeah, I don't—that is a perspective.

**Benjamin VanderSloot:** Yeah, like, in particular, like, you—you say, in particular, like, "I have my VOPRF, I—I present it, like, I just hand it back," which is great because the client doesn't need to do any computation. And then, um, I just scope it to that particular—like, let's say I'm a—I'm an issuer and I work for a bunch of different origins, right? I'll just say, "This one's used," right? And, and I don't need late origin binding because I've used that one spend anyway, and it can't get used again. So, yeah.

**Christopher Patton:** Got it. Yeah, I—I—I don't—I have, um, I have nothing substantial to say, uh, in response to that besides, um, this is a feature, this is like a—it's like an ugly corner—corner of ARC that, um, if it, you know, if it turns out to be useful, um, I would want to make sure that we implement it in a different way. Um, so, yeah, maybe that's—maybe that—that broader question, I think, is important to ask ourselves, is do we actually want this feature?

**Benjamin VanderSloot:** I—I want to clarify that I do want this feature, but—but I think if we're going to have it, we should implement it by doing a proof of a PQ secure cryptographic hash function, and—and I think that this approach is—is—of—of—the universal hash function here, I think—I think it's a dead end, um, and I want to encourage the group to, if it's not a dead end, convince ourselves of that today, otherwise, try to, you know, explore new—

**Christopher Patton:** What—what is a PQ secure hash function? What do you mean by that?

**Benjamin VanderSloot:** Like, like, so, DY can be inverted with a quantum computer, right? Yep. But something which is actually a one-way function in the presence of a quantum computer would be a PQ—PQ secure hash function. I- maybe this—this word is not right, but I think—I think you get my idea.

**Christopher Patton:** I don't quite, but I, um, let me—let me—let me try to put that, let me try to, um, rephrase. Um, so, the—the reason you think that universal hash, UHF, is dead is because of the computational cost? Or is there a different reason?

**Benjamin VanderSloot:** Um, I don't think it's better than the simpler things we have on tap. I think it's worse. And, the thing that I want is a compressed credential that I can present a large number of times, potentially trading off some computational cost at presentation time. And, this doesn't give me that because batch VOPRF is basically, asymptotically at least, the same storage space. And, with batch VOPRF, I don't need to do any computation at presentation, whereas if I had something that was, um, like similar to this DY idea, but instead of proving DY, I prove Poseidon or something like this, which is, I believe, thought to be secure in the presence of a—or thought to be one-way in the presence of a quantum computer, then I can still have a compressed credential and I can use it for a long time, and I can save my client lots of storage space by doing so.

**Christopher Patton:** Uh, but this is compressed. I mean, the—the cost of this is—is in terms of communication cost is not—

**Benjamin VanderSloot:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin VanderSloot:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin VanderSloot:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin VanderSloot:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin VanderSloot:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin VanderSloot:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin VanderSloot:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin VanderSloot:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin VanderSloot:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin VanderSloot:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin VanderSloot:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin VanderSloot:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin VanderSloot:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin VanderSloot:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin VanderSloot:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin VanderSloot:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin VanderSloot:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin VanderSloot:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin VanderSloot:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin VanderSloot:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin VanderSloot:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin VanderSloot:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin VanderSloot:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin VanderSloot:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin VanderSloot:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin VanderSloot:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin VanderSloot:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin VanderSloot:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin VanderSloot:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Wood:** I see.

**Christopher Patton:** Anyway, we'll talk about this on the list, so, um, we can move on if the chairs want to move on. Go ahead, Sam.

**Samuel Schlesinger:** All right, yeah. Thank you. I think, um, next we have, uh, Thibault, you're up, and this is Privacy Pass reverse flow draft (draft-ietf-privacypass-reverse-flow) update. Let me make sure—are you asked for presenting?

**Thibault Meunier:** Yeah, I've asked for control of the slide, but—

**Samuel Schlesinger:** You should have control now.

**Thibault Meunier:** Perfect. Okay, um, so, yeah. Hey everyone, uh, and I'm going to present Privacy Pass reverse flow, uh, the like draft version of the draft, um, interestingly, like the last time I presented, I think was in March 2025, and like the draft kind of has evolved, along with like some changes that like happened in the working group, and I wanted to like regroup, um, because this seems like, like relevant to some of the work that will be presented today. Um, so, overall, the context for the reverse flow is like, um, the architecture that like we know and love, like which is, like, standardized in the RFC, where like you have a client going to an origin, being challenged, working with like an attester and an issuer, to—to attest, get, uh, like send a token request, get a token response, finalizing the token locally, and then, once it has a token, the client would go to the origin with a request and present the token, um, to actually be redeemed and, uh, validate and authenticate, uh, as Privacy Pass. There's a couple of limitations should be to aid, to move of like the rate limiting in term of like, um, what if like we—like the client needs to like keep carry on, uh, like contacting the origin, and so that, uh, like started like the reverse flow, um, that that we presented um, in March last year. And so, the idea is it's exactly the same thing as like Privacy Pass, and so that's why like the diagram on the right, um, like the origin, the client, the attester, and the issuer, is like exactly the same. The only trick, um, that happened is like instead of like simply presenting, um, the token, the client would like present a token plus request a new token, for an issuer which is in control of the origin. And so that's what is illustrated in this diagram, where like the client makes a request with a token, uh, redemption, and a new token request. Once the origin like processes, the, um, like the full request, it—the origin may send the token request to like its own, like, a new issuer, get the token response, and like forwards it—the forwards the token response, along with like the normal response, to the client. Since then, um, has like evolved a bit, um, to like include, um, a couple of, um, like new steps, um, it was important, uh, specifically with like the credential work, um, to like distinguish, um, finalization and presentation, which were like two distinct steps, um, that—that—that were being conducted, should be with like ARC, should be with ACT. And so, like, these have been like clearly distinguished, um, in the, the, the diagram. Um, another thing that has been, uh, made different is like even though the architecture of Privacy Pass, um, as defined in the RFC, does not specify what a token response or token request looks like, this is defined by like further RFC, it felt a bit wrong to say that like the client sends a token request and a token response, while it's actually like a credential request and a credential response, and therefore, the diagram has been updated accordingly. In term of like brief, um, changelog, and you can see like all the changelog on the draft, um, we've expanded, uh, the modi—the motivation section, um, to like, for instance, could be used to like preserve rate limiting, to have like some bootstrap of, like, new origin that like would have its own, like, private issuer, um, allow for like credential conversion, for instance, from like Blind RSA to like a couple of, like, batch VOPRF, or like Blind RSA to a, a, a credential or etc. There's the move that I mentioned before, we move like the terminology from like token to credential, and have added a few steps, um, there's a request, response, the finalization that we know, and also added the presentation step, which is important, um, for—for—for the credential work, uh, that—that is being conducted. Um, we've also sharpened a bit, uh, the privacy guidance, should be in term of like the metadata, the number of bits per request, and how like conversion work, and like how that might affect like the privacy guarantees which are provided to user. And finally, um, one of the things which was discussed in the, like—like the previous time and was discussed with a few folks, um, is we've added like a concrete HTTP header, uh, which is like Privacy-Pass-Reverse, uh, which is using ACT, for instance, to convey, um, the credential and like be able to get the response. Overall, I still have some open questions with regards to this draft, um, like the main question that I have and like that is, like, kind of, like, one of the main contributions of this work is, like, um, do anonymous credential work need some architecture guidance in Privacy Pass, or is the architecture guidance that we have sufficient? I do feel that at least being able to like define like the steps, um, especially like distinguish between finalization and presentation, is like important, and would be required here. Um, some other questions I have is like the client state is not mentioned anywhere, but seems to be very key. It's been mentioned in like the previous discussion, uh, like about ARC, will be mentioned in like ACT down the line. It seems to be key but is not mentioned anywhere. Maybe that's out of scope for Privacy Pass, but that's something that I think we need to like be able to consider as part of the architecture, because it has quite like some important step, and like the architecture and deployment guidance that we provide. Another question I have is, um, what is the right way to pass a credential request and convey the credential response that would come from the origin? HTTP headers seem convenient to like prototype at this point, but maybe we need to like start considering something else, maybe have some body wrapping, or something else. I don't know what's the nicest method, but that's definitely an open question here. Um, and finally, a big question, um, that we have through this architecture is, like, how do we ensure privacy guarantees? Um, having a bigger deployment, like, opens and like multiplies the surface for, like, the privacy risks. Um, I think one of the things that will be discussed, uh, like—like, and that comes out of like the PACT workshop, that Sam will like present down the line, is even though with our, like, multiple blocks, it would be nice to really tighten them, to like clearly understand, uh, the privacy guarantees that like such systems are providing. Um, yeah. So, I will stop here, um, and happy to have like opinions or questions, um, on that work. Yes, Tommy.

**Tommy Pauly:** All right, hello. Um, yeah, this—so, I I continue to think this is useful to write down. Um, it—it's a case I see. I don't have um, a particular opinion for the relevance in anonymous credentials, but I think other cases still use this, and I think it's useful to uh, specify. Regarding how you pass the credential request and response, or like, essentially how you actually communicate the reverse flow, I- I would suggest we do it similar to how we did the base Privacy Pass uh, redemption flow, where we, you know, we have a specification for, you know, there's—there's the actual interaction that needs to happen. And then we define HTTP headers, and in that case, it was the auth method, but you, know, this—this wouldn't be the auth method, this—this would be something else, but let's have some HTTP headers defined, uh, but they should not be the only way to do this. That if someone is embedding this in some JSON, Protobuf, whatever else they have communicating to the uh, entity that they're doing reverse flow with, they can do that, but there is still a standard default that we can fall back to.

**Thibault Meunier:** Yeah, that totally makes sense, um, and maybe to give another example, like the way we integrate the reverse flow in like Media over QUIC, is not via HTTP header because it's like Media over QUIC, and and therefore, I do agree having like probably like a separate one would like—would be interesting. Um, yes, Ben.

**Benjamin Schwartz:** Hi, uh, so I've just been trying to understand the situation where you need this. Um, I think in the beginning of Privacy Pass, the- the sort of simple expectation of how this situation was handled was that the server's—the origin response would have a Set-Cookie header, and it would set a—a first-party cookie. And so that would become your—you would sort of bootstrap from Privacy Pass into a cookie authentication, and then that would be your—your ongoing cert- uh, certificate or, um, credential. Um, so I guess this would be for cases where, essentially, like ongoing privacy is required after that transition. Is that basically right?

**Thibault Meunier:** Yes, exactly. And, like, again, that's why the lines was with the work being done with credentials, or work being done with like batch, where you probably need to like carry on. It's like when you need actually the unlinkability between the different requests.

**Benjamin Schwartz:** Okay. Um, that's uh, that's helpful to understand. It does seem like there might be a clearer way to model this, uh, as like a new issuance flow, like, it sounds to me like essentially what's happening here is, um, we're using one credential as the, as the permission to access a new issuer, which is then issuing a new credential for a different purpose.

**Thibault Meunier:** Yes, basically, it's exactly that.

**Benjamin Schwartz:** Um, so, maybe we could, if the—if in terms of how this is encoded, if we could match the encodings to the issuance flow, um, maybe that would be a little clearer. Um, my other question about this was, uh, you've talked a lot about using uh, issuing a new credential that replaces the one you were using. Um, what happens in a failure case? I hand over my—my credential, and then the reissuance fails.

**Thibault Meunier:** Uh, yes. I think it's like very similar to what happened when you like present and like redeem, uh, like a Privacy Pass token, and somehow it fails because of like network connection, is like it's a policy which is like left to like how the client is configured. If you think that like it's okay, and like you won't be like linked if you like represent the token, then you can represent it, but like this is like one of the failures—failure cases for like credentials at this point. And again, like, probably like an architecture could help like—like to think that through. So, I don't have all the answers, but like—like for now, that's a client policy and deployment policy.

**Benjamin Schwartz:** Thank you.

**Samuel Schlesinger:** Sam?

**Samuel Schlesinger:** Yeah, um, just to give a little context to Ben, um, some of these reverse flow instantiations are not—so, like, the—the simplest ones are like an interleave redemption and, and, um, issuance, but then some of them like ACT (draft-ietf-privacypass-arc-protocol / draft-ietf-privacypass-arc-crypto), actually, are distinct. So, in particular, the request for the new issuance contains a proof about the redeemed previous credential. And so, it's not exactly like easily, uh, separable, which is why this new architecture is very helpful to like standardize, such that when we instantiate it again and again and again, we can describe it in one place, um, rather than describing this flow in each individual document like in ACT or reverse flow, whatever. Um, and I don't think we can standardize the—like, because of the fact that sometimes they're interlinked, I don't think we can just use the previous standard for, for the responses and the requests, etc.

**Benjamin Schwartz:** Oh, so you're—you're thinking specifically, you're thinking specifically of like, "I can, in an application, I can emulate late origin binding in a different way." Yeah, I don't—that is a perspective.

**Samuel Schlesinger:** Yeah, like, in particular, like, you—you say, in particular, like, "I have my VOPRF, I—I present it, like, I just hand it back," which is great because the client doesn't need to do any computation. And then, um, I just scope it to that particular—like, let's say I'm a—I'm an issuer and I work for a bunch of different origins, right? I'll just say, "This one's used," right? And, and I don't need late origin binding because I've used that one spend anyway, and it can't get used again. So, yeah. Got it. Yeah, I—I—I don't—I have, um, I have nothing substantial to say, uh, in response to that besides, um, this is a feature, this is like a—it's like an ugly corner—corner of ARC (draft-ietf-privacypass-arc-protocol / draft-ietf-privacypass-arc-crypto) that, um, if it, you know, if it turns out to be useful, um, I would want to make sure that we implement it in a different way. Um, so, yeah, maybe that's—maybe that—that broader question, I think, is important to ask ourselves, is do we actually want this feature?

**Benjamin Schwartz:** I—I want to clarify that I do want this feature, but—but I think if we're going to have it, we should implement it by doing a proof of a PQ secure cryptographic hash function, and—and I think that this approach is—is—of—of—the universal hash function here, I think—I think it's a dead end, um, and I want to encourage the group to, if it's not a dead end, convince ourselves of that today, otherwise, try to, you know, explore new—

**Christopher Patton:** What—what is a PQ secure hash function? What do you mean by that?

**Benjamin Schwartz:** Like, like, so, DY can be inverted with a quantum computer, right? Yep. But something which is actually a one-way function in the presence of a quantum computer would be a PQ—PQ secure hash function. I- maybe this—this word is not right, but I think—I think you get my idea.

**Christopher Patton:** I don't quite, but I, um, let me—let me—let me try to put that, let me try to, um, rephrase. Um, so, the—the reason you think that universal hash, UHF, is dead is because of the computational cost? Or is there a different reason?

**Benjamin Schwartz:** Um, I don't think it's better than the simpler things we have on tap. I think it's worse. And, the thing that I want is a compressed credential that I can present a large number of times, potentially trading off some computational cost at presentation time. And, this doesn't give me that because batch VOPRF is basically, asymptotically at least, the same storage space. And, with batch VOPRF, I don't need to do any computation at presentation, whereas if I had something that was, um, like similar to this DY idea, but instead of proving DY, I prove Poseidon or something like this, which is, I believe, thought to be secure in the presence of a—or thought to be one-way in the presence of a quantum computer, then I can still have a compressed credential and I can use it for a long time, and I can save my client lots of storage space by doing so.

**Christopher Patton:** Uh, but this is compressed. I mean, the—the cost of this is—is in terms of communication cost is not—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have linear—do you mean like—

**Benjamin Schwartz:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Christopher Patton:** Any solution would have**Christopher Patton:** linear storage cost. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—the benefit—to be clear, it would be great if—if—um, I want that too, but it's the storage cost that I care about, because the—the VOPRF and this both have linear storage costs. And so, I'll choose to use VOPRF instead.

**Benjamin Schwartz:** Any solution would have linear—do you mean like—

**Christopher Patton:** No, no, no, not the communication cost, the—