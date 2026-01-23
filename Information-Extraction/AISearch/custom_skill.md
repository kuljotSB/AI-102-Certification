## Custom Sentiment Analysis Skill in Azure AI Search

Add the following to your AI Search Skillset definition:

Add the following as the custom skill definition:
```json
 {
      "@odata.type": "#Microsoft.Skills.Text.V3.SentimentSkill",
      "name": "sentimentSkill",
      "context": "/document/merged_content/chunk/*",
      "defaultLanguageCode": "en",
      "includeOpinionMining": false,
      "inputs": [
        {
          "name": "text",
          "source": "/document/merged_content/chunk/*",
          "inputs": []
        },
        {
          "name": "languageCode",
          "source": "/document/language",
          "inputs": []
        }
      ],
      "outputs": [
        {
          "name": "sentiment",
          "targetName": "sentiment"
        }
      ]
    }
```

Then, make the following changes to the projection definitions:
```json
{
            "name": "sentiment",
            "source": "/document/merged_content/chunk/*/sentiment",
            "inputs": []
}
```

### Lucene Queries for Sentiment Analysis

```json
{
  "search": "*",
  "filter": "sentiment eq 'positive'"
}
```

```json
{
  "search": "Dubai",
  "queryType": "full",
  "filter": "sentiment eq 'negative'"
}
```

```json
{
  "search": "travel",
  "queryType": "full",
  "filter": "sentiment eq 'positive' and locations/any(o: o eq 'London')"
}
```

