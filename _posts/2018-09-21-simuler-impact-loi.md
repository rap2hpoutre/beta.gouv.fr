---
title: Simuler l'impact de la loi, c'est possible !
authors:
  - sandra.chakroun
  - anna-livia.gomart
  - hela.ghariani
---

Vos revenus actuels décideront-ils de vos aides sociales dans deux ans ?

## Contexte

Le Groupe de Travail (GT) [Accès aux droits et aux services, lutte contre le non-recours](https://fncp-france.fr/wp-content/uploads/2018/03/rapp-4.pdf) de la [Délégation interministérielle à la prévention et à la lutte contre la pauvreté des enfants et des jeunes](https://twitter.com/delegpauvrete) s’applique à proposer des solutions pour permettre à toutes et à tous, et surtout aux plus vulnérables, de connaître les moyens mis à leur disposition pour les accompagner.

Dans le cadre de ce GT, nous avons proposé d’utiliser [OpenFisca](https://fr.openfisca.org) en atelier pour étudier comment le prélèvement à la source de l’impôt pourrait impacter les foyers recevant des aides telles que le [RSA](https://fr.openfisca.org/legislation/rsa), la [PPA](https://fr.openfisca.org/legislation/ppa) et les aides au logement.

<!--more-->

Ces ateliers ont réuni des experts du calcul des prestations sociales et les équipes d'[Openfisca ](https://fr.openfisca.org) et de [Mes Aides](https://mes-aides.gouv.fr).

[Mes Aides](https://mes-aides.gouv.fr) se base sur [OpenFisca-France](https://fr.openfisca.org), un modèle informatique du système socio-fiscal, capable de simuler, non seulement la législation actuelle, mais aussi l‘impact de réformes sur des individus ou des foyers.

Au cours de ces ateliers, notre hypothèse de départ était qu’on ne pouvait pas simplifier l'accès au droit à cause de la complexité des règles de calcul des prestations sociales.

On part d'une question qui peut paraître simple : comment évalue-t-on combien gagne une famille lorsque l’on calcule son éligibilité à une prestation sociale ?

Aujourd’hui, ces règles prévoient une dizaine de méthodes de calcul des revenus d’un foyer. Certaines prennent en compte les revenus des 3 derniers mois, d’autres se basent sur le revenu fiscal de référence, calculé sur les revenus N-2 (année - 2). Avec le passage au prélèvement à la source de l'impôt sur le revenu, le calcul des prestations sociales pourrait utiliser une donnée plus proche de la situation actuelle des personnes.

Notre hypothèse était qu’en collant plus aux situations des personnesn les aides s’appliqueraient au plus près de leur besoin et cela simplifierait la compréhension de la façon dont elles sont calculées.

Nous voulions savoir :
* dans quelle mesure nous pouvions utiliser [OpenFisca](https://fr.openfisca.org) pour accompagner la conception d’une réforme.
* quelle était l'expérience des utilisateurs d'[OpenFisca](https://fr.openfisca.org) qui voulaient simuler l'impact d'une reforme.

Notre intention était de simuler concrètement une simplification des bases de calcul des prestations sociales, et de définir son l'impact sur différents types de ménages. Et nous nous sommes lancé dans l'exercice sans vision claire ni du résultat attendu ni du chemin pour y arriver.

## La rencontre des experts de la loi et des experts du code

L'objectif initial était de définir quels types de réformes tester et sur quelles typologies de foyers, simuler et évaluer leurs impacts. Nous avons commencé par définir 7 scenarios de réformes avec les experts métiers.

Nous avons lancé cette initiative sans filet. En nous laissant la possibilité d’adapter notre travail à ce que nous allions découvrir au fur et à mesure, nous avons appris comment faire dialoguer ces deux domaines, la maïeutique pour partir d'une idée et aller à une réforme.

En bref : temps réduit, environnements techniques très variables, compétences diversifiées. Nous nous sommes vite rendu compte que pour accompagner au mieux les travaux du GT, nous devions en priorité créer des outils de communication et de visualisation. Pour nous permettre de faire cela, nous avons réduit au fur et à mesure le périmètre des réformes pour retenir 2 scenarios.

### Simplifier, c'est d'abord comprendre la complexité du droit.

Avant de le coder ou de définir les contours d'une réforme, le premier apprentissage est de comprendre l'esprit de la loi.

Les raisons de chaque subtilité (par exemple, l’effet figé qui consiste à verser un montant identique entre les deux dates d’évaluation d’une aide) doivent être maîtrisées pour savoir quelle typologie de situation sera affectée par un changement.

Il est facile de se perdre dans la nébuleuse du droit social, même accompagné par des experts.

On se rend compte en discutant avec le GT que déterminer combien une personne (ou une famille) gagne aujourd’hui est loin d'être évident :
* Que se passe-t-il si la personne a des revenus qui fluctuent tous les mois ?
* Que se passe-t-il si elle n'est pas salariée ?
* Que se passe-t-il si la personne vient de partir à la retraite ?

### Simplifier les formules ou masquer la complexité ?

Devant la complexité législative inhérente à la diversité des situations familiales, nous nous sommes demandés si l’enjeu au final de facilitation d'accès au droit ne serait pas de masquer la complexité à l'usager en travaillant l'expérience utilisateur.

C’est le pari du service Mes Aides, une interface qui structure et simplifie la demande d’information à l’utilisateur, puis qui utilise [OpenFisca](https://fr.openfisca.org) pour calculer les droits sociaux auxquelles il peut prétendre.
Une partie de la solution peut se trouver dans l’ordonnancement des informations et la pédagogie.

Les micro-simulateurs comme [OpenFisca](https://fr.openfisca.org) ont un rôle à jouer, car ils permettent de "Mieux comprendre comment fonctionne le droit adapté à ma situation."

## Comment les réformes affectent les foyers : un exercice de communication politique

En parallèle des scénarios de réforme, nous avons créé un jeu de situations familiales (célibataire avec enfant/sans enfants, sénior touchant une retraite…) qui représentent les situations du [livret du pouvoir d'achat du Ministère du Budget](https://www.economie.gouv.fr/files/files/PLF2018/bro-pouvoir-achat-bat-web-10h.pdf). Cela permet de tester les réformes sur des cas concrets et voir comment des changements dans la loi affectent les foyers.

Nous nous sommes finalement concentrés sur une réforme qui considère les revenus des 12 derniers mois comme base de ressources.

![Comparaison de différentes bases ressources par cas types](/img/posts/2018-06-01_openfisca_comparaison_bases_ressources.png)

![3 modes de calcul des aides au logement selon la période des revenus d’activité ](/img/posts/2018-06-01_openfisca_3_modes.png)

![Temporalité de l’augmentation de l’aide au logement en cas de baisse de ressources (12 mois)](/img/posts/2018-06-01_openfisca_temporalite_al.png)

![Prise en compte des données fiscales, hors revenus d’activité](/img/posts/2018-06-01_openfisca_donnees_fiscales.png)

> `AL_MM01` correspond au calcul des aides au logement basé sur les revenus d’activité du mois M-1.
`AL_MM03` correspond au calcul des aides au logement basé sur les revenus d’activité du dernier trimestre.
`AL_MM12` correspond au calcul des aides au logement basé sur les revenus d’activité des 12 derniers mois.
`Base` est le mode de calcul actuel des aides au logement sur les revenus N-2 récupérés auprès des impôts.


Pour communiquer nos résultats, nous avons voulu générer des graphiques sur la rapidité de prise en compte d’un changement de situation (chômage, augmentation, retraite…) en fonction de la base de ressource prise en compte. La création de ces graphiques a été chronophage, car nous n’avions pas prévu la communication des résultats au début de l’exercice. Alors que rendre les résultats lisibles aux yeux des lecteurs est la fin de l’exercice.

Il y avait un enjeu politique fort dans nos travaux. Nous savions que le délégué n'aurait pas pu annexer nos travaux au rapport du groupe de travail s’il était dit des choses trop loin de la vision du gouvernement. Le fait que 100% des acteurs présents étaient de l'administration (CAF) a donné une caution à nos travaux.

Notre apprentissage principal est qu’[OpenFisca](https://fr.openfisca.org) permet d’ouvrir un espace de dialogue entre les experts de la loi en outillant le calcul et en le rendant plus aisément communicable à d'autres personnes. [OpenFisca](https://fr.openfisca.org) peut objectiver les échanges autour de la rédaction des réformes autour de cas concrets et améliorer la communication autour des réformes sans en enlever la complexité.

## Si nous refaisions l'exercice, qu'est ce que nous ferions différemment ?

Cette expérience était complètement nouvelle et ancrée dans le besoin bien réel d’un groupe de travail. Nous en sommes sortis avec une analyse intéressante.
Tout ne s’est pas passé exactement comme nous l’aurions souhaité et c’est là que se trouvent généralement les meilleurs apprentissages.
Si les situations se représentaient, voici ce que nous ferions différemment :
Réduire le périmètre législatif : les modifications de la législation sont complexes, et demandent de connaître le métier et [OpenFisca-France](https://fr.openfisca.org/legislation) pour bien comprendre les implications des changements. Chaque modification est très chronophage, il faut donc expliciter le périmètre de la réforme très en amont.

Prioriser une version simplifiée de bout en bout : de la réforme à la visualisation d’impact, avant d’ajouter des cas tests supplémentaires.
Pour tester le plus vite possible la réforme sur une situation.
Identifier les visualisations qui mettront en valeur les résultats.
Faire des workshops plutôt que des réunions : Écrire les réformes et les cas test en séance en binômant métier/tech.

En sortant de cet exercice, nous avons enrichi notre outillage pour accompagner un nouveau type d'utilisateurs :
* des cas tests réutilisables ;
* un petit logiciel qui permet d’automatiser les calculs sur les réformes et extraire les résultats dans un tableur .

## Conclusion

[OpenFisca](https://fr.openfisca.org) peut être utilisé pour créer des simulations de réformes dans le cadre de la création de nouvelles lois.
La forme mathématique des formules de calcul permet à différents experts d’échanger sur les méthodes de calculs.
La possibilité de simuler l’impact de réformes sur des individus et des familles donne des clefs pour mitiger les effets de bords potentiels.
La mise à disposition de cas types et d’exemples de visualisation permet de donner une base de travail qui parle aussi bien aux experts qu’au grand public.

## Pour aller plus loin

[Rapport final](https://www.caissedesdepotsdesterritoires.fr/cs/BlobServer?blobkey=id&blobnocache=true&blobwhere=1250171076233&blobheader=application%2Fpdf&blobcol=urldata&blobtable=MungoBlobs)
[Code source des travaux](https://github.com/openfisca/tutorial/tree/dea8d8fe13e7708af36d7ebfc3496dfb02485ad4/exemples/gt_non_recours)
[Code source OpenFisca-France](https://github.com/openfisca/openfisca-france)
[Explorateur de la législation française](https://fr.openfisca.org/legislation)
[Documentation officielle OpenFisca](https://openfisca.org/doc/)
