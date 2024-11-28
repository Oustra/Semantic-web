# Netflix Data Transformation: CSV to RDF

This repository contains a project that transforms Netflix movies and TV shows data from CSV format into RDF (Resource Description Framework) using **OpenRefine** with its RDF extension. The goal is to enable semantic querying and integration of this dataset into the Linked Data cloud.

---

## About the Dataset

The dataset includes metadata about Netflix movies and TV shows, such as:

- **Title**: The name of the movie or TV show.
- **Type**: Movie or TV Show.
- **Director**: Name(s) of the director(s).
- **Cast**: Main actors and actresses.
- **Country**: Country of production.
- **Date Added**: Date the title was added to Netflix.
- **Release Year**: Year of release.
- **Rating**: Content rating (e.g., PG-13, TV-MA).
- **Duration**: Duration in minutes or number of seasons.
- **Genres**: Genres or categories.
- **Description**: Brief summary of the content.

---

## Objectives

- Convert tabular CSV data into a structured RDF format.
- Use semantic vocabularies (e.g., `schema.org`, `dbo`) for consistent and meaningful representation of data.
- Reconcile fields like `Country` with existing Linked Data sources, such as **Wikidata**.

---

## Tools Used

1. **OpenRefine**: A powerful tool for cleaning and transforming data.
    - **RDF Extension**: Used to define an RDF skeleton and export the data in RDF format.
2. **Wikidata Reconciliation Service**: To match country names with corresponding Wikidata URIs.
3. **SPARQL**: For querying the transformed RDF data.

## RDF Mapping Details

The following mappings were applied to the dataset:

| **CSV Field**      | **RDF Property**            | **Example**                                    |
|---------------------|-----------------------------|------------------------------------------------|
| Title               | `dbo:title`                | "Stranger Things"                              |
| Type                | `schema:TVSeries` or `schema:Movie` | "TV Show"                                      |
| Director            | `schema:director`          | "Shawn Levy"                                   |
| Cast                | `schema:actor`             | "Millie Bobby Brown, Finn Wolfhard"           |
| Country             | `dbo:country` (URI)        | `http://www.wikidata.org/entity/Q30` (USA)    |
| Date Added          | `dbo:date`                | "2016-07-15"                                   |
| Release Year        | `schema:datePublished`     | "2016"                                         |
| Rating              | `schema:contentRating`     | "TV-MA"                                        |
| Duration            | `schema:duration`          | "1 Season" or "120 minutes"                   |
| Genres              | `schema:genre`             | "Drama, Thriller"                              |
| Description         | `dbo:description`          | "A group of kids uncover a supernatural mystery." |

## Files in the Repository

- `Netflix.csv`: Original CSV dataset.
- `Netflix.ttl`: Transformed dataset in Turtle format.
- `Netflix.rdf`: Transformed dataset in RDF format.
---

## Results

The RDF dataset enables advanced semantic queries and can be linked to other datasets in the Linked Data cloud, such as:

- Linking `dbo:country` to DBpedia or Wikidata entries.
- Using `schema:actor` to connect actors to their profiles in Linked Data.

---

## References

- [OpenRefine Documentation](https://openrefine.org/documentation.html)
- [Wikidata Reconciliation Service](https://wikidata.reconci.link/)
- [SPARQL Query Language](https://www.w3.org/TR/sparql11-query/)

---

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.
