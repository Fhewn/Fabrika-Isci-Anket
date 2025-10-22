# 🏭 Fabrika Çalışan Memnuniyeti Anket Sistemi

Bu depo, **imalat ve üretim sektörlerindeki** çalışan memnuniyeti süreçlerini dijitalleştirmek, izlemek ve derinlemesine analiz etmek amacıyla tasarlanmış bir veritabanı yönetim sisteminin (DBMS) çekirdek şemasını (DDL) içermektedir.

Proje, fabrika personelinin (mavi yaka, beyaz yaka) çalışma koşulları, yönetimle iletişim ve katılım düzeylerine dair objektif veriler toplamayı ve bu verileri departman ve demografik gruplar bazında karşılaştırmalı olarak raporlamayı hedefler.

## ✨ Temel Özellikler

* **Demografik Kırılım:** Cevapların Statü (Mavi/Beyaz Yaka), Cinsiyet ve Departman bazında filtrelenmesi.
* **Katılım Takibi:** Anket giriş ve tamamlama kayıtları sayesinde gerçek zamanlı katılım oranları hesaplama.
* **Gelişmiş Analiz Altyapısı:** SQL sorguları ile departmanlar arası memnuniyet farklarını ve zaman içindeki eğilimleri kolayca belirleme.
* **SQL Server Odaklı Yapı:** Microsoft SQL Server'ın performans ve güvenlik özelliklerinden yararlanacak şekilde optimize edilmiştir.

---

## 🇹🇷 Veritabanı Şeması (DDL)

Veritabanı yapısı, **Personel Takibi**, **Soru Yönetimi** ve **Detaylı Cevap Analizi** olmak üzere üç ana fonksiyonu destekleyen 5 tablodan oluşmaktadır.

### 💾 Tablo Yapıları

| Tablo Adı | Amaç | Anahtar İlişki | Kritik Sütunlar |
| :--- | :--- | :--- | :--- |
| **Soru** | Anketin temel sorularını (İş Güvenliği, Yönetim vb.) yönetir. | `Id` (PK) | `SoruMetni`, `Kategori` |
| **Personel** | Çalışanların temel sicil ve kimlik bilgileri. | `SicilNo` (PK) | `AdSoyad` |
| **Kisi** | Anket anındaki demografik (yaş, cinsiyet) ve statü bilgileri. | `SicilId` (FK: Personel) | `Statü`, `DepartmanAdi` |
| **Secim** | Personelin sorulara verdiği detaylı cevapların depolandığı temel tablo. | `SicilId` (FK: Kisi), `SoruId` (FK: Soru) | `Cevap`, `CevapTarihi` |
| **AnketLog** | Anket süreçlerine (Giriş/Tamamlama) dair log kayıtları. | `SicilId` (FK: Personel) | `GirisTarihi`, `Durum` |

### 🔗 Örnek Analiz Senaryoları

* **Departman Memnuniyet Karşılaştırması:** `Secim` ve `Kisi` tabloları birleştirilerek, örneğin "Üretim Departmanının Ortalama Memnuniyet Skoru" ile "Lojistik Departmanının" skoru arasındaki fark kolayca hesaplanabilir.
* **Mavi Yaka vs. Beyaz Yaka Analizi:** `Kisi.Statü` sütunu üzerinden yapılan gruplama ile iki ana personel grubu arasındaki memnuniyet uçurumları tespit edilebilir.

---

## 🇬🇧 English Description: Factory Employee Satisfaction Survey System

This repository contains the core database schema (DDL) for a system designed to digitize, monitor, and conduct in-depth analysis of employee satisfaction processes within the **manufacturing and production sectors**.

### ⚙️ Database Structure

| Table Name | Purpose | Key Relations | Critical Columns |
| :--- | :--- | :--- | :--- |
| **Soru** (`Question`) | Manages core survey questions (Safety, Management, etc.). | `Id` (PK) | `SoruMetni`, `Kategori` |
| **Personel** (`Personnel`) | Basic employee registration and identity details. | `SicilNo` (PK) | `AdSoyad` |
| **Kisi** (`Person`) | Demographic (age, gender) and status information at the time of the survey. | `SicilId` (FK: Personnel) | `Statü`, `DepartmanAdi` |
| **Secim** (`Selection`) | The core table storing detailed answers given to questions. | `SicilId` (FK: Person), `SoruId` (FK: Question) | `Cevap`, `CevapTarihi` |
| **AnketLog** (`SurveyLog`) | Log records for survey processes (Entry/Completion). | `SicilId` (FK: Personnel) | `GirisTarihi`, `Durum` |

---

## 💻 Kullanılan Teknoloji / Technology Used

| Category | Technology | Description |
| :--- | :--- | :--- |
| **Database Engine** | Microsoft SQL Server (T-SQL) | Chosen for enterprise-level performance and robust integration. |
| **Schema Type** | DDL (Data Definition Language) | Definitions of tables, indexes, and constraints. |

---

## 📞 İletişim / Contact

* **Geliştirici / Developer:** [Adınız Soyadınız]
* **GitHub:** [GitHub Profil Linkiniz]
* **Proje Adı / Project Name:** Fabrika-Isci-Anket (Factory Employee Survey)

*Bu tasarım, fabrika ortamındaki memnuniyet ölçüm ihtiyaçlarına özgü olarak hazırlanmıştır.*
