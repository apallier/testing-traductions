# Deuxièmement : Penser plus au test qu'à la vérification des résultats

> # Second: Think of testing as much more than output checking.

Pour nous, tester consiste à évaluer un produit en apprenant sur lui au travers d'exploration et d'expérimentation, ce qui comprend dans une certaine mesure : le questionnnement, l'étude, la modélisation, l'observation et la déduction, etc<sup>4</sup>.

> We say that testing is evaluating a product by learning about it through exploration and experimentation, which includes to some degree: questioning, study, modeling, observation and inference, etc.<sup>4</sup>

Nous avons pesés précautionneusement nos mots. Le test est nécessairement un processus humain. Seuls des hommes peuvent apprendre. Seuls des hommes peuvent déterminer une valeur. La valeur est un jugement social, et des personnes différentes évaluent les choses différemment. Il se peut que les techniciens croient qu'ils peuvent automatiser l'évaluation des exigences en les codant dans un script, mais l'évaluation est provisoire et incomplète jusqu'à ce qu'elle ai été revue par un humain. Il y aura presque toujours des circonstances où un manager dira "l'outil a rapporté un bug mais ce n'est pas réellement un problème dans ce cas." 

> We choose our words carefully. Testing is necessarily a human process. Only humans can learn. Only humans can determine value. Value is a social judgment, and different people value things differently. Technologists may believe that they can automate the evaluation of requirements by encoding them into a script, but the evaluation is provisional and incomplete until it has been reviewed by a human. There are nearly always circumstances in which a manager will say “the tool is reporting a bug, but it is really not a problem in this case.”

L'exploration est un élément central dans notre définition du test car nous ne pouvons pas savoir où sont les bugs avant de les avoir trouvé. Effectivement, pour tout nouveau produit, nous devons découvrir d'abord où chercher les problèmes, et il y a trop d'endroits pour nous à chercher pour tous les vérifier. Nous ne savons même pas ce qui peut être compter comme un bug avec certitude; il s'agit d'un jugement qui dérive et change pendant la vie d'un projet. Nous mettons l'accent sur l'expérimentation parce que les bons tests sont littéralement des expériences au sens scientifique du terme. Au moins 300 ans avant qu'on se pose la question de ce qu'un logiciel pourrait ou devrait faire, les "philosophes de la nature" testaient déjà la nature de façon systématique avec leurs expériences<sup>5</sup>. Ce que les scientifiques veulent dire par expérience est précisement ce que nous voulont dire par test. Le Test est nécessairement un processus de recherche incrémental, speculatif et orienté sur lui-même.

> Exploration is central to our definition of testing because we don’t know where the bugs are before we find them. Indeed, with any new product we must discover where to look for problems, and there are too many places to look for us to check them all. We don’t even know for sure what counts as a bug; that is a judgment that drifts and shifts over the course of a project. We emphasize experimentation because good tests are literally experiments in the scientific sense of the word. At least 300 years before anyone ever wondered what software could or would do, “natural philosophers” were systematically testing nature via their experiments.<sup>5</sup> What scientists mean by experiment is precisely what we mean by test. Testing is necessarily a process of incremental, speculative, self-directed search.

Finallement, le "etc." de la fin est le signe que le Test implique plein d'autres activités et de disciplines de type analytiques. Des activités qui ne sont pas du Test en elles-même, comme l'étude d'une spécification, deviennent du Test lorsqu'elles sont faites dans le but de tester. 

> Finally, the “etc.” at the end is a signal that testing incorporates many other analysis-related activities and disciplines. Activities that aren’t themselves testing, such as studying a specification, become testing when done for the purposes of testing.

----------------------

> Let’s break down testing further. What do we specifically do when we test? Testing is a performance that involves several kinds of ongoing, parallel activities:
- we design our testing by learning and modelling the product, determining test conditions to cover, generating specific test data, identifying and developing oracles (i.e. the means to recognize problems when we encounter them), and establishing procedures to explore and experiment.
- we interact with the product by configuring, operating and observing it.
- we evaluate the product by using appropriate oracles to detect inconsistencies between the product and qualities that we might consider ideal.
- we record and report the testing work that has been done.
- we manage the testing work, which includes understanding the current status of testing, analyzing product risk, scoping and assigning testing tasks.

> All of these activities can be helped with tools.

> [4] See http://www.satisfice.com/blog/archives/856
> [5] “…what these several degrees are I have not yet experimentally verified; but it is a notion, which if fully prosecuted as it ought to be, will mightily assist the astronomer to reduce all the Celestial motions to a certain rule, which I doubt will never be done true without it…” Robert Hooke, 1674, An Attempt to Prove the Motion of the Earth by Observations, (http://bit.ly/1MDwhBI)

> ## Distinguish between checking and testing.

> We find it necessary to distinguish between checking and testing. Checking is the process of making evaluations by applying algorithmic decision rules to specific observations of a product. This is different from the rest of testing in one vital way: it can be completely automated. Checking is an appropriate place to use that word “automation.”

> In testing, we design and perform experiments that help us develop our understanding of the status of the product. This understanding is an interpretation; an assessment. But it is not a fact. Simple facts are arguably “verifiable,” but quality is never a simple fact. Quality is a working hypothesis. When you exercise software and fail to spot a specific problem, you have not proven or demonstrated that “it works.” All you know is that you haven’t yet recognized a failure. All you have demonstrated is that the product can work. The product may have failed in a subtle way you did not or cannot yet detect., Maybe it works fine now, but won’t work ten minutes from now. So does it really, truly, deeply work? No output check can tell you that. No collection of output checks can tell you that.

> Indeed, any advertiser, late-night TV pitchman, or stage magician can show you that something appears to work. Our job as testers is not to obey the ad, swallow the pitch, or believe the trick. Our job is to figure out what the ad leaves out, where the product doesn’t meet the claims, or how the magician might be fooling us. Although routine output checking is part of our work, we continually re-focus on non-routine, novel observations. Our attitude must be one of seeking to find trouble, not verifying the absence of trouble—otherwise we will test in shallow ways and blind ourselves to the true nature of the product.

> Evaluating quality is a task that requires skillful, complex, non-algorithmic investigation and judgment. That task can be supported and accelerated by tools, but it cannot be performed by the tools themselves.

> ## Checking is important.

> Good checking is a subset of testing. Checking is not the same as testing in the way that biting is not the same as eating; tires are not the same as cars; and spell checking is not the same as editing. Good checking is always a product of— and embedded in— the processes of designing, implementing, and interpreting those checks, which are human activities; which constitute testing. Testing gives checking its value and meaning. Whereas, checking keeps testing grounded.

> Automated checking is a tactic of testing, and can have considerable value. Programmers who adopt automated checks into their coding practices can provide themselves with fast, inexpensive feedback. Checking through an API beneath the GUI level can be particularly useful. In designing such low-level checks, programmers and testers can profitably work together.

> We are more doubtful of automated checking at the GUI level. GUIs are notoriously fussy. Because non-technical people can see them and discuss them, GUIs may change much more capriciously than the underlying interfaces that only programmers see. This can lead to a large, expensive maintenance effort just to keep the simple checks running. Moreover, GUIs are designed to feel natural and comfortable for people, not for other software. You may need a skilled full-time programmer to maintain all the code necessary to attempt to simulate a speedy but unskilled human tester. That is probably not a money-saving proposition.
