# 🎬 QUILL : Universal Media Downloader & Extractor

A **modern, full‑stack YouTube video downloader and streamer** built with **FastAPI** and **Next.js**.
It supports **high‑quality video downloads (including 4K when available)**, **real‑time progress tracking**, and **instant browser playback via streaming** — all with a clean, responsive UI.

This project is designed with **clarity, correctness, and extensibility** in mind, making it suitable for learning, showcasing on a resume, or evolving into a production‑grade tool.

---

## ✨ Features

- 🎥 **Stream videos instantly** (no waiting for full download)
- ⬇️ **Download videos with real‑time progress updates** (SSE‑based)
- 🧠 **Smart file naming** — downloaded files include:
  - Original YouTube title
  - Selected video quality / format

- 📊 **Smooth progress bar** (no freezing or fake jumps)
- 🎞️ **Automatic audio + video merging**
- 🚀 **FastAPI backend** with clean separation of concerns
- 💻 **Next.js frontend** with modern UX

---

## 🏗️ Project Architecture

```
app/
├── main.py          # FastAPI app & API routes
├── extractor.py    # Video metadata extraction (yt-dlp)
├── downloader.py   # Streaming & download logic with progress
├── utils.py        # Shared helpers
├── models.py       # Pydantic models

frontend/
└── app/            # Next.js App Router

downloads/      # Downloaded files
```

This strict structure was intentionally preserved to keep the backend **maintainable and scalable**.

---

## 🧰 Tech Stack

### Backend

- **Python**
- **FastAPI**
- **yt-dlp** (media extraction & download)
- **FFmpeg** (stream‑friendly MP4 generation)
- **Server‑Sent Events (SSE)** for progress updates

### Frontend

- **Next.js (App Router)**
- **React**
- **TypeScript**
- **Tailwind CSS**

---

## ⚙️ Installation & Setup

### Prerequisites

Make sure you have the following installed:

- Python 3.9+
- Node.js 18+
- FFmpeg
- yt-dlp

---

### Backend Setup

```bash
python -m venv venv
source venv/bin/activate  # Linux / macOS
venv\Scripts\activate     # Windows

pip install -r requirements.txt

uvicorn app.main:app --reload
```

Backend will run on:

```
http://localhost:8000
```

---

### Frontend Setup

```bash
cd frontend
npm install
npm run dev
```

Frontend will run on:

```
http://localhost:3000
```

---

## 📥 Download Flow (How It Works)

1. User selects video quality
2. Backend starts yt-dlp with a **predefined final filename**
3. Progress is streamed via **Server‑Sent Events**
4. On completion, frontend downloads the exact file

This avoids race conditions, renaming bugs, and file‑not‑found errors.

---

## 🎞️ Streaming Flow

- yt-dlp pipes raw media
- FFmpeg converts it to **fragmented MP4**
- Browser starts playing instantly (no full download required)

---

## 🚧 Limitations

- Depends on YouTube’s available formats
- 4K downloads require separate audio/video streams

---

## ⚠️ Disclaimer

This project is for **educational purposes only**.
Users are responsible for complying with YouTube’s Terms of Service and local laws.

---

## 👤 Author

**Sairaj Mestry**
Backend & Full‑Stack Developer

---

⭐ If you find this project useful, consider starring the repository!
