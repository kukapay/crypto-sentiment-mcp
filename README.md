# Crypto Sentiment MCP Server

An MCP server that delivers cryptocurrency sentiment analysis to AI agents, leveraging Santiment's aggregated social media and news data to track market mood and detect emerging trends.

![GitHub License](https://img.shields.io/github/license/kukapay/crypto-sentiment-mcp)
![Python Version](https://img.shields.io/badge/python-3.10+-blue)
![Status](https://img.shields.io/badge/status-active-brightgreen.svg)


## Features

- **Sentiment Analysis**: Retrieve sentiment balance (positive vs. negative) for specific cryptocurrencies.
- **Social Volume Tracking**: Monitor total social media mentions and detect significant shifts (spikes or drops).
- **Social Dominance**: Measure the share of discussions an asset occupies in crypto media.
- **Trending Words**: Identify the most popular terms trending in cryptocurrency discussions.

## Tools

| Tool Name               | Description                                                                                   | Parameters                                  |
|-------------------------|-----------------------------------------------------------------------------------------------|---------------------------------------------|
| `get_sentiment_balance` | Get the average sentiment balance for an asset over a specified period.                      | `asset: str`, `days: int = 7`              |
| `get_social_volume`     | Fetch the total number of social media mentions for an asset.                                | `asset: str`, `days: int = 7`              |
| `alert_social_shift`    | Detect significant spikes or drops in social volume compared to the previous average.        | `asset: str`, `threshold: float = 50.0`, `days: int = 7` |
| `get_trending_words`    | Retrieve the top trending words in crypto discussions, ranked by score over a period.        | `days: int = 7`, `top_n: int = 5`          |
| `get_social_dominance`  | Measure the percentage of crypto media discussions dominated by an asset.                    | `asset: str`, `days: int = 7`              |

## Prerequisites

- **Python**: 3.10 or higher
- **Santiment API Key**: Obtain a free or paid key from [Santiment](https://app.santiment.net/). 

## Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/kukapay/crypto-sentiment-mcp.git
   cd crypto-sentiment-mcp
   ```

2. **Configure Client**:
    ```
    {
      "mcpServers": {
        "crypto-sentiment-mcp": {
          "command": "uv",
          "args": ["--directory", "path/to/crypto-sentiment-mcp", "run", "main.py"],
          "env": {
            "SANTIMENT_API_KEY": "your_api_key_here"
          }
        }
      }
    }
    ```  

## Examples

Below are examples of natural language inputs and their corresponding outputs when interacting with the server via an MCP-compatible client:

- **Input**: "What's the sentiment balance for Bitcoin over the last week?"
  - **Output**: "Bitcoin's sentiment balance over the past 7 days is 12.5."

- **Input**: "How many times has Ethereum been mentioned on social media in the past 5 days?"
  - **Output**: "Ethereum's social volume over the past 5 days is 8,432 mentions."

- **Input**: "Tell me if there's been a big change in Bitcoin's social volume recently, with a 30% threshold."
  - **Output**: "Bitcoin's social volume spiked by 75.0% in the last 24 hours, from an average of 1,000 to 1,750."

- **Input**: "What are the top 3 trending words in crypto over the past 3 days?"
  - **Output**: "Top 3 trending words over the past 3 days: 'halving', 'bullrun', 'defi'."

- **Input**: "How dominant is Ethereum in social media discussions this week?"
  - **Output**: "Ethereum's social dominance over the past 7 days is 18.7%."


## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
