/api/v1/sentiment
{
  "text": "string",
  "method": "afinn | syuzhet | nrc",
  "return_tokens": "boolean"
}
{
  "overall_score": 0.82,
  "sentiment_distribution": {
    "positive": 0.61,
    "negative": 0.12,
    "neutral": 0.27
  },
  "tokens": [
    {
      "word": "helpful",
      "score": 0.9
    }
  ]
}
{
  "status": "online",
  "timestamp": "2025-11-20T13:42Z"
}

# Example Usage:
library(httr)
library(jsonlite)

response <- POST(
  #url = "http://localhost:8000/api/v1/sentiment/analyze",
  body = list(
    text = "The provider described the process as helpful but overwhelming.",
    method = "nrc",
    return_tokens = TRUE
  ),
  encode = "json"
)

content(response, "parsed")
