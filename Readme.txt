Launch : tarql --delimiter semicolon --dedup 1000000 rdf.sparql > donnees.rdf
date_de_debut
SELECT ?titre
FROM <donnees.rdf>
WHERE {
	BIND( (year(?date_de_fin) - year(?date_de_debut))*12 + month(?date_de_fin) - month(?date_de_debut) AS ?Mois_effectif)
	BIND (?Mois_effectif - ?duree AS ?difference )
}
ORDER BY ?difference

SELECT DISTINCT ?sigle_de_partenaire ?titre
FROM <donnees.rdf>
WHERE {
	
}