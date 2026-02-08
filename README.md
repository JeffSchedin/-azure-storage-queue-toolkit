<p align="center">
  <img src="icon.png" alt="Azure Storage Queue Toolkit" width="128" height="128">
</p>

<h1 align="center">Azure Storage Queue Toolkit</h1>

<p align="center">
  <strong>The most powerful Azure Storage Queue tool for VS Code.</strong><br>
  Browse, inspect, and manage every message in your queues — not just the first 32.
</p>

<p align="center">
  <a href="https://marketplace.visualstudio.com/items?itemName=JeffSchedin.azure-storage-queue-toolkit">
    <img src="https://img.shields.io/visual-studio-marketplace/v/JeffSchedin.azure-storage-queue-toolkit?label=VS%20Code%20Marketplace&color=0078D4" alt="Marketplace Version">
  </a>
  <a href="https://marketplace.visualstudio.com/items?itemName=JeffSchedin.azure-storage-queue-toolkit">
    <img src="https://img.shields.io/visual-studio-marketplace/i/JeffSchedin.azure-storage-queue-toolkit?color=0078D4" alt="Installs">
  </a>
  <a href="https://marketplace.visualstudio.com/items?itemName=JeffSchedin.azure-storage-queue-toolkit">
    <img src="https://img.shields.io/visual-studio-marketplace/r/JeffSchedin.azure-storage-queue-toolkit?color=0078D4" alt="Rating">
  </a>
</p>

<p align="center">
  <a href="https://marketplace.visualstudio.com/items?itemName=JeffSchedin.azure-storage-queue-toolkit">Install from Marketplace</a> &bull;
  <a href="#features">Features</a> &bull;
  <a href="#getting-started">Getting Started</a> &bull;
  <a href="https://github.com/JeffSchedin/azure-storage-queue-toolkit/issues">Report Issue</a>
</p>

---

## The Problem

Azure's built-in tools limit queue peek to **32 messages**. That's a hard API limit. If your queue has thousands of messages and you need to inspect, debug, or move them — you're stuck writing scripts or guessing.

## The Solution

**Azure Storage Queue Toolkit** breaks that limit with **Deep Peek** — a safe two-phase scanning approach that lets you see every message in your queue, search through them, and take action. All from VS Code.

---

## Features

### Deep Peek — See All Your Messages
Azure's API caps peek at 32 messages. Deep Peek scans your entire queue: messages are temporarily received, collected, then immediately restored. Full visibility without losing a single message.

### Bulk Operations at Scale
Select and **copy**, **move**, or **delete** messages across queues — with no 32-message ceiling. Full queue scanning means you can operate on hundreds or thousands of messages at once.

### Generate Test Messages
Create realistic test data directly in your queues. Choose from **JSON**, **plain text**, or **XML** formats with randomized sample data. Generate up to 1,000 messages in one shot.

### Blob Storage Built In
Browse containers, upload and download files, preview content (text, JSON, images), manage metadata, and generate SAS tokens. Full blob management without leaving VS Code.

### Production-Safe
Every destructive operation shows a clear warning explaining what will happen — visibility timeouts, message invisibility windows, and operation scope — before you confirm.

---

## Complete Feature List

### Queue Management
- Connect multiple Azure Storage accounts
- Create and delete queues
- View queue properties and metadata
- Queue analytics dashboard with health scores
- Auto-refresh at configurable intervals
- Favorites for quick access

### Message Operations
| Operation | Description |
|-----------|-------------|
| **Peek Messages** | View up to 32 messages (Azure API limit) |
| **Deep Peek** | Scan ALL messages in a queue — no limit |
| **Send Message** | Send new messages to any queue |
| **Receive / Dequeue** | Receive messages with visibility control |
| **Delete** | Remove individual messages |
| **Clear Queue** | Delete all messages at once |
| **Export to JSON** | Save messages to a file |
| **Import from JSON** | Load messages from a file |
| **Generate Test Messages** | Create bulk test data (JSON, text, XML) |
| **Bulk Delete** | Select and delete multiple messages |
| **Move Messages** | Move selected messages to another queue |
| **Copy Messages** | Copy selected messages to another queue |

### Blob Storage
- Browse containers with virtual folder navigation
- Upload and download blobs
- Preview blob content (text, JSON, images, hex for binary)
- Container management (create, delete, properties, metadata)
- Bulk delete blobs
- Generate SAS tokens for containers and individual blobs
- Copy blob URLs

### Security
- SAS token generation for queues and blobs
- Access policy management
- Connection strings stored in VS Code's encrypted secure storage
- No telemetry or data collection
- All Azure communication is direct from your machine

---

## Getting Started

### Requirements
- VS Code 1.85+
- Python 3.9+
- An Azure Storage account connection string

### Install

1. **Install** from the [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=JeffSchedin.azure-storage-queue-toolkit)
2. **Click the toolkit icon** in the Activity Bar (left sidebar)
3. **Click +** to add your Azure Storage account
4. **Paste your connection string** (Azure Portal > Storage Account > Access Keys)
5. **Explore** — expand your account to see Queues and Blob Containers

> Your connection string is stored securely in VS Code's encrypted storage and never leaves your machine.

---

## How Deep Peek Works

Azure Queue Storage's peek API is hard-limited to 32 messages per call. Deep Peek works around this:

1. **Receives** messages in batches of 32 (they become temporarily invisible)
2. **Collects** all messages with deduplication by message ID
3. **Restores** visibility immediately so no messages are lost

Messages are invisible for up to 5 minutes during scanning as a safety buffer, but are restored as soon as collection completes. A warning dialog explains the process before you confirm.

---

## Configuration

| Setting | Description | Default |
|---------|-------------|---------|
| `azureQueueExplorer.pythonPath` | Path to Python executable | Auto-detect |
| `azureQueueExplorer.serverPort` | Backend server port | 5789 |
| `azureQueueExplorer.maxMessagesToDisplay` | Default messages to peek | 32 |
| `azureQueueExplorer.autoRefreshInterval` | Refresh interval in seconds | 30 |

---

## Privacy

- No telemetry, analytics, or data collection of any kind
- No external server communication
- The Python backend runs locally on `127.0.0.1`
- Connection strings are encrypted in VS Code's secure storage

---

## Feedback

Found a bug or have a feature request? [Open an issue](https://github.com/JeffSchedin/azure-storage-queue-toolkit/issues) — I read every one.

---

<p align="center">
  <strong>Azure Storage Queue Toolkit</strong> — Built for developers who need more than 32 messages.
</p>
