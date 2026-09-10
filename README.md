# Kityo0.github.io

# Exercice 2

## Récupération des information rdf de ma page personnel orcid
```
curl -L -H "Accept: application/rdf+xml" "https://orcid.org/0009-0003-7062-7941"
```

Resultat:
```
<rdf:RDF
    xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"
    xmlns:owl="http://www.w3.org/2002/07/owl#"
    xmlns:prov="http://www.w3.org/ns/prov#"
    xmlns:pav="http://purl.org/pav/"
    xmlns:rdfs="http://www.w3.org/2000/01/rdf-schema#"
    xmlns:gn="http://www.geonames.org/ontology#"
    xmlns:foaf="http://xmlns.com/foaf/0.1/"
    xmlns:xsd="http://www.w3.org/2001/XMLSchema#">
  <foaf:PersonalProfileDocument rdf:about="https://pub.orcid.org/orcid-pub-web/experimental_rdf_v1/0009-0003-7062-7941">
    <pav:createdOn rdf:datatype="http://www.w3.org/2001/XMLSchema#dateTime"
    >2026-09-10T08:48:51.007Z</pav:createdOn>
    <prov:generatedAtTime rdf:datatype="http://www.w3.org/2001/XMLSchema#dateTime"
    >2026-09-10T08:48:51.597Z</prov:generatedAtTime>
    <pav:lastUpdateOn rdf:datatype="http://www.w3.org/2001/XMLSchema#dateTime"
    >2026-09-10T08:48:51.597Z</pav:lastUpdateOn>
    <pav:createdWith rdf:resource="https://orcid.org"/>
    <prov:wasAttributedTo>
      <prov:Person rdf:about="https://orcid.org/0009-0003-7062-7941">
        <foaf:account>
          <foaf:OnlineAccount rdf:about="https://orcid.org/0009-0003-7062-7941#orcid-id">
            <rdfs:label>0009-0003-7062-7941</rdfs:label>
            <foaf:accountName>0009-0003-7062-7941</foaf:accountName>
            <foaf:accountServiceHomepage rdf:resource="https://orcid.org"/>
          </foaf:OnlineAccount>
        </foaf:account>
        <foaf:publications>
          <foaf:Document rdf:about="https://orcid.org/0009-0003-7062-7941#workspace-works"/>
        </foaf:publications>
        <foaf:familyName>DOUCET</foaf:familyName>
        <foaf:givenName>Evann</foaf:givenName>
        <rdfs:label>Evann DOUCET</rdfs:label>
        <rdf:type rdf:resource="http://xmlns.com/foaf/0.1/Person"/>
      </prov:Person>
    </prov:wasAttributedTo>
    <pav:createdBy rdf:resource="https://orcid.org/0009-0003-7062-7941"/>
    <foaf:maker rdf:resource="https://orcid.org/0009-0003-7062-7941"/>
    <foaf:primaryTopic rdf:resource="https://orcid.org/0009-0003-7062-7941"/>
  </foaf:PersonalProfileDocument>
</rdf:RDF>
```

# Exercice 3

mon pod est accéssible dans le lien
```
https://web_semantique.solidcommunity.net/
```

mon webID est accéssible via:
```
https://web_semantique.solidcommunity.net/profile/card#me
```
Pour récupérer les triplet de ma description sur solidcommunity, lancer la commande:
```
curl -L -H "turtle" "https://web_semantique.solidcommunity.net/profile/card#me"
```

Resultat:
```
@prefix : <#>.
@prefix foaf: <http://xmlns.com/foaf/0.1/>.
@prefix ldp: <http://www.w3.org/ns/ldp#>.
@prefix org: <http://www.w3.org/ns/org#>.
@prefix schema: <http://schema.org/>.
@prefix solid: <http://www.w3.org/ns/solid/terms#>.
@prefix space: <http://www.w3.org/ns/pim/space#>.
@prefix vcard: <http://www.w3.org/2006/vcard/ns#>.
@prefix xsd: <http://www.w3.org/2001/XMLSchema#>.
@prefix inbox: </inbox/>.
@prefix set: </settings/>.
@prefix web: </>.
@prefix sol: <https://solidcommunity.net/>.
@prefix ent: <http://www.wikidata.org/entity/>.

<> a foaf:PersonalProfileDocument; foaf:maker :me; foaf:primaryTopic :me.

:id1789032679079
    a solid:PastRole;
    schema:description "mon alternance";
    schema:endDate "2026-09-01"^^xsd:date;
    schema:startDate "2024-05-01"^^xsd:date;
    vcard:role "safran aerosystems";
    org:member :me;
    org:organization :id1789032679080 .
:id1789032679080
    a schema:Corporation, vcard:Organization;
    schema:name "Safran";
    schema:uri "https://www.safran-group.com/fr";
    org:location "cognac";
    solid:publicId ent:Q1886126 .
:me
    a foaf:Person;
    vcard:note "ma biographie";
    ldp:inbox inbox:;
    space:preferencesFile set:prefs.ttl;
    space:storage web:;
    solid:oidcIssuer sol:;
    solid:privateTypeIndex set:privateTypeIndex.ttl;
    solid:publicTypeIndex set:publicTypeIndex.ttl.
```

Liste de triplé de film mediaKraken:
```
@prefix dc: <http://purl.org/dc/terms/>.
@prefix ldp: <http://www.w3.org/ns/ldp#>.
@prefix posix: <http://www.w3.org/ns/posix/stat#>.
@prefix xsd: <http://www.w3.org/2001/XMLSchema#>.

<> a ldp:Container, ldp:BasicContainer, ldp:Resource;
    dc:modified "2026-09-10T09:41:34.895Z"^^xsd:dateTime;
    posix:mtime 1789033294.
<the-lord-of-the-rings-the-return-of-the-king-2003> a ldp:Resource, <http://www.w3.org/ns/iana/media-types/text/turtle#Resource>;
    dc:modified "2026-09-10T09:41:34.895Z"^^xsd:dateTime;
    posix:mtime 1789033294;
    posix:size 1216.
<> ldp:contains <the-lord-of-the-rings-the-return-of-the-king-2003>.
<12-angry-men-1957> a ldp:Resource, <http://www.w3.org/ns/iana/media-types/text/turtle#Resource>;
    dc:modified "2026-09-10T09:41:34.671Z"^^xsd:dateTime;
    posix:mtime 1789033294;
    posix:size 990.
<> ldp:contains <12-angry-men-1957>.
<the-godfather-part-ii-1974> a ldp:Resource, <http://www.w3.org/ns/iana/media-types/text/turtle#Resource>;
    dc:modified "2026-09-10T09:41:34.435Z"^^xsd:dateTime;
    posix:mtime 1789033294;
    posix:size 889.
<> ldp:contains <the-godfather-part-ii-1974>.
<the-dark-knight-2008> a ldp:Resource, <http://www.w3.org/ns/iana/media-types/text/turtle#Resource>;
    dc:modified "2026-09-10T09:41:34.215Z"^^xsd:dateTime;
    posix:mtime 1789033294;
    posix:size 1057.
<> ldp:contains <the-dark-knight-2008>.
<the-godfather-1972> a ldp:Resource, <http://www.w3.org/ns/iana/media-types/text/turtle#Resource>;
    dc:modified "2026-09-10T09:41:33.975Z"^^xsd:dateTime;
    posix:mtime 1789033293;
    posix:size 966.
<> ldp:contains <the-godfather-1972>.
<the-shawshank-redemption-1994> a ldp:Resource, <http://www.w3.org/ns/iana/media-types/text/turtle#Resource>;
    dc:modified "2026-09-10T09:41:33.767Z"^^xsd:dateTime;
    posix:mtime 1789033293;
    posix:size 1062.
<> ldp:contains <the-shawshank-redemption-1994>.
```

# Exercice 4

java -jar ldspider-1.3-with-dependencies.jar \
  -s seeds.txt \
  -b  2 50 10 \
  -o resultat_crawl.nq \
  -t 4
