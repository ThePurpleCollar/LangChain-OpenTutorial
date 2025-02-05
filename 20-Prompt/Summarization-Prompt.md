# **Summarization Prompt**

## **Description**

- This prompt is designed to help you create concise yet comprehensive summaries from various types of documents (e.g., transcripts, research papers, articles). By analyzing the provided text, it extracts key ideas, context, and details, delivering a coherent overview that highlights the most important points.

---

## **Input**

- SYSTEM: You are an expert summarizer. Please read the document below and summarize the most critical information. Focus on core ideas, statistics, or facts that should not be overlooked.
- HUMAN:
  """
  [Paste your text here, in paragraphs or bullet points if relevant]
  """
  
*Note: For long texts, consider breaking into chunks (e.g., 500 words) with a 50-word overlap to maintain context coherence.*

---

## **Output**

Generate a summary in one of two formats:
- Bullet-point format (numbered or bulleted)
- Concise executive summary (1-5 sentences)

Key Requirements:
- Include relevant numbers, statistics, or contextual dates
- Ensure coherence
- Avoid excessive repetition
- Do not omit vital details

### **Example Output**

**Option 1: Key Points**
1. First critical point
2. Second critical point
3. Third critical point

**Option 2: Executive Summary**
[1-5 sentences capturing the main ideas]

---

## **Tool**

### **Document Loader**
- **Description**: Loads a document or transcript from a specified source
- **Input Types**:
  - File path  
  - URL  
  - Direct text input

**Usage Example**:
```python
DocumentLoader("path/to/file.txt")
DocumentLoader("https://example.com/document")
```

### **Text Chunking Assistant**
- **Description**: Splits large texts into manageable chunks for easier processing
- **Input Types**:
    - JSON configuration for chunkSize (number of words to include in each chunk).
    - JSON configuration for overlapSize (number of words to overlap between chunks)

**Configuration Example**:
```json
{
  "chunkSize": {
    "unit": "words",
    "value": 500
  },
  "overlapSize": {
    "unit": "words",
    "value": 50
  }
}
```

**Usage Example**:
```python
ChunkingAssistant(chunkSize=500, overlap=50).process(text)
```