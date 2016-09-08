# Troisièmement : explorez les nombreuses façons d'utiliser les outils

> # Third: Explore the many ways to use tools!

Les compétences et l'état d'esprit d'un testeur sont centrales dans l'utilisation responsable d'outils. Cependant, lorsque nous disons ça, certaines personnes semblent penser que nous disons que les outils ne sont pas importants, ou que les testeurs "conduits par le contexte" haïssent les outils. Rien ne peut être plus éloigné de la vérité.
> 
> The skill set and the mindset of the individual tester are central to the responsible use of tools. When we say this, however, some people seem to hear us saying that tools are not important, or that context-driven testers hate tools. Nothing could be farther from the truth.

Etablissons le catalogue des différentes manières dont les outils peuvent nous aider dans le test :

* En conception, on utilise des outils pour nous aider à:
   
    * produire des données de test (outils comme les tableurs, générateurs d'états par modèle, simulations de "Monte Carlo", générateurs de nombres aléatoires)
    * obfusquer ou nettoyer les données de production pour des raisons de confidentialité (brouilleurs de données, remplacements de nom)
    * générer des combinaisons intéressantes de paramètres (générateurs de données combinatoires ou "all-pairs")
    * générer des flux à travers le produit qui couvrent des conditions spécifiques (générateurs de chemins  par modèle d'état ou par modèle de flux)
> 
> Let’s catalog some of the many ways tools help us in testing:
> 
> * In design; we use tools to help us
>     – produce test data (tools like spreadsheets; state-model generators; Monte Carlo simulations; random number generators)
>     – obfuscate or cleanse production data for privacy reasons (data shufflers; name replacers)
>     – generate interesting combinations of parameters (all-pairs or combinatorial data generators)
>     – generate flows through the product that cover specific conditions (state-model or flow-model path generators)
> 
--------------------

> * In product interaction, we use tools to help us
>     – set up and configure the product or test environments (like continuous deployment tools; virtualization tools; or system cloning tools)
>     – submitting and timing transactions; perhaps for a long time; at high volume; under stress (profiling and benchmarking tools)
>     – encode procedures like operating the product and comparing its outputs to calculated results (this is automated checking).
>     – simulate software or hardware that has not been developed yet; or that we do not have immediately available to us (mocking or stubbing tools)
>     – probe the internal state of the system and analyze traffic within it as testing is being performed (instrumentation; log analysis; file or process monitors; debugging tools)
> 
> * In evaluation, we use tools to help us
>     – sort, filter, and parse output logs (text editors; spreadsheets; regular expressions)
>     – visualize output for comparative analysis (diffing, charting and graphing tools, conditional output formatting)
>     – develop, adapt and apply oracles that help us recognize potential problems (source file or output comparison tools; parallel or comparable algorithms; internal consistency checks within the application; statistical analysis tools)
> 
> * In recording and reporting, we use tools to help us
>     – record our activities and document our procedures (note-taking tools; video-recording tools; built-in logging; word processing tools; user interaction recording tools)
>     – prepare reports for our clients (mind maps; word processors; spreadsheets; presentation software)
> 
> * In managing the testing work, we use tools to help us
>     – map out our strategies (mind maps, outline processors, word processors)
>     – identify what has and has not been covered by testing (coverage tools; profilers; log file analysis)
>     – preserve information about our products, and to aid other people in future support and development (wikis; knowledge bases; file servers)
> 
> And this is an incomplete list of the ways in which we use tools to help us. Moreover, we use tools to help us produce the tools that we use.
> 
> You have probably noticed how we repeatedly said “We use tools to help us...” We have chosen these words deliberately to emphasize once again that tools don’t do testing work; tools help testers to do testing work. In conversation about testing, tools may be important, but the center of testing must be the skill set and the mindset of the individual tester.
> 
> ## Let your context drive your tooling.
> 
> By “context”, we mean the set of factors that should affect the decisions of a responsible tester. Generally speaking, a craftsman who has both the skills and intent to select and apply the appropriate tools and methods for any given context can be called context-driven. More specifically the Context-Driven school of software testing is a paradigm of testing based on the following principles:
> 
> 1. The value of any practice depends on its context.
> 2. There are good practices in context, but there are no best practices.
> 3. People, working together, are the most important part of any project’s context.
> 4. Projects unfold over time in ways that are often not predictable.
> 5. The product is a solution. If the problem isn’t solved, the product doesn’t work.
> 6. Good software testing is a challenging intellectual process.
> 7. Only through judgment and skill, exercised cooperatively throughout the entire project, are we able to do the right things at the right times to effectively test our products.
>     
> These principles were written by Cem Kaner, James Bach, and Bret Pettichord, and first published in their book Lessons Learned in Software Testing: A Context-Driven Approach, which is the seminal book on Context-Driven thinking.
> 
> Note that if you are working in a way that solves the problems that exist in your environment, you may be doing context-specific work without necessarily being context-driven. To be context-driven you must be ready and able to change the way you work if and when the context changes. That’s why the Context-Driven community focuses on developing skills and sharing experiences across many kinds of projects and technologies. This is why we foster peer conferences dedicated to conversation and debate, rather than to flashy exhibitions.
> 
> ## How specifically does context drive tooling?
> 
> Context drives tooling through the activity of ongoing problem-solving. We do that by developing in our minds various understandings, including:
> 
> * what surrounds us and our place in that world
> * our clients and our mission
> * other people involved and what they are trying to do
> * tools and techniques available to us
> * actions we could take and the effects they may have
> * the immediate costs (and time) of those actions
> * the long term costs of those actions
> * the value of learning from trying new things
> 
> These understandings may be thought of as spaces that we explore throughout our projects and careers. As we learn and grow, during the course of our projects and careers, we get better at navigating them.
> 
> What we do with those understandings ultimately results in mental calculations and decisions along the lines of Figure 3. In context-driven work, our choices are guided not according to a fixed script of “best practices” but rather by dynamically evaluating context and selecting, designing, or adjusting our actions to solve the problems that we encounter. We don’t simply look at whether a particular strategy is worth doing in and of itself, such as strategy B in the diagram, where you can see that its value outweighs the risks and the costs. We also compare that to other strategies that might be even better, such as strategy A. Yes, these decisions may be biased, as in Figure 4, perhaps because we unconsciously veer toward things we know and away from potentially wonderful new ideas that we aren’t yet comfortable with. But still, we strive to make decisions based on merits rather than following the dictates of fashion or arguments from authority. In context-driven testing, we don’t idolize “best practices.”
> 
> The answer to the question of how context drives tooling is: we read the situation around us; we discover the factors that matter; we generate options; we weigh our options, and we build a defensible case for choosing a particular option over all others. Then we put that option into practice and take responsibility for what happens next. All along we are learning and getting better at this.
> 
> Building a test strategy and determining how to use tools to fulfill that strategy is an evolutionary process. No one who says “do it right the first time” has ever really done anything difficult right the first time. We become able to do things well partly via the experience of doing them badly. We often learn how to develop powerful, polished tools by developing cheap, disposable tools—and then throwing them away and applying what we’ve learned. Developing software also means developing our approaches to testing it.
> 
> Context-driven behavior tends to be highly exploratory because the practitioner is responsible, at every turn, for the quality of the work—and not just the immediate work, but also the overall strategy. If you are not just following instructions handed down from a boss or bureaucrat, then you have to evaluate the situation and frequently adjust your practices to get the best result you can. This also means that Context-Driven practitioners think not only about efficiencies, but about contingencies as well.
> 
> Approaching test tooling in a context-driven way means we don’t play down the problems that tools have. We try to face them forthrightly. This can make us look rather pessimistic about certain ways of using tools, though, so it is a special challenge to remind ourselves of the benefits of tooling and to move toward the kind of tools that provide more of those benefits.
> 
> # Invest in tools that give you more freedom in more situations.
> 
> So, how does a Context-Driven tester approach tools and their use? Well, there are no “best tools” in the Context-Driven world. Indeed, there are no dedicated “test tools” in the Context-Driven world. Any tool can be a test tool. Any tool might be useful. But we can suggest, all other things being equal, factors that make some tools more generally preferable. In good Context-Driven fashion, we acknowledge at least one exception for each heuristic:
> 
> 1. Tools that support many purposes are preferable to those optimized for one purpose. Some tools are designed with specific process assumptions in mind. If you work in a context where those assumptions apply, you are fine. But what if you decide to change the process? Will your tools let you change? In changing contexts, tools that are simple, modular, or adaptable tend to be better investments. Tools that operate through widely used interfaces and support widely used file formats are more easily adapted to new uses. Note that a tool may have only one major function, such as searching for patterns in text, and yet be a good fit for many purposes and many processes. Exception: If a tool happens to fulfill its one purpose far better than alternative tools, it might be worth the trouble of making room for it in your toolbox.
>     
> 2. Tools that are inexpensive (or free) are preferable to expensive tools even in many cases where the expensive tools are more powerful. This is partly because of “sunk cost bias.” The more money management pays to acquire a tool, the less acceptable it is to stop using the tool even if the tool is obviously unsuited for the purpose at hand. Furthermore, free tools invite us to experiment with different techniques. Experimenting is absolutely necessary in order to develop the skills and knowledge we need to make informed decisions about our processes. Exceptions: Remember there is more to cost than the purchase price. An apparently inexpensive tool may cost more in the long run if it requires extraordinary maintenance. Also, an expensive tool might be the only tool that has the special capabilities that you seek.
>     
> 3. Tools that require more human engagement and control are preferable to those that require less. This is due to a syndrome called “automation complacency,” which is the tendency of human operators to lose their skills over time when using a tool that renders skill unnecessary under normal circumstances. In order to retain our wits, we humans must exercise them. Tools should be designed with that in mind, or else when the tool fails, the human operator will not be prepared to react6. Exception: We may genuinely value the power and convenience that the tool gives us more than we value the skills and awareness that we lose in the process.
>     
> 4. Tools that are supported by a large and active community are preferable to those that are not. The more people who use a tool, the more free support will be available and the more libraries, plug-ins, or other extensions of that tool. This increases the value of the investment in learning that tool, while reducing the learning curve. (The R language is a good example. It’s a powerful and general purpose data analysis tool. Lots of researchers use R, lots of books about it are on Amazon.com, and there are hundreds of libraries that provide special capabilities beyond the defaults capabilities of the tool.) Exception: Just as in the case of expensive tools, sometimes the value you get from a tool is so important that it overrides concerns about support.
>     
> 5. Tools that can be useful to non-specialists are preferable to those that are not. We’re talking about tools that lower the cost of getting started; that afford ease of use; that don’t depend on proprietary languages; that have lower transfer and training cost. Microsoft Excel and spreadsheets in general provide a good example. It is possible to use Excel in a very specialized and sophisticated way, but there is a lot Excel can do for you, even if you have only basic skills with it. Exception: Sometimes it can be good for a tool to dissuade non-specialists from using it, because non-specialists may not be capable of using the tool wisely.
>     
> 6. Tools over which we have control are preferable to those controlled by others. Good tools are at the very least configurable to your specific needs. An open source tool allows you to control every aspect of it, if you need to do that. Apart from the expense, commercial proprietary tools prevent you from adding new features and fixing critical bugs. Proprietary tools may be modified in ways that disrupt your work at inconvenient times, and you have no control over that schedule. Exception: Sometimes not having control over a tool is a good thing, because you are forced to use standard versions and configurations which allow you to share work more easily with others who use that tool.
>     
> 7. Tools that are portable across many platforms are preferable to those restricted to a single platform. One aspect of context is the operating system or hardware platform. Cross-platform tools obviously work in a wider context. Exception: A tool may provide value that is important enough to offset its lack of cross-platform compatibility; or it may offer interoperability with similar tools on those other platforms.
>     
> 8. Tools that are widely (or easily) deployed are preferable to tools that aren’t. A primary problem of tool use is getting the tool in the first place. Some tools require complicated installation and configuration. Some tools may require special permission or expenditure. This can require negotiating with the IT department, managers, or co-workers. Exception: Some tools may be worth this trouble.
>     
> 
> ## Invest in testability7.
> 
> The success of any tooling strategy depends in large part on how well your technology affords interactions with tools. This is why it pays to build testability into your products. From a tool perspective this means two big things: that your product is controllable by tools via easily scripted interfaces, and that its states and outputs are observable by those tools. For this reason, browser based products tend to be more testable while apps on mobile devices are less testable. Products with standard controls are more testable than products with custom controls.
> 
> Consider making testability review a part of each iteration, and otherwise instill this thought process early in your projects. Any serious attempt to make tooling work must go hand-in-hand with testable engineering.
> 
> 
> 
> [6] See Nicholas Carr, The Glass Cage, and Lisanne Bainbridge, "Ironies of Automation", Automatica, Vol. 19, No. 6. pp. 775 779, 1983.
> 
> [7] See http://www.satisfice.com/tools/testability.pdf
