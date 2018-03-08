---
layout: post
title: Betraying Open Source - Altova Missionkit
tags: etl data altova mapforce open-source  
---

I am not the only one googling and posting on stack StackOverflow looking for an Open Source alternative to Altova Mapforce. Responses are few, vague and honestly not worth following up on. I felt somehow defeated that a proprietary tool rules this space so perfectly suited for Open Source. Then I started using it. It is so much just a tool that works, I can see why no one has bothered starting an OSS alternative. 

In 2016 I was very excited about Pentaho Kettle. It was the solution to my ETL woes. Except it was slow, didn't have good community support, tricky to install on windows and buggy. Buggy like stops with wonderful messages like 'An error has occurred.' Even at Free, I am not going to keep using that product. So I kept learning Python and moved on with my life, I will argue moved on for the better. 

Fast Forward 2018. At work, we still have a lot of data feed projects that are nothing more than remaps and ETL on data we already have. Generally, a BA would gather the requirements, write the ticket, and wait for the PM to slot the work. Weeks would go by. Then an analysis would be performed mapping explicit field names like ON1208 to the output fields like 'Description'. Then finally it would be handed off to a developer who would write the code, develop unit tests, go through QA, then finally turn over an example feed to go back to the vendor/business owner for approval. Total time to deliver a first iteration: about 5 weeks from the beginning of the analysis.

Yesterday I went from requirements to sample in 2 hours with Altova Mapforce while in the process of learning the tool. 

### Input

For input, I used an existing google shopping feed. There is a daily job that drops a text file on an FTP server. So a quick import from that FTP using the text file dialog, Mapforce does type detection on the fly. This file is all strings, but the fields can be typed to decimal, integer, dates, date time and so on. 

### Output

For the output file, create another text file that has the headers for your output. I was able to go to the vendor's website for file documentation, drop the fields into Excel, then do a transpose to get them on a single row. Copy - paste into a text file. Save as text tab, output file headers. Done. Yes, I could have saved the excel file as text tab, I don't trust excel to not do funky things when it saves text. I prefer notepad or an editor like VSCODE or Atom for things that need to be text. 

Now that the output headers are in place, define the output file. Use the header file as the 'input' a little confusing since this is the output, I wish it used the term 'source' or something else, but it does work. Then name your output file. Leave this blank if you wish to use a dynamic file name (like appending a date to a file name).

### Transform

This feed has a few specific requirements which is the reason we can't just send the original file.  
1. All HTML must be stripped  
2. Parent skus are not valid, only the child skus with a general_id to tie them together  
3. Any lines without an image, copy or brand must be excluded  
4. Currency needs to be formated to '19.99 USD'  

**Strip HTML**  
To strip the HTML I created a user-generated function in Mapforce. In python, this would be a method or in other languages a function. In the graphical interface think of it as a way to create a re-usable process that is much cleaner than having all the parts exposed. If you are using more than 2 or 3 operations tied together, consider creating a function to keep everything clean. 

Yes just a daisy chain of serial replace. There is obviously a map function in mapforce, but I didn't see a way to apply it to a parsed string. This is my first day in the tool, be kind. 

**Include Only Valid Rows**  
To remove the parent skus and to exclude rows that don't have an image or copy we can use a single user-generated function I'll label as validation. Add as many inputs as you need, then do your logic steps to perform the validation. If 4 data fields were critical, I would just add another input row. For the parent skus I can look for the field 'is_parent'= false, the rest the step of 'exist' will provide the boolean true false. Pipe everything to an AND since they are all required. Done.

Now connect the input fields to the validation. Connect the output of the validation to the rows line of the output. Done. 

**Currency**  
Tricky if you are not paying attention to types. The prices are in dollars with trailing zeros. The output feed requires 2 decimal places and a currency designator 'USD.' First convert the number as a string to a number, format it correctly, then concatenate as a string with a space and USD. Easier to follow in the function than in a paragraph. 

**More Clean Up**  
The internet says (and the internet is never wrong) that 80% of data is clean up, in this case, the title field has extra spaces. No need for a function this time. A quick trim and the field is good. 

### Checking the Output

At the bottom of the workspace, Mapforce has handy tabs that allow navigation to different stages of the workflow. Using the output view generates the mapping on a portion of the input file. 

### Generate the code

Generate the output code in the required format. Then either use it as part of a larger script or compile it to run on a machine of your choice. This step seemed too easy to me at first, but it really does work. 

### Wrapping Up

I can write Python to get done what I need, but Mapforce is simple enough I would have no problem setting up the inputs and outputs, then turning the mapping steps over to a business user. The documentation is daunting in volume and does not have a great way to dive in an out of it to move quickly. That being said, once I got the hang of the interface I was able to search for specific functions that looked close to what I needed. I still feel a little ashamed for being so excited about a proprietary tool, maybe I shouldn't be when it is the right tool for the job. 
