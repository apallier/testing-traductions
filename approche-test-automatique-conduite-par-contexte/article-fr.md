# Une approche du Test automatique conduite par le contexte

> A Context-Driven Approach to Automation in Testing

de James Bach et Michael Bolton

-------------------
### NDT : 
  Ce document est une "tentative" de traduction de l'article "[A Context-Driven Approach to Automation in Testing](http://www.satisfice.com/articles/cdt-automation.pdf)".
  C'est un travail actuellement toujours en cours.
  
  Traduit avec l'aimable autorisation de James Bach et Mickael Bolton.

-------------------

## Avant-propos

Les outils peuvent être utilisés de manières formidables pour aider au test des logiciels. Cependant, dans toute l'industrie, on voit  des outils mal utilisés. Ceci engendre un grand gaspillage, de la confusion et des difficultés à ce qui est déjà un problème difficile à résoudre. Pourquoi est-ce ainsi ? Que pouvons-nous faire ? Nous pensons que la base du problème vient d'une approche superficielle, restrictive et ritualiste de l'usage des outils. Ce fait est encouragé par la croyance généralisée mais rarement examinée et absolument fausse que le test est un processus mécanique et répétitif. Faire du "bon" test, tout comme programmer, est en réalité un défi intellectuel. L'usage d'outils en test doit absolument être réalisé par des personnes qui comprennent la complexité des outils et des tests. Ceci est vrai pour le test comme pour le développement, mais en réalité pour toutes activités demandant des compétences spécifiques, de la menuiserie à la médecine.

> There are many wonderful ways tools can be used to help software testing. Yet, all across
industry, tools are poorly applied, which adds terrible waste, confusion, and pain to what is
already a hard problem. Why is this so? What can be done? We think the basic problem is a
shallow, narrow, and ritualistic approach to tool use. This is encouraged by the pandemic,
rarely examined, and absolutely false belief that testing is a mechanical, repetitive process.
Good testing, like programming, is instead a challenging intellectual process. Tool use in
testing must therefore be mediated by people who understand the complexities of tools and
of tests. This is as true for testing as for development, or indeed as it is for any skilled
occupation from carpentry to medicine.

## Introduction

Dans ce "livre blanc", nous proposons une vision du test automatique qui place le testeur au centre du test, tout en promouvant une manière de penser qui fait la part belle aux nombreuses choses que les outils peuvent faire pour nous. Nous adoptons volontier les outils sans renoncer à notre responsabilité en tant que technicien de garder la main. 

Les outils peuvent être puissants, et nous allons dire des choses encourageantes et utiles sur leur compte. Mais l'automatisation peut aussi est traître - ne serait-ce qu'à cause du terme "automatisation" qui vouloir dire différentes choses. Donc nous devons commencer avec un regard humble sur les idées fausses qui engendrent un grand gaspillage, de la confusion et des difficultés à ce qui est déjà un problème difficile à résoudre même dans le meilleur des cas. Si vous avez besoin de bien tester, alors une bonne maitrise de l'outillage fera partie du travail, et cela signifie que vous devez apprendre pourquoi il est possiible de mal s'y prendre avec les outils.

> In this white paper, we offer a vision of test automation that puts the tester at the center of testing,
while promoting a way of thinking that celebrates the many things tools can do for us. We
embrace tools without abdicating our responsibility as technical people to run the show.

> Tools can be powerful, and we are going to say encouraging and helpful things about them. But
automation can also be treacherous — not least because the label “automation” refers to a mess of
different things. So, we must begin with a sober look at some basic misconceptions that add
terrible waste, confusion, and pain to what is already difficult even in the best of times. If you need
good testing, then good tool support will be part of the picture, and that means you must learn
why we go wrong with tools
