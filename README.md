# CitationFinder
The project aims to automate the process of generating relevant citations for a given text and conducting literature review for researchers.

## Research Problem:

As a researcher, it is often necessary to substantiate one's statements with existing literature by providing relevant citations. This can be a time-consuming and labor-intensive process, particularly when searching for citations that are both relevant and up-to-date. Moreover, literature review can be slow, making it difficult to write and publish research papers in a timely manner. Additionally, while researchers may have past knowledge on a topic, linking it to the existing literature can be a challenging task, especially when searching for the relevant citations manually.

## The Solution:

To solve these problems, we propose a tool that uses both semantic and AI search techniques to generate relevant citations for a given text. The tool searches the Crossref database using a combination of text-based queries and extracted keywords to identify relevant literature. The search results are then ranked based on their relevance score, which is generated using AI techniques. The most relevant citations are presented to the user in a user-friendly format, allowing them to quickly and easily review the literature and add relevant citations to their research paper.

With this tool, researchers can save time and effort by quickly finding and selecting relevant citations, improving their research process, and enabling them to publish their work more efficiently. Additionally, the tool can aid researchers in identifying new research areas by surfacing relevant literature, helping them stay up-to-date with the latest developments in their field.

## UML:
 `mermaid`
sequenceDiagram
    participant User
    participant API
    participant Crossref
    participant OpenAI
    participant Pandas
    
    User->>+API: Define Query Text
    API->>+Crossref: Send Query Text
    Crossref->>-API: Send Data
    API->>+Pandas: Create DataFrame
    Pandas->>-API: Send DataFrame
    API->>+OpenAI: Generate Keywords
    OpenAI->>-API: Send Keywords
    API->>+Crossref: Send Query with Keywords
    Crossref->>-API: Send Data
    API->>+OpenAI: Extract Relevance Score
    OpenAI->>-API: Send Score
    API->>+Pandas: Sort DataFrame by Score
    Pandas->>-API: Send Sorted DataFrame
    User->>+API: Get Citations
    API->>+User: Display Citations
