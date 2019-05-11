---
layout: post
title: Overview of VSCode vs. Notepad++
tags: editors, coding, review
---

One of the closing questions for Micheal Kennedy's Talk Python to Me podcast is "What editor do you use?"
In the last year or so the answer has frequently been VSCode. In the recently released [2019 Stack Overflow Developer Survey](https://stackoverflow.blog/2019/04/09/the-2019-stack-overflow-developer-survey-results-are-in/) VSCode took over the top spot as the editor of choice. 

[![Top 10 editors from Stack Overflow 2019 Survey](<{{ site.baseurl }}/images/stack-over-flow-editors-2019.png>)](https://insights.stackoverflow.com/survey/2019?utm_source=so-owned&utm_medium=blog&utm_campaign=dev-survey-2019&utm_content=launch-blog#development-environments-and-tools)

The next free and opensource editor on the list (coming in at number 3) is the venerable Notepad ++, in this post we will compare the feature sets of the two programs.

| Spec                          | Notepad ++   | VSCode                |
| ----------------------------- | ------------ | --------------------- |
| Initial Release               | 11/24/2003   | 4/29/2015             |
| Supported OS                  | Windows Only | Windows, MacOS, Linux |
| Size                          | 3.63 MB      | ~70 MB                |
| License                       | GPL 2        | MIT                   |
| Syntax Highlighting Languages | 78           | 42                    |
| Syntax Folding                | Yes          | Yes                   |
| Customizable GUI              | Yes          | Yes                   |
| Word Completion               | Yes          | Yes                   |
| Function Completion           | Yes          | Yes                   |
| Tab Interface                 | Yes          | Yes                   |
| WYSIWYG preview               | Yes          | Yes                   |
| Zoom                          | Yes          | Yes                   |
| Automations                   | Macros       | Snippets and Macros   |
| Source Control Integration    | No           | Yes                   |
| Add-Ons                       | Plugins      | Extensions            |
| Remote Development            | No           | In Beta               |
| Collaborative Coding          | No           | Extension             |
| Embedded Chat                 | No           | Extension             |
| Embedded Voice                | No           | Extension             |
| Embedded Whiteboard           | No           | Extension             |
| Linter Support                | Community    | Extension             |
| Dark Theme                    | Plugin       | Default               |

So far as specs and supported features, the two applications are at feature parity. One clear win for Notepad ++ is its small install size of less than 4 MB, compared to about 70 MB for VSCode. This is for the core install, with extensions VSCode on my system is about 120 MB. A clear advantage for VSCode is that it is cross-platform for Windows, MacOS and Linux. This may or may not be a deal breaker for you, but having the same editor no matter where you are writing is a feature that I really like. 

Recently VSCode has been releasing functionality that supports modern workflows like pair programming and remote coding. While remote coding is has not been fully released as of this writing (May 2019) it is one of the features that I see removing a lot of friction for a lot of developers. It fits with the new Microsoft mindset of 'use what you want, we support you' where a dev can have a local instance of VSCode on their Macbook, but it is linked over SSH to files that are edited on a linux box, VM or container hosted elsewhere. 

Another feature in VSCode that make it ideal for distributed teams is an extension that supports an embedded whiteboard. I have struggled finding a good low-cost whiteboard application in the past. The VSCode version is as good as most of them, and the tight integration makes it easy to add the output to your docs. 

## References

**Notepad ++**  
[Notepad ++ Wikipedia](https://en.wikipedia.org/wiki/Notepad%2B%2B)  
[Notepad ++ plugins](http://docs.notepad-plus-plus.org/index.php/Plugin_Central)  
[Dracula Dark Theme Plugin](https://draculatheme.com/notepad-plus-plus/)  

**VSCode**  
[VSCode Wikipedia](https://en.wikipedia.org/wiki/Visual_Studio_Code)  
[VSCode Extensions](https://marketplace.visualstudio.com/VSCode)  
[Remote coding in VSCode](https://code.visualstudio.com/docs/remote/remote-overview)  
[Collaborative Coding in VSCode](https://medium.com/@ibrahimbutt/how-to-set-up-vscode-for-remote-pair-programming-e5f5c30a48e2)  
[VSCode Live Share (voice and chat support)](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare-pack)  
[VSCode Whiteboard Extension](https://marketplace.visualstudio.com/items?itemName=lostintangent.vsls-whiteboard)
