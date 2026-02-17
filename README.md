# Sentiment Analysis API Documentation
**v1.2.0** | *Updated February 16, 2026*

Easily analyze text for sentiment using the Sentiment Analysis API.  
The API determines whether text is **positive**, **negative**, or **neutral**, and returns confidence scores for accuracy.

---

## 📋 Table of Contents
- [Overview](#-overview)
- [Authentication](#-authentication)
- [Base URL](#-base-url)
- [Endpoints](#-endpoints)
  - [1. Analyze Sentiment](#1-analyze-sentiment)
  - [2. Batch Analysis](#2-batch-analysis)
- [Status Codes](#-status-codes)
- [Rate Limits](#-rate-limits)
- [Quickstart](#-quickstart-example-curl)
- [Postman Collection](#-postman-collection)
- [Support & Contact](#-support--contact)

---

## 📘 Overview

The Sentiment Analysis API provides NLP features to help developers understand user emotion in:

- customer reviews  
- social media comments  
- chat conversations  
- survey responses  

### **Key Features**
- Classify sentiment: **positive**, **negative**, or **neutral**  
- Confidence scoring for accuracy validation  
- Simple REST API structure  
- Batch processing for multiple inputs  
- Secure authentication using API keys  

---

## 🔐 Authentication

All requests require an API key provided at registration.

**Header**: `Authorization: Bearer YOUR_API_KEY`

---

## 🌍 Base URL

`https://api.sentimently.ai/v1`

---

## 📌 Endpoints

### **1. Analyze Sentiment**
**Endpoint:** `POST /analyze`

Analyze a single text string.

#### **Request Body**
```json
{
  "text": "I love using this product!",
  "language": "en"
}
```
### **Example Response**
``` json
{
  "sentiment": "positive",
  "confidence": 0.94,
  "scores": {
    "positive": 0.94,
    "neutral": 0.04,
    "negative": 0.02
  }
}
```
### **2. Batch Analysis**
**Endpoint:** `POST /analyze/batch`
Analyze multiple text strings at once

#### **Request Body**
```json
{
  "texts": [
    "The service was excellent!",
    "I'm disappointed with the delay."
  ]
}
```
### **Example Response**
``` json
{
  "results": [
    { 
      "text": "The service was excellent!", 
      "sentiment": "positive", 
      "confidence": 0.91 
    },
    { 
      "text": "I'm disappointed with the delay.", 
      "sentiment": "negative", 
      "confidence": 0.87 
    }
  ]
}
```
---
## Status Codes

| Code | Message               | Meaning                          |
|------|-----------------------|----------------------------------
| 200  | OK                    | Successful request              |
| 400  | Bad Request           | Missing or malformed parameters |
| 401  | Unauthorized          | Missing or invalid API key      |
| 429  | Too Many Requests     | Rate limit exceeded             |
| 500  | Internal Server Error | Server encountered an error     |

## Error Response Format ❌🚫
### **Example Error Response**
```json
{
  "error": {
    "code": 401,
    "message": "Unauthorized: Invalid API key."
  }
}
```
---
## Rate Limits

Maximum: 500 requests per minute

Exceeding the limit returns HTTP 429 Too Many Requests
---
## 
🚀 Quickstart Example (cURL)
``` bash

curl -X POST "https://api.sentimently.ai/v1/analyze" \
     -H "Authorization: Bearer YOUR_API_KEY" \
     -H "Content-Type: application/json" \
     -d '{"text": "I love using this product!"}'
```
---
## 📦 Postman Collection

🔗 **[Download Postman Collection](postman-collection.json)**  
✅ **Includes:**
- Pre-configured authentication
- Environment variables  
- Automated test cases
- Sample requests & responses

---

## 💬 Support & Contact

**API support:** support@sentimently.com  
**Documentation feedback:** docs@sentimently.com

---

*Built by Hauwa Kudu Mohammed | [Portfolio](https://jiddarh.github.io/) | February 2026*
