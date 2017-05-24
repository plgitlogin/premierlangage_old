
# Problèmes

1)
Les repository si ils ont le même nom cela pose des problèmes.
IL faut un étage nomdurepo/ exemple "officiel/"
puis un étage avec le repo exemple "plbank/"
donc officiel/plbank/ est la racine du git


2) edit_file dans les views de gitload.

	je n'arrive pas a faire fonctionner l'editeur
	problemes de static
	il faut récupérer le contenu si il est validé
	puis faire:
	git commit -m "web : $user" fichier
	git push -> en cas d'échec
			git request-pull
	sinon signaler le problème à l'utilisateur


3) Templates généraux 

	Il faut un certain nombre de templates:

	base.html # template général de l'application 
			#  les autres template de page sont construits
			# sur ce template en faisant {% extends "base.html" %}

	gitload.html # template général de gitload
		# Import de l'activité :
		browse.html
		view_file.html
		edit_file.html

	activity.html
		# deux parties
		# le mode
		mode.html
		# l'exercice 
		exo.html

4) Rôles des utilisateurs
	Admin -> connecté local
	Prof
	Elèves

	Droits LTI
	si profs alors accès
		menu racine
			gitload (possibilité d'ajouter un git, de charger un pltp)
			loaded (possibilité de lire une url d'accès)
			playexo (possibilité de tester un pltp et un pl comme un élève)
			classe (possibilité de regarde les élements de la classe)
				=> LTI accès à la classe
	si Elève alors
		menu Eleve:
			choix du pltp
			pltp en cours
				pl upload to LMS grades
	si admin alors
		menu admin
			gitload
			loaded
			playexo

