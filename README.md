Türkçe Kitap Üzerinden Konuşan Yapay Zeka Asistanı (LLM + RAG + TTS)

Bu proje, Türkçe kitapları okuyup anlamlandırarak kullanıcıya yazılı ve sesli yanıtlar verebilen yapay zeka destekli bir asistan geliştirmeyi amaçlar. LLM, RAG, embedding ve TTS gibi teknolojiler kullanılmıştır.

 Kurulum Adımları

1. Backend:
   ```bash
   cd backend
   pip install -r requirements.txt
   ```

2. Frontend:
   ```bash
   cd frontend
   npm install
   ```

3. Ortam değişkenleri:
   - `.env` dosyasını `.env.example`'dan oluşturun.

4. Uygulamayı çalıştırmak:
   - Backend: `uvicorn main:app --reload`
   - Frontend: `npm run dev`

 Hızlı Kullanım

- `data/raw` klasörüne kitap yükleyin.
- `scripts/prepare_dataset.py` komutu ile veriyi parçalayın.
- API üzerinden veya frontend arayüzü ile kitap hakkında sorular sorun.

 Kullanılan Teknolojiler

- **Backend:** FastAPI, LangChain, HuggingFace, FAISS
- **Frontend:** Vue.js / React
- **Sesli İşlem:** Whisper, gTTS, Coqui TTS
- **Veritabanı:** PostgreSQL / SQLite

 Detaylı Proje Belgesi

Projenin kapsamlı teknik dökümanına buradan ulaşabilirsiniz:  
[PROJECT_PLAN.md](./PROJECT_PLAN.md)(https://github.com/user-attachments/files/21315437/PROJECT_PLAN.md)



