# Santral-C Masaüstü Sürümleri

Santral-C Windows masaüstü uygulaması ve çağrı kontrol aracının resmi dağıtım deposu.

[English](README.md) | Türkçe

## İndirme Bağlantıları

| Paket | Tür | Açıklama |
| :--- | :--- | :--- |
| [Santral-C Mini Widget Setup 1.0.0.exe](https://github.com/toprakgureli/santral-desktop-releases/releases/download/v1.0.0/Santral-C-Mini-Widget-Setup-1.0.0.exe) | NSIS Kurulum Paketi | Otomatik güncelleme destekli standart Windows kurulum dosyası. |
| [Santral-C-Widget-Portable.exe](https://github.com/toprakgureli/santral-desktop-releases/releases/download/v1.0.0/Santral-C-Widget-Portable.exe) | Taşınabilir Binary | Kurulum gerektirmeyen, doğrudan çalışan taşınabilir sürüm. |

Otomatik güncelleme doğrulama dosyası: [`latest.yml`](https://github.com/toprakgureli/santral-desktop-releases/releases/download/v1.0.0/latest.yml)

## Teknik Özet

Santral-C Masaüstü, santral yönetim arayüzünü ve yüzen mini softphone aracını Windows için tek bir Electron istemcisinde birleştirir.

- **Yerleşik WebRTC Entegrasyonu:** SIP sinyalleşmesi, dahili kaydı ve ses trafiği doğrudan masaüstü sürecinde işlenir. Harici tarayıcı eklentisi gerektirmez.
- **Pencere ve Görev Çubuğu Yönetimi:** Mini çağrı aracı görev çubuğunda ayrı bir pencere veya simge oluşturmaz. Ekranda her zaman üstte kalabilir; kapatma ve simge durumuna küçültme işlemleri bildirim alanı (tepsi) üzerinden yönetilir.
- **Otomatik Güncelleme:** Kurulum paketi ile yüklenen sürümler bu depoyu kontrol eder; yeni sürüm çıktığında kullanıcı onayıyla arka planda indirilir ve güncellenir.
- **Tema Uyumu:** Açılışta beyaz parlama yapmaması için sistemin koyu/açık temasını okur; panel içindeki tema değişikliklerine (`dark`, `midnight`, `forest`, `matte`, `sand`, `crimson`, `light`) anında uyum sağlar.

## Sistem Gereksinimleri

- İşletim Sistemi: Windows 10 (sürüm 1809 veya üstü), Windows 11
- Mimari: x64
- Donanım: Çalışır durumda mikrofon ve ses çıkış cihazı
- Ağ Erişimi: Panel sunucusuna ve SIP uç noktalarına giden HTTPS ve WebSocket bağlantısı

## Yapılandırma

Varsayılan panel adresi uygulamanın içine gömülüdür. Farklı bir sunucu adresi tanımlamak için `%AppData%\santralc-desktop-widget\widget-config.json` dosyasını düzenleyebilirsiniz:

```json
{
  "panelUrl": "https://cm.toprakgureli.com"
}
```

Ayrıca uygulama başlatılmadan önce `SANTRAL_PANEL_URL` ortam değişkeni verilerek de adres tanımlanabilir.
