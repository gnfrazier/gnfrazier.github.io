---
layout: post
title: My Thoughts on Rust
tags: rust python learning opinion 
---

<div class="img_center">
  ![Rust-Lang Logo]({{ site.baseurl }}/images/rust-logo-blk.svg)
</div>
I have been interested in Rust for about a year, in January 2017 I went through to about chapter 4 of [The Book](https://doc.rust-lang.org/book/second-edition/ "Rust Lang.org - The Book 2nd Edition"). I found Rust very enjoyable, different in its compiled-ness, attractive in its toolchain and stunningly fast to run. I described rust to a coworker.

> If Python is like a Toyota Corolla, Rust is like a Tesla.

The more I think about both Python and Rust, the more I find that statement fitting. 

| Corolla                                                                                                                                                                | Python                                                                                                                      |     | Tesla                                                                                        | Rust                                                                                                                 |     |     |     |     |     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | --- | -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | --- | --- | --- | --- | --- |
| Common Teen or College Car                                                                                                                                             | Common first language or learned in college                                                                                 |     | Rare for first car                                                                           | Rare for first language, not taught at university                                                                    |     |     |     |     |     |
| [44.1 million sold](https://newsroom.toyota.co.jp/en/corolla50th/history/by_the_numbers/ "Toyota by the Numbers - Corolla 50th Aniversary")                            | Number 2 by volume on github                                                                                                |     | [236k sold](https://en.wikipedia.org/wiki/Tesla,_Inc.#cite_ref-82 "Wikipedia - Tesla Sales") | Ranked [18th](http://redmonk.com/sogrady/2017/03/17/language-rankings-1-17/ "Redmonk - Language Rankings") on github |     |     |     |     |     |
| Base model is not fast                                                                                                                                                 | Vanilla Python not fast                                                                                                     |     | Performance baked into the design                                                            | Designed for Speed                                                                                                   |     |     |     |     |     |
| Steady Evolution of Design                                                                                                                                             | Few breaking changes                                                                                                        |     | Made by hand, few identical vehicles                                                         | Many core libraries still in pre 1.0 state                                                                           |     |     |     |     |     |
| Your grandmother drove one in college [(1966)](https://newsroom.toyota.co.jp/en/corolla50th/history/by_the_numbers/ "Toyota by the Numbers - Corolla 50th Aniversary") | [Python 1.0 - 1994](<http://python-history.blogspot.com/2009/01/brief-timeline-of-python.html - Python History - Timeline>) |     | [Founded 2003](https://en.wikipedia.org/wiki/Tesla,_Inc. "Wikipedia - Tesla")                | [Rust 1.0 - 2015](https://blog.rust-lang.org/2015/05/15/Rust-1.0.html "Rust Lang - Announcing 1.0...")               |     |     |     |     |     |

In light of all this, Rust is just hard to learn. I don't want to have to think about thread safety and ownership and memory usage. I just want to write some code and get work done. It is rare that a difference of 3ms vs 3 hours in run time makes a difference for me, what does make a difference is 15 minutes vs 5 hours to code it. After a few toy programs, I lost interest.

I still follow the Rust community. When they started their push to [lower the bar to learning Rust](https://blog.rust-lang.org/2017/02/06/roadmap.html "Rust Lang Blog - 2017 Roadmap") I became intrigued again. With their successful push of so many [core libraries to 1.0 in December 2017](https://blog.rust-lang.org/2017/12/21/rust-in-2017.html "Rust Lang Blog - What We Achived in 2017"), I thought I would try again. 

For some reason, it is still not sticking for me. I get to the part where The Book starts to explain ownership and suddenly I lose interest. There are some books scheduled to publish this spring. I'll pick one up to see if that helps. Otherwise, I may try go-lang. 

 For now, I will stick with Python where I can get some work done. 

#### Update:

The day after I wrote this post, I read [Why is Rust Difficult? by Micheal Vaner](https://vorner.github.io/difficult.html). He perfectly outlines where I struggle with Rust and brings me to another question. Is there an eloquent explanation of Ownerships, Traits and Lifetimes? Preferably with pseudo code or IRL analogies instead of Rust. If so please send it to me in a [tweet](https://twitter.com/gnfrazier).

* * *

**Footnote:**  
Please note that I am a huge Python fan, nearly an evangelist. I am active in my local Python community and it is my language of choice for just about everything. 
