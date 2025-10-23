# Buch Chatbot mit RAG Architecture
Ein intelligenter Chatbot, der tiefes inhaltliches Verständnis für literarische Werke demonstriert, entwickelt mit Retrieval-Augmented Generation (RAG).
# Projektübersicht
Dieses Projekt implementiert ein KI-System, das über reine Textverarbeitung hinausgeht und tiefes inhaltliches Verständnis für das Buch "Heidi" von Johanna Spyri entwickelt. Das System kann komplexe Fragen zu Charakteren, Handlung, Kapiteln und thematischen Elementen beantworten.
# Systemarchitektur
## Kernkomponenten
*  Duale Vektordatenbank: Separate FAISS-Datenbanken für Text-Chunks und komplette Kapitel
*  Intelligente Frageklassifizierung: Automatische Erkennung des Fragetyps für optimierte Antwortstrategien
*  Semantische Suche: Vektoreinbettungen für bedeutungsbasierte Inhaltsrecherche
*  Mehrschichtige Verarbeitung: Unterschiedliche Prompt-Strategien basierend auf Fragetyp

## Entwicklungsschritte
1.  PDF-Verarbeitung - Textextraktion und -bereinigung
2.  Kapitelerkennung - Automatische Identifizierung von Kapiteln mit römischen Zahlen
3.  Semantische Suche - Implementierung von Vektoreinbettungen
4.  QA-System - Spezialisierte Antwortmechanismen

## Technologien & Frameworks
*  LangChain: RAG-Pipeline, Prompt-Templates und Chain-Konstruktion
*  FAISS: Hochperformante Vektordatenbank für semantische Suche
*  HuggingFace Embeddings: Sentence-Transformers für Text-Einbettungen
*  Ollama mit Llama3.2: Lokales LLM für Sprachgenerierung

## Textverarbeitung
*  PyPDFLoader: PDF-Text-Extraktion
*  RecursiveCharacterTextSplitter: Intelligente Textsegmentierung
*  Regex-Pattern-Matching: Kapitelerkennung und -verarbeitung

## Datenaufbereitung
### Textbereinigung
*  Entfernung überflüssiger Zeilenumbrüche und Leerzeichen
*  Elimination von Archiv-Wasserzeichen
*  Bereinigung von Seitenzahlen und Formatierungsartefakten
### Chunking-Strategie
*  Feine Chunks: 800 Zeichen mit 120 Zeichen Überlappung
*  Kapitel-basierte Segmente: Ganze Kapitel als kontextuelle Einheiten
*  Intelligente Trennung: An natürlichen Textgrenzen (Absätze, Sätze)

## Features
### Frageklassifizierung
*  Kapitel-Fragen: Detaillierte Analyse spezifischer Kapitel
*  Charakter-Fragen: Tiefgehende Charakteranalysen
*  Zusammenfassungen: Konzise Inhaltsübersichten
*  Allgemeine Fragen: Umfassende Buchanalyse
### Intelligente Suche
*  Automatische Erkennung römischer Zahlen für Kapitelverweise
*  Dynamische Kontextauswahl basierend auf semantischer Ähnlichkeit
*  Multi-Level Retrieval (Chunks & Kapitel)

## Installation & Usage
### Voraussetzungen
```python
!pip install langchain langchain-community faiss-cpu sentence-transformers pyPDF
```
### System starten
# System starten
```python
from main import initialize_system, run_system_tests
qa_system = initialize_system()
antwort = qa_system.answer_question("Was sind die Namen der Ziegen in der Geschichte?")
print(antwort)
```
### Beispiel-Fragen
1.  "Who is the author of the book?"
2.  "What are the names of the goats in the story?"
3.  "Summarize the events of Chapter II"
4.  "What happens in Chapter I?"
5.  "What is the relationship between Heidi and her grandfather?" 
