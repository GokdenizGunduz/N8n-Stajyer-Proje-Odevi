# N8n-Stajyer-Proje-Odevi

AI İçerik Üretici – n8n Workflow Dokümantasyonu 

**Kurulum**

1- n8n hesabı açılır.

2- Workflow -> Import → JSON dosyası içe aktarılır.

3- Notion → AI İçerikler ve AI Logs database’leri oluşturulur.

4- Notion Integration oluşturulur → Full access verilir.

5- Bu integration her iki database’e de share edilir.

6- n8n’de Notion credentials içine Notion API anahtarı eklenir.

7- Eğer OpenAI kullanılacaksa → OpenAI API key cred içine eklenir.


**Çalıştırma**

1- Workflow aktif edilir.

2- Webhook URL alınır. (n8n → Webhook node → Production URL)

3- POST isteği şu formatta gönderilir:
{
  "topic": "Yapay zeka nedir?",
  "contentType": "Blog"
}

4- AI tarafından üretilen içerik → Notion’daki AI İçerikler tablosuna kaydedilir.

5- Log → AI Logs tablosuna yazılır.

**Yapı**

Webhook: Kullanıcıdan topic + contentType alır.

Message a model: OpenAI ile içerik üretir.

Create Content: Üretilen içeriği Notion’a kaydeder.

Create Log: Log kaydı açar.
