
Un LLM prédit le token suivant le plus probable compte tenu des tokens précédents et de ses données d'entrainement. Pas de raisonnement, pas de compréhension : de la statistique sur du texte à partir d'une immense base de donnée. 

On pourrait penser, et c'est l'utilisation la plus courante, que la meilleur façon de tirer profit d'un LLM c'est de l'utiliser pour sa base de connaissance. Les problèmes que ça pause 

- dépendance (analogie google effect)
- hallucination
- dette technique
- ... (essai de faire une liste exhaustive)

Ce n'est pas mon approche. Pour ma part je l'utilise pour sa "capacité de raisonnement" alors qu'on vient de rappeler que tout ça n'était au fond que des calculs statistiques. Je ne lui demande pas ce qu'il sait : je lui fournis exactement ce dont moi j'aurais besoin pour résoudre. ça présuppose bien sur que je maitrise le sujet et que je pourrais le faire moi même c'est juste un gain de temps. Je lui donne donc les connaissances, les outils qui apportent du déterminismes partout ou c'est possible et du feedback


Mes règles d'usage IA

1 - Fixer une limite d'utilisation (analogie avec data version 3g 4g 5g... si on fixe une limite qui n'évolue pas avec la version on évite les effets rebonds sinon a chaque nouvelle version on a tendance a utiliser toujours plus de données)
2 - Utiliser que pour qqch que l'on sait faire (accélère ce que l'on peut faire sois même)
3 - Contenir le pouvoir d'action de l'agent (sois supervision de chaque sortie, sois containerisation pour process autonome revue à la fin)
4 - Fournir les informations et ne pas se fonder sur les données d'entrainements (assure la conservation de la maitrise, améliore grandement la qualité)
5 - Fournir un feedback autonome (améliore la qualité)
6 - Restreindre le context au minimum pour la tache en cours
7 - Automatiser la construction du context