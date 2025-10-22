# Fabrika-Isci-Anket

🏭 Fabrika Çalışan Memnuniyeti Anket Sistemi (Fabrika-Isci-Anket)
Bu depo, imalat ve üretim sektörlerine özel olarak tasarlanmış, çalışan memnuniyeti süreçlerini dijitalleştiren ve analiz eden bir veritabanı yönetim sisteminin (DBMS) çekirdek şemasını (DDL) sunmaktadır. Proje, fabrika personelinin (mavi yaka, beyaz yaka) objektif ve ayrıştırılmış verilerle izlenmesini sağlar.

🎯 Projenin Amacı ve Odak Noktası
Proje, çalışanların çalışma koşulları, iç iletişim, yönetim kalitesi ve katılım düzeyleri hakkındaki görüşlerini toplayarak; yönetim kararlarına ışık tutacak, departman ve demografik bazlı analitik çıktıları sağlamayı hedefler.

✨ Temel Yetenekler ve Analitik Güç

Kategori	Özellik	Açıklama
Demografik Kırılım	Statü ve Departman Analizi	Cevaplar; Mavi Yaka/Beyaz Yaka, Cinsiyet ve Üretim/Lojistik gibi departmanlar arasında kolayca filtrelenebilir.
Katılım İzleme	Anket Logları (AnketLog)	Gerçek zamanlı olarak katılım oranlarını, giriş/tamamlama başarılarını Sicil No bazında takip etme imkanı.
Performans	SQL Server Altyapısı	Veri bütünlüğünü (FK) ve yüksek performanslı sorgulamayı destekleyen Microsoft SQL Server yapısı.
Karar Desteği	Karşılaştırmalı Skorlar	Departmanlar arası memnuniyet farklarını ve zaman içindeki eğilimleri hızla tespit etme yeteneği.
🇹🇷 Veritabanı Şeması (DDL)
Şema, Personel Takibi, Soru Yönetimi ve Detaylı Cevap Analizi olmak üzere 5 tablo ile veri akışını yönetir.

📊 Tablo Yapısı ve Fonksiyonları

Tablo Adı	Fonksiyonel Açıklama	Anahtar Bilgi	Kritik Bağlantılar (FK)
Soru	Anketin içeriğini (Sorular ve Kategorileri) barındırır.	Id (PK)	-
Personel	Fabrika çalışanlarının temel kimlik (Sicil) ve iletişim bilgileri.	SicilNo (PK)	-
Kisi	Personelin anket anındaki demografik (Yaş, Cinsiyet) ve organizasyonel (Statü, DepartmanAdi) bilgileri.	SicilId (PK, FK: Personel)	1-1 ilişki (Personel ile)
Secim	Memnuniyet Skorlarının Temeli. Personelin verdiği tüm cevapları (Cevap, CevapTarihi) kaydeder.	Id (PK)	Kisi.SicilId, Soru.Id
AnketLog	Anket katılım geçmişi ve durumu (Giriş Başarılı, Tamamlandı) takibi.	Id (PK)	Personel.SicilNo
🇬🇧 English Description: Database Schema
This core schema (DDL) is built for Microsoft SQL Server, focusing on robust data management for analyzing factory employee satisfaction.

⚙️ Database Structure and Functions

Table Name	Functional Description	Key Information	Critical Relations (FK)
Soru (Question)	Stores the survey questions and their categories.	Id (PK)	-
Personel (Personnel)	Contains basic personnel ID (SicilNo) and identity details.	SicilNo (PK)	-
Kisi (Person)	Stores personnel demographics (Age, Gender) and status (Statü, DepartmanAdi) at the time of the survey.	SicilId (PK, FK: Personnel)	1-1 relation (with Personnel)
Secim (Selection)	The core of satisfaction scores. Records all individual responses (Cevap, CevapTarihi).	Id (PK)	Kisi.SicilId, Soru.Id
AnketLog (SurveyLog)	Tracks survey participation history and status (Entry Success, Completed).	Id (PK)	Personnel.SicilNo
💻 Teknolojiler / Technologies

Kategori	Teknoloji	Not / Comment
Veritabanı Motoru	Microsoft SQL Server (T-SQL)	Enterprise-grade performance.
Dil	DDL (Data Definition Language)	Schema creation and constraints.
✉️ İletişim / Contact

Geliştirici / Developer: [Adınız Soyadınız]

GitHub Profil: [GitHub Profil Linkiniz]

Proje Adı: Fabrika-Isci-Anket

Bu veritabanı mimarisi, fabrika ortamındaki memnuniyet süreçlerini bilimsel ve analitik bir yaklaşımla yönetmek üzere tasarlanmıştır.
