PROFILE MATCH (p:Person)-[:DIRECTED]->(m:Movie)<-[:ACTED_IN]-(p) RETURN p.name,m.title ORDER BY p.name, m.title <br><br>
SECOND ONE DOESNT WORK IN CURRENT STATE <br><br>
PROFILE MATCH (a:Person)-[:ACTED_IN]->(m:Movie)<-[:ACTED_IN]-(b:Person) WHERE elementId(a) < elementId(b) WITH a, b, count(m) AS moviesTogether, collect(m.title)[0..10] As sampleMovieTitles WHERE moviesTogether > 1 RETURN a.name AS actor1, b.name as actor2, moviesTogether, sampleMovieTitles ORDER BY moviesTogether DESC, actor1, actor2 <br><br>
PROFILE MATCH (c:Person {name: "Clint Eastwood"}) MATCH (c)-[*1..4]-(n) WHERE elementId(n) <> elementId(c) RETURN count(DISTINCT n) AS reachable_in_4_hops; <br>

once you have set up the neo4j enviroment and connected to the database, just paste into the query prompt section. 
There will be multiple different types of outputs that are viewable

Graph
- Shows the relationships between nodes
Table
RAW
- shows json query info and json return data from the database
