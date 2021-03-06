# Conception de packages

Le chapitre A36/F29\ \faBook\ du livre du cours contient des directives pour la conception de packages. 

Les points importants sont les suivants (les détails se trouvent dans le livre):

- La notation UML des diagrammes de package
- Organiser les packages par **cohésion**
- Organiser les packages une **famille d'interface** (convention Java)
- Créer un package par **tâche** et par **groupe de classes instables** (Branches)
- Les packages les plus responsables sont les plus stables
- Factoriser les types indépendants
- Utiliser **fabrique** (factory) pour limiter la dépendance aux packages concrets
- Comment rompre les cycles dans les packages

La figure\ \ref{DiagrammePackage} est un exemple d'un diagramme de package.

```{.plantuml hide-image=true plantuml-filename=build/images/DiagrammePackage.pdf}
@startuml
!include ../forme.pumlinclude
allowmixing
package "Services Techniques" as ST <<Folder>> {
    package Persistance <<Folder>> {
    }
    package Sécurité <<Folder>> {
    }
    package Journalisation <<Folder>> {
    }
}
package Domaine as D <<Folder>> {
    package POS <<Folder>> {
    }
    package Stocks <<Folder>> {
    }
    package Taxes <<Folder>> {
    }
}

D -d[hidden]- ST

' skinparam legendfontsize 5
' legend center
' Filename: %filename()
' end legend

@enduml
```

![Diagramme de packages (tiré de la figure F12.6\ \faBook\ du livre du cours). [(PlantUML)](http://www.plantuml.com/plantuml/uml/XPDHRzGm3CVVA-qxM9FGjeT9yC0BcgOXRaE3IKoqZ0V4WqbyhTNKEPoKku7sWVOvziLmji4Ac-wgo4tZN-A_xVGePTGy3g5AFSi25GT8-JAGMMLNF5iJrpTqVQjn5EzYY0fPKPAvIF9MjGEvumGs43eKlrJEcGJcKJAmm6SM7vV9m8S3FSrn3BaWWWF1U-LKzfmsRunhEae4CNUa2KACFRHAU7jOVV4MTWViJUYeP97fSiVUB9PG2EGjgiBhipFuL1z_h2VXuSNplMbA_oj8s1OZwtMUIW_lugY2OIstwfs7sYalybhkdAnKcgR2fYNCEb9bUSNbm2kMjbfO8uhGxPhq1pjAq93hXB-FbBO14zGD71oSnE193m_XLmNs_DbqRf6ip2YE7aDN_w3rpRKRJSJDzIRolXgSC7EKf-YhlwfdSK0MAZfdQsH-g3VAoz7rQHFLu8hIqugg6UpxBnrxJ_9rtwfMsJL-w46WbiINBYN-IV3Id7TBuEpAazht2GSgBNm5p-RtqzqzMo_G7LjLHsRjJ_eD)](build/images/DiagrammePackage.pdf){#DiagrammePackage}
