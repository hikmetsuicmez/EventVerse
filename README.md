# EventVerse 🎉

EventVerse, etkinlik organizasyonu ve yönetimi için geliştirilmiş modern bir web uygulamasıdır. Kullanıcılar etkinlik oluşturabilir, etkinliklere katılabilir ve etkinlikleri filtreleyebilir.

## 📋 İçerik

- [Özellikler](#özellikler)
- [Teknolojiler](#teknolojiler)
- [Kurulum](#kurulum)
- [Ekran Görüntüleri](#ekran-görüntüleri)
- [API Endpoints](#api-endpoints)
- [Katkıda Bulunma](#katkıda-bulunma)

## ✨ Özellikler

### 🔐 Kullanıcı Yönetimi
- JWT tabanlı kimlik doğrulama
- Kullanıcı kaydı ve girişi
- Profil yönetimi
- Şifre güncelleme

### 📅 Etkinlik Yönetimi
- Etkinlik oluşturma ve düzenleme
- Detaylı etkinlik bilgileri (tarih, konum, kategori, vb.)
- Etkinlik katılımcı yönetimi
- Etkinlik yorumları ve değerlendirmeleri

### 🔍 Gelişmiş Filtreleme (Gelecekte eklenecek)
- Çoklu kategori seçimi
- Tarih aralığı filtreleme
- Konum bazlı filtreleme
- Fiyat ve yaş aralığı filtreleme
- Özel filtreler (ücretli/ücretsiz, yaş sınırı)

### 📱 Kullanıcı Arayüzü
- Modern ve responsive tasarım
- Kolay kullanılabilir filtreleme arayüzü
- Dinamik sayfalama
- Gerçek zamanlı bildirimler

## 🛠 Teknolojiler

### Backend
- Java 17
- Spring Boot 3.x
- Spring Security
- Spring Data JPA
- MySQL
- JWT Authentication
- Maven

### Frontend
- React.js
- Material-UI (MUI)
- Axios
- React Router
- Date-fns
- JWT Decode

## 🚀 Kurulum

### Gereksinimler
- Java 17 veya üzeri
- Node.js 14 veya üzeri
- Maven 3.6 veya üzeri
- MySQL 8.0 veya üzeri

### Backend Kurulumu

1. Repository'yi klonlayın:
```bash
git clone https://github.com/kullaniciadi/eventverse.git
cd eventverse/eventverse-backend
```

2. MySQL veritabanını oluşturun:
```sql
CREATE DATABASE eventverse;
```

3. `application.properties` dosyasını düzenleyin:
```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/eventverse
spring.datasource.username=your_username
spring.datasource.password=your_password
```

4. Uygulamayı derleyin ve çalıştırın:
```bash
mvn clean install
mvn spring-boot:run
```

### Frontend Kurulumu

1. Frontend dizinine gidin:
```bash
cd ../eventverse-frontend
```

2. Bağımlılıkları yükleyin:
```bash
npm install
```

3. Uygulamayı başlatın:
```bash
npm start
```

## 📸 Ekran Görüntüleri

[NOT: Aşağıdaki başlıkların altına ilgili ekran görüntülerini eklemeniz gerekiyor]

### Ana Sayfa
- Ana sayfa tasarımını gösteren bir ekran görüntüsü ekleyin
- Öne çıkan etkinliklerin gösterildiği bölümün ekran görüntüsü

### Etkinlik Listeleme ve Filtreleme
- Filtreleme arayüzünün ekran görüntüsü
- Etkinlik kartlarının listelendiği bölümün ekran görüntüsü
- Aktif filtrelerin gösterildiği bölümün ekran görüntüsü

### Etkinlik Detay Sayfası
- Etkinlik detaylarının gösterildiği sayfanın ekran görüntüsü
- Katılımcı listesinin gösterildiği bölümün ekran görüntüsü
- Yorum ve değerlendirme bölümünün ekran görüntüsü

### Profil Sayfası
- Kullanıcı profil sayfasının ekran görüntüsü
- Kullanıcının oluşturduğu etkinliklerin listelendiği bölümün ekran görüntüsü
- Kullanıcının katıldığı etkinliklerin listelendiği bölümün ekran görüntüsü

## 📚 API Endpoints

### Kimlik Doğrulama
```
POST /api/auth/register - Kullanıcı kaydı
POST /api/auth/login - Kullanıcı girişi
POST /api/auth/refresh - Token yenileme
GET /api/auth/test - Backend bağlantı testi
```

### Kullanıcı İşlemleri
```
GET /api/v1/users/profile - Mevcut kullanıcı bilgilerini getir
GET /api/v1/users/{userId} - Kullanıcı bilgilerini getir
PUT /api/v1/users/profile - Profil bilgilerini güncelle
DELETE /api/v1/users - Kullanıcı hesabını sil
POST /api/v1/users/profile/picture - Profil fotoğrafı yükle
```

### Etkinlik İşlemleri
```
GET /api/v1/events - Tüm etkinlikleri getir
POST /api/v1/events - Yeni etkinlik oluştur
GET /api/v1/events/{eventId} - Etkinlik detaylarını getir
POST /api/v1/events/filter - Etkinlikleri filtrele
GET /api/v1/events/my-events - Katıldığım etkinlikleri getir
GET /api/v1/events/{userId}/events - Kullanıcının katıldığı etkinlikleri getir
GET /api/v1/events/{userId}/created-events - Kullanıcının oluşturduğu etkinlikleri getir
GET /api/v1/events/my-created-events - Oluşturduğum etkinlikleri getir
GET /api/v1/events/locations - Tüm etkinlik lokasyonlarını getir
GET /api/v1/events/{eventId}/location - Etkinlik lokasyonunu getir
```

### Katılımcı İşlemleri
```
POST /api/v1/events/{eventId}/participants - Etkinliğe katıl
GET /api/v1/events/{eventId}/participants - Etkinlik katılımcılarını getir
PATCH /api/v1/events/{eventId}/participants/{participantId}/status - Katılımcı durumunu güncelle
```

### Yorum ve Yanıt İşlemleri
```
POST /api/v1/events/{eventId}/comments - Etkinliğe yorum yap
GET /api/v1/events/{eventId}/comments - Etkinlik yorumlarını getir
POST /api/v1/comments/{commentId}/reply - Yoruma yanıt ver
POST /api/replies - Yanıt oluştur
```

### Favori İşlemleri
```
POST /api/v1/favorites - Favorilere ekle
GET /api/v1/favorites - Favorileri getir
DELETE /api/v1/favorites/{favoriteId} - Favorilerden kaldır
GET /api/v1/favorites/status/{eventId} - Favori durumunu kontrol et
```

### Bildirim İşlemleri
```
GET /api/v1/notifications - Tüm bildirimleri getir
PATCH /api/v1/notifications/{notificationId}/read - Bildirimi okundu olarak işaretle
GET /api/v1/notifications/unread - Okunmamış bildirimleri getir
PATCH /api/v1/notifications/read-all - Tüm bildirimleri okundu olarak işaretle
```

## 🤝 Katkıda Bulunma

1. Bu repository'yi fork edin
2. Yeni bir branch oluşturun (`git checkout -b feature/amazing-feature`)
3. Değişikliklerinizi commit edin (`git commit -m 'feat: Add amazing feature'`)
4. Branch'inizi push edin (`git push origin feature/amazing-feature`)
5. Bir Pull Request oluşturun

---

## 📞 İletişim

Hikmet Suiçmez - [@hikmetsuicmez](https://twitter.com/hkmtscmz)

Proje Linki: [https://github.com/hikmetsuicmez/eventverse](https://github.com/hikmetsuicmez/eventverse) 
