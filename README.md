# YKS Fight Sorular

YKS Fight uygulaması için soru ve bilgi kartları veritabanı.

## Dosya Yapısı

```
yksfightsorular/
├── questions.json        # Online maç soruları (TYT + AYT)
├── studyCards.json       # Ders çalışma kartları (flashcards)
└── README.md
```

## questions.json

Online maçlar ve günlük sorular için kullanılan ana soru havuzu.

### Yapı

```json
{
  "version": "1.0.0",
  "lastUpdated": "2026-03-05",
  "questions": {
    "tyt": {
      "turkce": [...],
      "matematik": [...],
      "fizik": [...],
      "kimya": [...],
      "biyoloji": [...],
      "tarih": [...],
      "cografya": [...],
      "felsefe": [...]
    },
    "ayt": {
      "matematik": [...],
      "fizik": [...],
      "kimya": [...],
      "biyoloji": [...],
      "edebiyat": [...],
      "tarih": [...],
      "cografya": [...]
    }
  }
}
```

### Soru Formatı

```json
{
  "id": "tyt_mat_1",
  "subject": "Matematik",
  "difficulty": "easy",
  "format": "multiple_choice",
  "text": "Soru metni?",
  "options": [
    { "id": "a", "text": "A şıkkı", "isCorrect": false },
    { "id": "b", "text": "B şıkkı", "isCorrect": true },
    { "id": "c", "text": "C şıkkı", "isCorrect": false },
    { "id": "d", "text": "D şıkkı", "isCorrect": false }
  ]
}
```

### Zorluk Seviyeleri
- `easy` - Kolay
- `medium` - Orta
- `hard` - Zor

## studyCards.json

Ders kartları (flashcard) sistemi için kullanılan içerik.

### Yapı

```json
{
  "version": "1.0.0",
  "lastUpdated": "2026-03-05",
  "studyCards": [...]
}
```

### Kart Formatı

```json
{
  "id": "sc_mat_1",
  "subject": "Matematik",
  "topic": "Türev",
  "front": "Ön yüz (soru)",
  "back": "Arka yüz (cevap ve açıklama)"
}
```

### Mevcut Konular
- **Matematik** (10 kart): Türev, İntegral, Limit, Logaritma, Trigonometri, vb.
- **Fizik** (11 kart): Newton Yasaları, Elektrik, Enerji, Işık, vb.
- **Kimya** (12 kart): Periyodik Tablo, Asit-Baz, Mol, Gazlar, vb.
- **Biyoloji** (11 kart): Hücre, DNA, Fotosentez, Sindirim, vb.
- **Tarih** (10 kart): Osmanlı, Cumhuriyet, Kurtuluş Savaşı, vb.

## Kullanım

### React Native Uygulamasında

```typescript
// .env dosyasında
QUESTIONS_URL=https://raw.githubusercontent.com/serkandevv/yksfightsorular/main/questions.json

// QuestionService ile fetch
const response = await fetch(QUESTIONS_URL);
const data = await response.json();
```

### Raw URL'ler

- **questions.json**: `https://raw.githubusercontent.com/serkandevv/yksfightsorular/main/questions.json`
- **studyCards.json**: `https://raw.githubusercontent.com/serkandevv/yksfightsorular/main/studyCards.json`

## Soru Ekleme

1. İlgili JSON dosyasını düzenleyin
2. Unique bir `id` verin (örn: `tyt_mat_99`)
3. Commit ve push yapın

## İstatistikler

| Kategori | Soru Sayısı |
|----------|-------------|
| TYT Türkçe | 8 |
| TYT Matematik | 8 |
| TYT Fizik | 4 |
| TYT Kimya | 6 |
| TYT Biyoloji | 5 |
| TYT Tarih | 5 |
| AYT Edebiyat | 7 |
| **Toplam Soru** | **43** |
| **Ders Kartı** | **54** |

## Lisans

Bu içerik YKS Fight uygulaması için özel olarak hazırlanmıştır.
