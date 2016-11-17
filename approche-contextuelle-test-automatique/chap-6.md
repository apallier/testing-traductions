> # Let’s see tool-supported testing in action!
> 
> We now present you with three examples of how tools help testing. The first example involves no checking. The second is checking done partly with tools and partly by the tester. The third is fully automated checking through the GUI (and gives you an idea of why we generally avoid doing that).
> 
> These examples are worked from the perspective of the independent tester, rather than the developer. We will demonstrate by describing some of our testing of FocusWriter, a word processor with a minimalist design, intended to create a distraction-free environment that helps authors write novels.
> 
> ## CASE #1: Tool use without checking.
> 
> > James wanted to test FocusWriter. He opened his browser, navigated to the gottcode.org Web site, downloaded FocusWriter, extracted it from its .zip file, and played with it.
> 
> Are there any tools in use here, so far? Most testers would say no. But seemingly, according to our definition, the computer is a tool of some kind. Various parts of the computer are tools, such as the mouse, the monitor, and keyboard; hardware. The web browser James used to download the product is a software tool. The website he accessed is a tool, too. The Internet itself is a tool. Yet, no one feels that these are “testing tools”, nor that this activity is anything like “test automation.”
> 
> Why? Because none of these things are tools with respect to anything unique about testing. Instead, they comprise the fabric of ordinary computing; ordinary use of the product. When we speak of tools in testing, we do not mean the natural processes of using the product, but rather contrivances applied for the purpose of accelerating or enabling testing over and above ordinary human interaction with the product.
> 
> *James opened SnapTimer and set a 15-minute rolling timer. He opened Evernote and started a new note titled “FocusWriter Test Session.” Then he Googled FocusWriter and thumbed through the top hits. In this way, he discovered that FocusWriter is an open source app.*
> 
> The tools here are SnapTimer, Evernote, and Google. These are not part of the FocusWriter user experience, and they are not employed in simulation of what a user would do in the ordinary business of using FocusWriter. Therefore, these are bona fide test tools in this case. They are applied specifically for testing purposes, even though they may not have been designed for testing per se.
> 
> More tool use quickly followed:
>     
>     1. James located the source code on Github. (Google)
>     2. He used Git to download that code. (Git)
>     3. He unzipped it. (7Zip)
>     4. He opened a Windows command prompt. (CMD)
>     5. From the top of the source directory he used grep to
>     search for the string “error.” (grep)
>     6. He noticed this line in the output: m_error =
>     tr("Unable to open archive."); On the conjecture that
>     "tr" means translate, and therefore may be the formal
>     mechanism for displaying localized message strings, he
>     used a regular expression search to extract every
>     associated string from the source. (grep with regex)
>     7. He extracted the strings themselves using this Perl
>     program: while(<>) { foreach (/tr\("(.*?)"\)/g) {
>     print "$_\n" } } (Perl with regex)
>     8. He used Notepad++ TextFX plugin to sort the result
>     and eliminate duplicates. (Notepad++ with TextFX)
>     9. He grouped all commands together, all keyboard
>     shortcuts together, all messages to the user together.
>     (Notepad++)
>     10. At some point during this process, the 15-minute timer
>     chimed, which alerted James to the need to update his
>     notes and check in on his test charter. (SnapTimer and
>     Evernote)
>     
> 
> We see plenty of tool use here, but most people would not call this “test automation.” So what? It is tool-supported testing. Testers should think about tools as helping them in any aspect of testing.
>  
> This case also shows the power of a tester who already knows how to use basic, free, technical tools and possesses a foundation of technical knowledge sufficient to read and write code. Not all testers need that—but we suggest all testers need access to someone who does have that skill, such as a toolsmith on the team.
> 
> The use of tools in this case led to interesting results:
>     * Discovery of functionality referred to inside the product (“&Daily Progress”) but not yet implemented.
>     * Discovery of error messages relating to previously unknown functionality.
>     * The basis for systematic testing of error handling.
>     
> ## CASE #2: Tool-support via patterned data generation for better coverage and a powerful oracle.
> 
> James frequently uses tools to generate special test data. One of his favorite tactics is called a “simplified data oracle.” For FocusWriter he used that to test the Scene List and Filter functions.
> 
> The Scene List is a feature that allows the author to navigate, select, and move scenes more easily. A scene is a block of text delimited by a specific text marker, such as “##.”
> 
> To test the Scene List we need a document that has scenes in it. That’s easy. We create some text and put some scene dividers into it, as in Figure 5. This text will display in the Scene List as in Figure 6. Let’s say this looks good. Let’s say it is exactly what we wanted to see.
> 
> Now we could automate this as a typical output check. But tools can do so much more for us. So, James decided to write a program that would create thousands of scenes, and identify them in a specific way that would help us track whether they were in the correct order in the Scene List. In other words, it is a combination of a stress test and a correctness check (to be performed by a human tester) that helps us see if there is a bug in how the Scene List displays and sequences the scenes. It helps us test the scene divider handling for a variety of different divider strings (because the scene divider string is configurable) as well as scene filtering functionality.
> 
> The program he wrote results in the file shown in Figure 7, which contains a total of 5,050 sub-sections. If the scene divider string is set to “scene” then the Scene List shows Figure 8.
> 
> Now, by filtering on “07.” it should pick out only seven scenes, wherever they are in the document, and display them in order in the Scene List panel. This is in fact what happens.
> 
> This is testing with a big boost from a tool. The tester can play. The tester can move scenes, filter, edit the document, or whatever. All the while, his test coverage will be deeper and his oracles sharper because of this patterned data. The tester is not limited to using the data, but can also edit the program that created the data to create even more interesting data. In fact, the version of the data you see, above, is the fifth refinement of the original concept.
> 
> ## CASE #3: Automated checking.
> 
> We wanted to demonstrate full-on automated checking, while at the same time staying with the FocusWriter example. FocusWriter does not provide an API for testing, which required us to automate through the GUI, and so the headaches began.
> 
> The high concept for the check was straightforward: perform a series of operations in FocusWriter that touch several features, change a document in a few ways, but result in the same output as we had at the beginning. A check that ends with the same state it began with is called idempotent. Idempotency is a useful heuristic because the process should be repeatable any number of times without regard for any progressive issues with system state—and if the state of the system interferes with the automation, that would be an interesting test result.
> 
> James proposed a process to be automated:
> 
>     1. Delete any old temporary test files.
>     2. Start FocusWriter.
>     3. Load the Three Musketeers text file.
>     4. Search and replace all instances of lower case “e” with “~” (chosen since it does not appear in the text).
>     5. Save the file as type ODT.
>     6. Close the file.
>     7. Close FocusWriter.
>     8. Open FocusWriter.
>     9. Open .ODT file.
>     10. Search and replace all instances of “~” with lower case “e.”
>     11. Save as TXT in new file.
>     12. Compare original with new text document.
>     13. Log result.
>     14. Exit FocusWriter.
> 
> This is designed to exercise saving (two kinds of files), loading (two kinds of files), starting, stopping, searching, and replacing. It comprises a bit of a stress test, because of the size of the Three Musketeers novel (1.3 million characters), but mainly it would be useful as a sanity check.
> 
> At James’ suggestion, Michael started to tackle the task using AutoHotKey, a Visual-Basic-like Windows scripting language. He soon ran into a problem: he was unable to query and confirm the state of the list box control by which the user chooses the file type. That obstacle and his unfamiliarity with AutoHotKey prompted him to switch to Ruby, with which he has a good deal more experience. Ruby has several libraries that provide support for the Windows API. He soon found the RAutomation library which is billed as “a small and easy to use library for helping out to automate windows and their controls for automated testing”. Like many such open-source offerings, it is sparsely documented, but with a few minutes of experimentation, Michael was confident that he would be able to make sense of it and put it to work.
> 
> RAutomation proved to be intuitive and straightforward to use, but Michael quickly discovered that certain aspects of FocusWriter made automating the process tricky. Among other things, FocusWriter appeared to implement list boxes such that RAutomation (as AutoHotKey before it) could not determine the currently selected option for the current file type; Michael had to track this by other means. Saving a file would sometimes cause a confirmation dialog to appear, sometimes not. Several dialogs shared the same caption (“Question”), even though the prompts and options within were different. Frequently the script would initialize actions before the application was ready for them, requiring wait states of one kind or another. All of this required loops of experimentation, discovery, learning, and revision that, in the end, took hours. Among other things, Michael wished that he had been part of the development process for FocusWriter to appeal for better testability.
> 
> After much fiddling Michael succeeded in getting the process running reliably, but when James used the same script on his own system, it was not able to find and start FocusWriter! After an hour of investigating together, we abandoned Ruby.
> 
> We considered our problems so far. Perhaps what we needed was a tool optimized for interacting with the product via the GUI. We’ve heard of HP Unified Functional Testing and its predecessors from testers forever. HP says “HP UFT software automates testing through an intuitive, visual user experience that ties manual, automated, and framework-based testing together in one IDE. This far-reaching solution significantly reduces the cost and complexity of the functional testing process while driving continuous quality.”8 To test this claim, we downloaded the trial version. After another full hour using the record and playback facility of HP UFT, we were able to get FocusWriter started, but could not get HP UFT to recognize the application window. It recognized Notepad, but there seemed to be something about FocusWriter (the fact that it is built with the QT toolkit?) that made it invisible to the HP tool. HP UFT would record a script, but then was not able to run its own script! We changed settings and edited the script in different ways, all to no avail.
> 
> Perhaps another five minutes or five hours would have gotten us past the problems with HP UFT. Neither of us are expert in the use of this particular GUI automation tool, and some experience with it might help us get around some of the obstacles. Perhaps our programming skills would accelerate our learning curve. Yet tools like this are often marketed in terms of “test automation without programming skills”. Here’s a typical example: “Test automation alleviates testers' frustrations and allows the test execution without user interaction while guaranteeing repeatability and accuracy.” Claims like these were being made 20 years ago. Meanwhile, the self-driving flying cars are still very much on the ground, with human drivers behind the wheel.
> 
> As a final effort, James used AutoHotkey to record a macro that performed the basic script. Success!
> 
> ## We found bugs…but not because we automated the check.
> 
> During this experiment in checking, we found that the final TXT file did not match the original one. That is all that checking can do: report some sort of inconsistency that must then be investigated.
> 
> Our subsequent investigation of the inconsistency led to two bugs:
>     1. FocusWriter writes ODT files in a manner that Microsoft Word complains is invalid (although it is apparently able to rescue the content).
>     2. FocusWriter reads ODT files incorrectly, causing one extra line and ten new spaces to be inserted wherever there is a line that begins with at least two leading spaces.
> 
> We reached our understanding of the first problem because we thought to use Microsoft Word and OpenOffice as “comparable product” oracles for the evaluation of the ODT file saved by FocusWriter. We reached our understanding of the second problem using a bevy of tools:
>     * WinMerge to analyze the text differences between the files
>     * Frhedit to analyze the hexadecimal differences between the files
>     * Perl to create and modify test files with various properties in order to test our hypotheses
>     * 7Zip and Notepad++ to examine the XML content of ODT files
>     * Excel to build a spreadsheet that predicted size changes
>     * Wikipedia/Google to study UTF-8 encoding
> 
> Note that automating the check had little to do with finding and investigating these bugs. It didn’t save us any time. In this case, so far, the automated check is a cost without benefit. The check itself in its un-automated form—specified by a thinking tester, and carried out interactively during the process of automating it—simply gave us an indication of a problem. Then, skilled testers carried through with the investigation (with the help of tools) that systematically pared down potential factors to home in on the few that mattered.
> 
> The foray into automated checking took far more time than the first two cases. We learned things in the process of developing this automated check that might have made further checking easier to some degree, especially if our experience could inform better testability. Yet we wonder: if we were to create a library of checks, would the value of such checks match the development cost? The maintenance cost? The opportunity cost?
> 
> It may be that, sometime in the future, another bug will creep in to the product that this particular check will notice. If there are changes to this area of the product in the future, they will probably cause our check to fail irrespective of whether the failure is due to a bug in the product or in the script. If there are no changes in this area, the check will not fail, but probably also will not be worth running. It is often difficult, ahead of time, to choose which checks will be worth having automated, and which will turn out to have been white elephants. A lot of this is a matter of guessing about risk and change. This involves skill, experimentation and learning.
> 
> ## Why is automating interactions through a GUI so difficult?
> 
> After hearing this story, some “test automators” might claim that they don’t have these kinds of problems, and if they did, they would be able to get around the problems easily. In saying so, they would be completely missing several points.
> 
> GUIs are designed for able-bodied humans, who don’t have the same trouble finding and interacting with products as robots do. In fact, our tools fell victim to the same kinds of barriers presented to people who suffer from disabilities and yet try to use modern technology. Accessibility is a widespread problem in computing9 for people and tools alike. Just as success with one accessible product does not disprove the existence of the accessibility problem in general, pointing to one trouble-free use of a tool to control an app doesn’t disprove our general claim, which is this:
> 
> GUI-level scripting is fiddly. It’s fussy. It fails suddenly in unexpected ways. It’s notoriously problematic. It requires learning not only about the application and the tool, but also about how they will interact. We both learned this in the 80’s and 90’s10, we’ve seen it ever since, and we are seeing it now.
> 
> Beyond the accessibility issue, think about it. Even something as simple as saving a file, which is easily navigated by a human, becomes an exercise in pure pedantics when you attempt to program a machine to do the same thing. When you save a file, the application may or may not present dialogs that are distinguishable using a particular approach; it may or may not use libraries or controls that are recognized by the test framework you’re using. On any given run, the application may or may not be pointed to the right directory; it may or may not ask you if you really want to overwrite another file; it may or may not refuse to proceed because that other file is locked by another process or because disk space ran out on your USB stick. The application may or may not be interrupted by some other application during this process. It may or may not take an unusually long time to save.
> 
> Humans take all these eventualities in stride—we barely notice them unless they seem wrong! Not so for programs. Any possibility that has not been anticipated and not expressly programmed is a potential stumble for the script, which means another round of troubleshooting, debugging, and testing for the person trying to program it. Even if you think you could do better with FocusWriter using your favorite tool, we claim that the kinds of problems we have highlighted are not unusual in tooling generally, and that they are normal to GUI-level user simulation tooling, regardless of your skill level, industry, or product type.
> 
> Although Michael succeeded with Ruby and James succeeded with AutoHotKey, without more work, success took the form of rough prototype scripts. These are very brittle. The smallest change in the application, or in the saved state of the application, or in the data set may disrupt the script in a way that requires tuning or a complete rewrite.
> 
> ## You can make GUI checking more resilient in the face of product change, at a price…
> 
> As one of our reviewers, Ben Simo, noted, we can certainly make GUI checks less brittle in the face of change, but the very factors that make them less brittle usually make them less powerful, too, because we achieve greater resiliency by sacrificing certain sensitivities. For instance, we may filter out time stamps or user names, or we block out sections of screenshots. It may be okay to ignore the current user name when we are running the tests with accounts called “TestRobot6” or “TestRobot22” and want to use the same logic to check screens in both cases, but what if there is a legitimate bug whereby the user’s name is wrongly displayed? Our modified check won’t spot it. Adding such special case logic into the check code also increases the complexity of that code, which creates brittleness of a different kind: an increased likelihood that we will break the code when we try to improve it.
> 
> We may be completely successful in suppressing certain disruptions to GUI automation, but those same disruptions may give us information about the product that, as human users, we would easily understand as significant. For instance, we can implement a time delay in checking output from a process in order to assure that the process is complete before we attempt to process the output, but that means we won’t notice if it gets progressively slower and faster in its response times within that time delay. Testers don’t just numbly watch the world go by. Real testers are not just idle product tourists—we critically analyze what we see. But if we outsource our “seeing” to the computer, we cannot be critical of what it sees, and the computer doesn’t know how to be critical.
> 
> As you navigate these troubles, you will probably be caught up in a more insidious pattern: GUI-level checking distracts testers from performing deep tests that examine complicated or subtle functional behaviors. This is because you have to keep the checking simple. If you pour complex, interesting data and interactions into your checks, you will create huge headaches for yourself in coding and maintaining it. Imagine reproducing, in code form, just five minutes of your typical use of your computer. Yikes. This is why GUI check designers focus on superficial interactions and easily parsed outputs. It’s economically viable. It will allow you to add more “test cases” to your “test suite”, but what it accomplishes is likely to be shallow testing. At the same time, all this effort presents opportunity cost that robs you of time for deeper testing.
> 
> There are contexts in which automated checking is likely to be cheaper and more powerful. Products that are built with testability in mind—scriptable interfaces and log files that can be easily parsed—tend to be more amenable to automated checking. Products that have simpler forms of input and output are easier to check programmatically. Automated checks closer to the developer’s current task can afford quick change detection, fast feedback, and simpler repair. Well-built, “unbuggy” products can be much easier to automate and to check.
> 
> These points we are making are not new. The first Los Altos Workshop on Software Testing, which was the first organized gathering of the not-yet-named Context-Driven School of software testing dealt with the problems of automating the interaction of an application through a GUI—and that was way back in late 90’s11.
> 
> 
> [8] http://bit.ly/1j9VUCL, retrieved October 30, 2015.
> 
> [9] http://arc.applause.com/2015/11/02/mobile-accessibility-end-user
> 
> [10] See James Bach, “Test Automation Snake Oil”, http://www.satisfice.com/articles/test_automation_snake_oil.pdf
> 
> [11] Kaner, Cem, Improving the Maintainability of Automated Test Suites, p. 10, http://www.kaner.com/pdfs/autosqa.pdf
