![img_1.png](img_1.png)

# NovaCore
**Own your data. Master your AI.**

NovaCore ist eine **Enterprise-fähige, souveräne KI-Plattform** für lokale Wissensverarbeitung, Retrieval Augmented Generation (RAG) und agentenbasierte Automatisierung.

NovaCore richtet sich an **Unternehmen, Behörden und anspruchsvolle Entwicklerteams**, die KI **kontrolliert, nachvollziehbar und datensouverän** einsetzen möchten – ohne Vendor-Lock-in und ohne unkontrollierten Datenabfluss.

---

## 🎯 Mission

- Volle Datenhoheit über Wissen & KI
- Strukturierte, reproduzierbare RAG-Pipelines
- Transparente & messbare KI-Ergebnisse
- Enterprise-Architektur statt Prototypen-Chaos

---

## 🏗️ Deployment & Betriebsmodelle

NovaCore ist eine **Web-Anwendung** und kann flexibel in unterschiedlichen Betriebsmodellen eingesetzt werden – je nach Sicherheitsanforderungen, Infrastruktur und Compliance-Vorgaben.

### Unterstützte Betriebsarten

- **Local / On-Premise**
  - Betrieb vollständig innerhalb der eigenen Infrastruktur
  - Keine externen Abhängigkeiten erforderlich
  - Ideal für sensible Daten, Behörden & regulierte Umgebungen

- **Private Cloud (Self-Hosted)**
  - Deployment in einer eigenen Cloud-Umgebung (z. B. Azure, AWS, GCP)
  - Volle Kontrolle über Daten, Netzwerke & Zugriffe
  - Geeignet für skalierbare Enterprise-Setups

- **Self-Managed Cloud**
  - Betrieb in gemanagten Kubernetes- oder VM-Umgebungen
  - Integration in bestehende CI/CD- und Security-Setups
  - Kombinierbar mit lokalen und externen LLM-Providern

- **Docker Compose**
  - Fertige Docker-Compose-Konfigurationen für Infrastruktur (PostgreSQL + Qdrant) und Anwendung
  - Multi-Stage Docker Build für optimierte Images

Unabhängig vom Betriebsmodell bleibt NovaCore:
- **datensouverän**
- **vollständig kontrollierbar**
- **ohne Vendor-Lock-in**

> „Local" bedeutet bei NovaCore **kontrolliert betrieben** – nicht „Desktop-Anwendung".

---

## 📋 Features

### 💬 RAG-basierter Chat
Konversationen mit **echtem, prüfbarem Kontext**:

- Antworten ausschließlich auf Basis eigener Dokumente
- Transparente Quellenangaben mit URLs und Relevanz-Scores unter jeder Antwort
- Mehrere Chat-Profile je Use-Case mit individueller Collection-, Prompt- und LLM-Zuordnung
- **Streaming-Responses** via Server-Sent Events für Echtzeit-Ausgabe
- **Persistente Chat-Sessions** – Gespräche speichern, laden und fortsetzen
- **Demo-Fragen** pro Chat-Konfiguration für schnellen Einstieg
- Konfigurierbarer TopK-Parameter und Temperatur pro Anfrage
- **Performance Metrics**
  - Laufzeiten
  - Token-Nutzung (Input/Output)
  - Retrieval-Qualität & Chunk-Trefferquote

---

### ✏️ Live Document Editor
KI-gestützter WYSIWYG-Dokumenten-Editor:

- Echtzeit-HTML-Editor mit vollständiger Formatierungsleiste
- Integrierter KI-Chat zur Dokumenterstellung und -bearbeitung
- **Live-Editing**: Änderungen werden sichtbar einzeln angewendet – wie kollaboratives Editing
- Strukturierte Dokumentoperationen (Sektionen ersetzen, einfügen, löschen, anhängen)
- Session-Management – Dokumente speichern und laden
- HTML-Export
- Token-Statistiken und Nachrichten-Tracking

---

### 🤖 Agent Chunker
Intelligenter Agent zur automatischen Wissenserschließung:

- Web-Suche basierend auf einer Fragestellung (Google Search API, SerpApi)
- Automatischer Download & Parsing von Webseiten
- KI-gestützte Chunk-Erstellung
- Direkte Integration in die RAG-Pipeline
- Wiederverwendbare Chunk-Strategien:
  - Gesetzestexte (Paragraphen, Artikel)
  - Markdown
  - Strukturierte Dokumente

---

### 📄 Dokumentenverarbeitung & Import
Zentrale Wissensaufbereitung mit vielfältigen Import-Wegen:

- **Smart Document Chunking** mit Pattern-Erkennung und KI-gestützter Segmentierung
- **Import-Formate:**
  - PDFs (via PdfPig)
  - HTML (via HtmlAgilityPack)
  - Markdown
  - Plain Text
- **Web-Chunker** – Einzelne Webseiten importieren mit automatischer Inhaltsextraktion
- **Wikipedia-Chunker** – Wikipedia-Artikel mit sektionsbasiertem Chunking (Mehrsprachig)
- **KI-basiertes Text-Chunking** – LLM-gestützte semantische Segmentierung mit Token-Management
- **Notion-Plugin**
  - Direkter Import von Seiten & Datenbanken
  - Content-Vorschau vor dem Import
  - Kategorie-Management
  - Konfigurierbare Workspace-Verbindungen
- **Collections** zur logischen Trennung von Wissensräumen mit individueller Embedder-Zuordnung

---

### 🔌 REST API
Programmatischer Zugriff auf NovaCore-Funktionalität:

- **POST `/api/chat`** – Synchrone Chat-Anfrage mit RAG-Kontext
- **POST `/api/chat_stream`** – Streaming-Chat via Server-Sent Events
- **POST `/api/DocumentChunker/chunk`** – KI-gestütztes Dokumenten-Chunking (PDF, HTML, Text)
- **API-Key-Authentifizierung** über `X-API-Key` Header
- API pro Chat-Konfiguration aktivierbar/deaktivierbar
- Temperatur-Steuerung und Source-Tracking

---

### 🔑 API-Key-Management
Verwaltung von API-Schlüsseln für den REST-API-Zugriff:

- Erstellen, Aktivieren und Deaktivieren von API-Keys
- Optionales Ablaufdatum
- Nutzungs-Tracking (letzter Zugriff)
- Sichere Anzeige mit Schlüssel-Prefix (`nvc_`)

---

### 🛠️ Konfiguration & Management

#### Prompt-Management
- Prompt-Editor für System- & Agent-Prompts
- **Prompt-Analyzer** – KI-gestützte Prompt-Generierung auf Basis von Collection-Inhalten
- Analyse & Vergleich von Prompt-Varianten

#### LLM-Management
- Mehrere Modelle und Provider gleichzeitig konfigurierbar
- Modell-Browser mit Verfügbarkeitsprüfung je Provider
- **Separate Embedding-Provider-Konfiguration** – unabhängig von Chat-LLMs

#### Chat-Konfigurationen
- Mehrere Chat-Profile mit individueller Collection-, Prompt- und LLM-Zuordnung
- API-Freischaltung pro Chat
- Demo-Fragen und Optionen-Panel konfigurierbar

#### Collection-Management
- Qdrant-Collections mit Punkt-Anzahl, Vektor-Dimensionen und Status
- Individuelle Embedder-Zuordnung pro Collection
- Content-Vorschau

---

### 📈 Analytics & Testing

#### RAG-Debugger
- Interaktives Test-Tool für RAG-Suchen
- Parameter-Optimierung (TopK, Score-Threshold)
- Direkte Ergebnis-Inspektion

#### Vector-Search-Tester
- Vektorsuche gegen Qdrant und ElasticSearch testen
- Performance-Vergleich zwischen Backends

#### Topic-Klassifikation
- KI-gestützte Themenanalyse über Collections
- Query-basierte oder allgemeine Themen-Extraktion

#### Parser-Schema-Generator
- KI-gestützte XPath-Parser-Erstellung für HTML-Strukturen
- Schema-Test und Vorschau

#### Metriken
- Laufzeit-Metriken pro Anfrage
- Token- & Kostenanalyse
- Chunk-Verteilung & Qualitätsmetriken

---

### 🔐 Authentifizierung & Benutzerverwaltung
- Cookie-basierte Authentifizierung mit konfigurierbarer Session-Dauer
- **Benutzerverwaltung** – Benutzer anlegen, bearbeiten, aktivieren/deaktivieren
- **Rollenbasierte Zugriffskontrolle (RBAC)** – Rollen zuweisen und verwalten
- Login-Rate-Limiting zum Schutz vor Brute-Force
- Last-Login-Tracking

---

## 🤖 LLM- & Provider-Unterstützung

NovaCore unterstützt eine Vielzahl von LLM-Providern über eine einheitliche Provider-Abstraktion (`ILlmProvider`). Alle Provider unterstützen Chat, Streaming und Embedding.

### Lokale Modelle
- **Ollama**
  - Alle Ollama-kompatiblen Modelle (Mistral, Llama, Gemma, etc.)
  - Lokale Embedding-Modelle (z. B. `nomic-embed-text`)
- **Ollama Cloud** – Ollama-API über externe Endpunkte

### Cloud & API-basierte Modelle
- **Claude API** (Anthropic) – Hochwertige Analyse- & Reasoning-Fähigkeiten
- **Azure OpenAI** – Enterprise-OpenAI über Azure
- **Google Gemini** – Google AI Modelle
- **Mistral API** – Europäischer KI-Provider
- **OpenRouter** – Zugang zu zahlreichen Modellen über eine API

### Vektor-Datenbanken
- **Qdrant** – Primäre Vektor-Datenbank mit Collection-Management
- **ElasticSearch** – Alternative Vektor-Suche mit Dense-Vector-Support

### Web-Suche
- **Google Search API** – Direkte Google-Suche
- **SerpApi** – Search Engine Results API

---

## 🛠️ Technologie-Stack

### Backend & Architektur
- **.NET 10.0**
- **Entity Framework Core** (PostgreSQL via Npgsql)
- **Serilog** (Logging)

### UI
- **Blazor Server** (Interactive Server Mode)
- **Radzen Blazor Components**

### AI / RAG
- **8 LLM-Provider** (Ollama, Claude, Azure OpenAI, Gemini, Mistral, OpenRouter, Ollama Cloud, ElasticRag)
- **Qdrant** (Vector Database)
- **ElasticSearch** (Vector Search)

### Parsing & Dokumente
- **PdfPig** (PDF-Extraktion)
- **HtmlAgilityPack** (HTML-Parsing)
- **Markdig** (Markdown-Rendering)
- **OpenXml** (Office-Dokumente)

### Infrastruktur
- **Docker** & **Docker Compose**
- **PostgreSQL 18**
- **Qdrant**

---

## 🏢 Enterprise-Readiness

NovaCore ist **von Grund auf Enterprise-ready konzipiert**.

### Warum .NET 10?
- Langfristige Stabilität & planbare Release-Zyklen
- Hervorragende Performance (Async, Parallelisierung, Memory-Effizienz)
- Starke Typisierung → wartbarer Code bei wachsender Komplexität
- Exzellente Observability & Debugging-Tools
- Bewährte Plattform für langlebige Unternehmenssoftware

### Warum Blazor Server?
- Zentrale Kontrolle über Geschäftslogik & Security
- Keine verteilte Business-Logik im Client
- Direkte Integration mit .NET-Services
- Ideal für interne Tools, Admin-Oberflächen & Fachanwendungen
- Sehr gut geeignet für:
  - Authentifizierung
  - Rollen & Berechtigungen
  - Audit-Logs

### Architekturprinzipien
- Saubere Trennung von UI, Services & Infrastruktur
- Erweiterbar über Provider- & Factory-Pattern
- Rollenbasierte Zugriffskontrolle (RBAC)
- API-Key-basierter Zugang für externe Systeme
- Vorbereitet für Multi-Tenant-Betrieb

---

## 🚀 Getting Started

### Voraussetzungen

1. .NET 10.0 SDK
2. PostgreSQL
3. Qdrant
4. Ollama (optional, z. B. `mistral-small3.1`, `nomic-embed-text`)

---

### Installation

```bash
git clone <repository-url>
cd NovaCore/src
dotnet restore
dotnet run
```

### Docker Compose

```bash
# Infrastruktur (PostgreSQL + Qdrant)
cd infrastructure/Infra
docker-compose up -d

# Anwendung
cd infrastructure/app
docker-compose up -d
```

---

## 🧭 Roadmap / Coming Soon

### 🤖 LLM- & Provider-Erweiterungen
- **OpenAI API** (direkt)
- Einheitliche Failover-Strategien pro Provider
- Modell-Routing je Use-Case (Kosten, Latenz, Qualität)

---

### 📄 Dokumenten- & Wissens-Synchronisation

#### 🔄 Notion Plugin – Erweiterung
- Inkrementelle Synchronisation (Delta-Updates)
- Erkennung von Änderungen & Löschungen
- Versionierte RAG-Chunks
- Hintergrund-Synchronisation über Agenten

#### 📁 Massen-Dokumenten-Synchronisation
- Agent für Bulk-Import von:
  - PDFs
  - Text-Dateien
  - Word-Dokumenten
- Ordner- & Dateisystem-Watcher
- Automatische Re-Indexierung bei Änderungen

---

### 🔌 Wissens- & Business-Integrationen
- **Confluence Synchronisation**
  - Space-basierter Import
  - Seitenbaum als semantische Struktur
- **Jira Synchronisation**
  - Tickets, Kommentare & Beschreibungen
  - Projekt- & Label-basierte Wissensräume

---

### 🔐 Authentifizierung & Sicherheit
- **Microsoft Entra ID**
- **Keycloak (OIDC / SAML)**
- Multi-Tenant-Betrieb

---

### 🧠 Agenten & Automatisierung
- Background-Agenten für zeitgesteuerte Jobs
- Event-basierte Re-Indexierung
- Detaillierte Laufzeit- & Kostenmetriken pro Agent

---

### 📊 Governance & Enterprise Features
- Audit-Logs für Zugriffe & Antworten
- Nachvollziehbare Quellenketten
- Vorbereitung für Compliance- & Prüfanforderungen

---

## 🌍 Vision

NovaCore entwickelt sich zu einer **souveränen AI-Plattform**, die Organisationen in die Lage versetzt, ihre Daten **vollständig unter eigener Kontrolle** in echte, nutzbare Intelligenz zu verwandeln.

Die Vision von NovaCore ist eine Welt, in der:

- KI **lokal, nachvollziehbar und auditierbar** eingesetzt wird
- Wissen nicht in Silos verschwindet, sondern strukturiert erinnert wird
- RAG-Pipelines reproduzierbar, messbar und erklärbar sind
- Agenten zuverlässig Daten erschließen, statt Blackboxes zu erzeugen
- Unternehmen und Behörden **keine Kompromisse** zwischen Innovation und Datensouveränität eingehen müssen

NovaCore versteht sich nicht als Chatbot, sondern als **Intelligence Layer** über bestehenden Daten, Systemen und Dokumenten.

> **Own your data. Master your AI.**

## 📝 Lizenz

Dieses Projekt steht unter der **GNU Affero General Public License v3 (AGPL v3)**.

### Kurzfassung
- Die Nutzung, Änderung und Weiterverbreitung ist erlaubt
- Auch die **kommerzielle Nutzung** ist zulässig
- Bei Nutzung über ein Netzwerk (z. B. als Service) **muss der Quellcode offengelegt werden**
- Änderungen am Code müssen unter derselben Lizenz veröffentlicht werden

Die AGPL v3 stellt sicher, dass Verbesserungen an NovaCore der Community erhalten bleiben und schützt das Projekt vor proprietärer Vereinnahmung.

© Adrian Lorenz
