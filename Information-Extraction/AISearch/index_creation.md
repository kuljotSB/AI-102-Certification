## Creating Azure AI Search Index

- Deploy an AI Multi Service Account in the Azure Portal.

- Upload all the documents in the `collateral` and the `reviews` folders to an Azure Blob Storage container.

- Establish a connection to the blob storage container from Azure AI Search and set `parsing` mode to default.

- Make changes to the following fields:
    - Set `merged_content` to `searchable` and `retrievable`.
    - Set `metadata_storage_name` to `searchable` and `retrievable`.
    - Set `keyPhrase` to `searchable`, `retrievable`, and `filterable`
    - Set `persons`, `locations` and `organizations` to `searchable`, `retrievable`, and `filterable`


Try these lucene queries:

```lucene
 {
  "search": "San Francisco",
  "queryType": "full"
}
```

```lucene
 {
  "search": "title:\"Dubai Brochure.pdf\"",
  "queryType": "full"
}
```

```lucene
{
  "search": "hote*",
  "queryType": "full"
}
```

```lucene
{
  "search": "Dubia~",
  "queryType": "full"
}
```

```lucene
{
  "search": "*",
  "filter": "organizations/any(o: o eq 'Margie’s Travel')"
}
```

```lucene
{
  "search": "*",
  "filter": "locations/any(l: l eq 'London')"
}
```

```lucene
{
  "search": "hotel",
  "queryType": "full",
  "filter": "locations/any(l: l eq 'London') or keyPhrases/any(k: k eq 'beach')"
}
```
