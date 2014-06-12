---
layout: page
title: Frequently Asked Questions
published: true
---

* FAQs
{:toc}

<p>&nbsp;</p>

----


#### What is Open Source Software (OSS)?

Open Source Software (OSS) is software that also includes the program's source code.
In almost all cases, the software is licensed such that it can be modified by anyone
and used in any environment.  It typically doesn't cost anything and there are no
legally binding guarantees.  The official US Department of Defense
[definition](http://dodcio.defense.gov/Portals/0/Documents/OSSFAQ/2009OSS.pdf) 
is "software for which the human-readable source code is available for use, study, re-use, modification, enhancement,
and re-distribution by the users of that software".<a href="#top" class="reversefootnote">↩</a>



#### What are the key benefits and risks of using OSS?

An organization does not have to officially procure or purchase open 
source software licenses, as, under most licenses, the software and it's source code
are free and can be modified as needed. So, from a product procurement perspective, OSS
is not an issue.  However, you need the skills to integrate and maintain the software.
Additionally, most open source software does not come with a warranty, so, if it doesn't
do what you expect, or it breaks, you must rely on the product's community for support.

Community support, in many cases is quite good and you frequently deal with people who 
are intimately familiar with the inner workings of the product. They may very well be the 
software's author.  That said, some communities and products go stale and community support
is difficult to find. Have the in-house skills, in these cases, is very helpful.
<a href="#top" class="reversefootnote">↩</a>

Another risk is the loss of personal identifying information, or _PII_, which may accidentally
be in the software's source code.  Even the best programmers
and security specialists make mistakes and these can be costly to an organization's reputation and, 
for government agencies, this can affect public trust. Organizations should implement sufficient
quality controls and code reviews to reduce this risk.  Refer to the [git workflow document](pages/git_workflow)
for ideas.

An organization who is actively accepting changes from the public runs the risk of inadvertently 
accepting undesirable code. The code could have bugs, security vulnerabilities, and other nastiness.
Again, implementing and following good workflows greatly reduces these risks.



#### What kind of license should we use?

Open source software suffers from a fragmented plethora of licensing and there
are many good practical and philosophical arguments why one license 
should be chosen over another and your situation may vary.  Start with the
[Open Source Initiative](http://opensource.org/) for licensing considerations.

Some government agencies consider the software and code they produce as 
being in the public domain, and there are various descriptions of that; e.g.,
[CC0](http://creativecommons.org/publicdomain/zero/1.0/).

The point is to make
make sure the government is indemnified and does not try to restrict use of the
source code. <a href="#top" class="reversefootnote">↩</a>




#### What are the restrictions and what should we look out for?

Typically, there are no restrictions on the use and modification of OSS. Where
it gets complex is on redistribution.  You need to make sure that you follow the
original license.

Where the government can be challenged is when software is written by a contractor
**and** the contractor didn't waive their rights to the work product in the original
contract. In cases like this, ownership and rights over the source code can be ambiguous.
This is likely a bigger issue with larger contracts that have been in place for a long
time. See
[http://www.acq.osd.mil/dpap/dars/dfars/html/current/252227.htm](http://www.gpo.gov/fdsys/pkg/USCODE-2009-title41/html/USCODE-2009-title41-chap4-subchapIV-sec264b.htm) <a href="#top" class="reversefootnote">↩</a>



#### How do I get people in my organization to adopt open source?

Education is key. OSS is a significant paradigm shift for many and the
process to change that paradigm is _a process_.

It may also help to have a small focus group or pilot
project that can demonstrate the strengths and weaknesses of open source adoption
in a given environment. <a href="#top" class="reversefootnote">↩</a>




#### Why do developers participate in OSS if they don't get paid?
There a many reasons; some are individual and are others may be more generalized. 

A developer's reputation and ability get good jobs can be greatly improved by participating in OSS. 
Effectively, participating in OSS builds a public portfolio that can be used by the developer and prospective 
employers to determine if there is a good match.  Because of the need for public reputation, developers pay
often more attention to detail, security, and quality than if the software were not facing the public.

Many developers work remotely and in very specialized areas.  OSS is global which allows developers to 
connect with a broad and diverse community.  In many cases, developers collaborate and forge strong partnerships
and friendships with other developers and may never meet face-to-face.  <a href="#top" class="reversefootnote">↩</a>


#### What is at OpenSource.gov?  

OpenSource.gov is a website for [open source intelligence](http://en.wikipedia.org/wiki/Open-source_intelligence).  This is intelligence material that has been gleaned from public sources.  The site is available to anyone with a .gov email addrss but unfortunately is not relevant to our open source efforts.  

*[OSS]: Open Source Software
