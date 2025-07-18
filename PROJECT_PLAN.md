# PROJECT_PLAN.md

## 1. Proje Başlığı
**Türkçe Kitap Üzerinden Konuşan Yapay Zeka Asistanı (LLM + RAG + TTS)**

## 2. Proje Amacı
Bu projenin amacı, yapay zeka teknolojilerini (LLM, RAG, embedding, TTS gibi) kullanarak Türkçe içerik tabanlı bir bilgi asistanı geliştirmektir.

## 3. Proje Kapsamı

### Aşama 1: Metin Tabanlı Yapay Zeka Chatbot
- Kitap PDF/epub metninin işlenmesi
- Embedding + RAG altyapısı
- Türkçe LLM modeli
- Web tabanlı frontend

### Aşama 2: Sesli Yanıt ve Mikrofon ile Soru Sorma
- Web üzerinden sesli soru alma
- TTS ile Türkçe sesli yanıt üretimi
- Konuşma geçmişi yönetimi

## 4. Teknolojiler
- **Backend:** Python (FastAPI) veya ASP.NET Core Web API
- **LLM/AI:** HuggingFace Transformers, LangChain, FAISS
- **Embedding:** sentence-transformers/paraphrase-multilingual-mpnet-base-v2
- **TTS:** Google Cloud TTS / Coqui TTS / gTTS
- **Speech-to-Text:** OpenAI Whisper / Vosk
- **Frontend:** ReactJS / VueJS / ASP.NET Blazor
- **Veri Saklama:** SQLite / PostgreSQL
- **Hosting:** Lokal / GCP / Azure

## 5. Mimari Şema
Bileşenler:
- BookPreprocessor
- Embedder
- VectorStore
- LLMResponder
- TTSModule
- SpeechToTextModule
- FrontendUI

## 6. Modüller
Ayrı dosyalar halinde organize edilmiştir. Backend içerisinde aşağıdaki dosyalar yer alır:
- `embeddings.py`, `vector_store.py`, `llm_responder.py`, `tts_engine.py`, `stt_engine.py`, `book_loader.py`, `routes.py`, `main.py`

## 7. Zaman Planı
- **1. Hafta:** Kitap verisi alma, PDF parser
- **2. Hafta:** Embedding ve vektör veritabanı
- **3. Hafta:** LLM entegrasyonu
- **4. Hafta:** Web arayüzü
- **5. Hafta:** Sesli giriş ve çıkış
- **6. Hafta:** Test, dokümantasyon ve sunum

## 8. Kullanım Senaryosu
1. Kullanıcı arayüze girer.
2. Klavye veya mikrofonla soru sorar.
3. Sistem, ilgili metni bulur ve yanıt üretir.
4. Gerekirse TTS ile yanıt seslendirilir.

## 9. Öğrenme Hedefleri
- Transformers kullanımı
- RAG ve vector search
- Türkçe dil modeli uygulamaları
- Text-to-speech ve speech-to-text
- API geliştirme
- Frontend-backend entegrasyonu

## 10. Gelecek Geliştirme Fikirleri
- Çok dilli destek
- Çok kitaplı sohbet
- Oturum takibi
- Mobil uyarlama

## 11. GitHub Repo Yapısı
```
llm-turkish-book-assistant/
├── backend/
│   ├── app/
│   │   ├── api/routes.py
│   │   ├── core/ [embeddings.py, vector_store.py, ...]
│   │   └── main.py
│   └── requirements.txt
├── frontend/
│   ├── src/components/[ChatBox.vue, AudioRecorder.vue]
│   ├── App.vue, main.js
│   └── package.json
├── data/raw/, processed/
├── notebooks/test_embeddings.ipynb
├── scripts/prepare_dataset.py
├── .env.example, .gitignore, README.md, LICENSE
└── docker-compose.yml
```

## 12. Veritabanı Şeması (SQL)
### Books
- id, title, author, language, source_file, created_at

### Embeddings
- id, book_id, segment_text, vector, chunk_index, created_at

### Users (opsiyonel)
- id, username, email, created_at

### ChatSessions
- id, user_id, book_id, started_at, ended_at

### Messages
- id, session_id, role, message_text, timestamp, source_chunks

## 13. Örnek API'ler
- `POST /api/books/upload`
- `GET /api/books`
- `POST /api/books/{book_id}/embed`
- `POST /api/chat/ask`
- `POST /api/chat/ask-voice`
- `POST /api/tts`
- `GET /api/sessions/{session_id}/messages`
- `GET /api/status`

## 14. Authentication (opsiyonel)
JWT tabanlı giriş:
- `POST /api/auth/login`
- `POST /api/auth/register`
- `GET /api/auth/me`

---
Bu dosya, projeyi derinlemesine anlayabilmek için teknik detayları içeren başlıca referans belgedir.
