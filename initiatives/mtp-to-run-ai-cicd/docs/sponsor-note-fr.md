# Note de présentation au sponsor

## Objet

Proposer une phase de cadrage de deux semaines pour un groupe de travail transversal **MTP-to-Run & AI-Augmented CI/CD**, sans achat ni changement en production.

Le groupe examinerait une continuité concrète entre les recommandations du Master Test Plan, les règles industrielles de dimensionnement, les différentes BOM, la génération gouvernée d'Infrastructure as Code, les preuves issues du testbed et l'apprentissage opérationnel autorisé.

La proposition ne consiste pas à laisser une IA décider ou déployer seule. L'IA pourrait rechercher, comparer, détecter des incohérences, proposer des variantes et générer des brouillons. Les responsables humains conserveraient l'autorité sur l'architecture, les données, le risque résiduel, le déploiement et toute modification d'une règle industrielle.

Le premier cas serait volontairement limité et synthétique : partir d'une recommandation MTP et d'un modèle de dimensionnement de démonstration, produire un Solution Manifest et une BOM traçables, générer un brouillon IaC et ses tests, l'exécuter dans un environnement isolé, puis constituer automatiquement le dossier de preuve.

La phase de cadrage devrait livrer :

- le cas pilote et son propriétaire ;
- l'inventaire des actifs réutilisables et sources faisant autorité ;
- le contrat minimal de traçabilité ;
- l'évaluation sécurité, confidentialité et réutilisation des données ;
- la baseline mesurée, les seuils quantifiés, le budget maximal et le protocole de mesure ;
- le plan et les conditions d'arrêt du pilote de 90 jours ;
- une recommandation explicite : arrêter, réduire ou poursuivre.

Ces résultats constituent le jalon P0 : le pilote ne démarre pas si P0 n'est pas approuvé. La décision demandée à ce stade porte uniquement sur le cadrage. Le dépôt contient une proposition détaillée, dix gates réutilisant le service commun de décisions humaines, un exemple de Solution Manifest et six vues SysML/UML/BPMN pour permettre une revue technique contradictoire avant tout engagement.
