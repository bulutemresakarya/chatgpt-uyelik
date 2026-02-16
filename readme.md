# 🤖 Advanced Account Automation & RPA Bot

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![Playwright](https://img.shields.io/badge/Playwright-Async-green)
![GUI](https://img.shields.io/badge/GUI-Tkinter%2FBootstrap-orange)
![Status](https://img.shields.io/badge/Status-Private%20%2F%20Client%20Project-red)

## 🇹🇷 Proje Hakkında (Turkish)

Bu proje, bir freelance müşteri (Armut) için özel olarak geliştirilmiş, yüksek güvenlikli platformlarda hesap oluşturma ve doğrulama süreçlerini otomatize eden masaüstü tabanlı bir RPA yazılımıdır.

Yazılım, **Cloudflare Turnstile** ve benzeri bot koruma sistemlerini "insan benzeri davranışlar" (human-like behavior) sergileyerek aşar ve e-posta doğrulama kodlarını (OTP) webmail servislerinden otomatik olarak çeker.

### 🔒 Gizlilik ve Kod Erişimi
**Bu proje ticari bir anlaşma kapsamında geliştirilmiştir.**
Müşteri gizliliği ve fikri mülkiyet hakları gereği, kaynak kodlar (source code) halka açık olarak paylaşılmamaktadır. Bu depo, projenin teknik yetkinliklerini, kullanılan teknolojileri ve çözülen mühendislik problemlerini sergilemek amacıyla oluşturulmuştur.

### 🛠️ Teknik Özellikler ve Mimari

Proje, modern Python kütüphaneleri kullanılarak modüler bir yapıda geliştirilmiştir:

*   **Core:** Python 3.x, `asyncio` (Asenkron G/Ç yönetimi).
*   **Web Otomasyonu:** Microsoft Playwright (Async API).
*   **Anti-Detection (Gizlilik):**
    *   `playwright-stealth` kütüphanesi ile `navigator.webdriver` izlerinin silinmesi.
    *   User-Agent rotasyonu ve Canvas fingerprinting koruması.
    *   Cloudflare iframe analizi ve koordinat bazlı mouse hareket simülasyonu.
*   **GUI (Arayüz):** `ttkbootstrap` (Modern Tkinter) kullanılarak responsive ve thread-safe (donmayan) arayüz.
*   **Veri İşleme:** CSV tabanlı loglama ve işlem raporlama.
*   **Dağıtım:** PyInstaller ile tek dosya (One-File EXE) haline getirilmiş taşınabilir yapı.

### 🧩 Çözülen Zorluklar (Challenges Solved)

1.  **Cloudflare & CAPTCHA Bypass:**
    *   Bot, `iframe` içerisindeki doğrulama kutucuklarını tespit eder.
    *   Doğrudan tıklamak yerine, rastgele eğrilerle (Bezier curves benzeri) mouse hareketi yaparak "insan" onayı alır.
    
2.  **Multithreading & Async Entegrasyonu:**
    *   Arayüzün (GUI) donmasını engellemek için iş mantığı ayrı bir `Thread` içinde çalıştırılır.
    *   Thread içerisindeki Playwright işlemleri `asyncio` event loop'u üzerinden asenkron yönetilir.

3.  **Dinamik OTP Doğrulama:**
    *   Bot, kayıt esnasında gönderilen doğrulama kodunu almak için eş zamanlı olarak Webmail servisine bağlanır, gelen kutusunu dinler ve kodu Regex ile ayrıştırır.

### 📸 Ekran Görüntüleri

<img width="610" height="637" alt="screenshot_gui" src="https://github.com/user-attachments/assets/2068163c-fa3c-417f-a077-20b7bbb6af35" />

---

## 🇬🇧 Project Overview (English)

This is a desktop-based RPA (Robotic Process Automation) software developed for a freelance client to automate account creation and verification processes on high-security platforms.

The software bypasses **Cloudflare Turnstile** and similar bot protection systems by simulating human-like behavior and automatically retrieves email verification codes (OTP) from webmail services.

### 🔒 Confidentiality Notice
**This project was developed under a commercial agreement.**
Due to client confidentiality and intellectual property rights, the source code is not publicly available. This repository serves as a showcase of the technical skills, technologies used, and engineering challenges solved during development.

### 🚀 Key Technical Features

*   **Smart Waiting:** Uses dynamic element detection instead of static sleeps for maximum speed.
*   **Stealth Mode:** Removes webdriver flags to avoid detection by anti-bot systems.
*   **Robust Error Handling:** Automatically retries failed steps (up to 3 times) and logs errors to a CSV file.
*   **User-Friendly GUI:** Allows non-technical users to configure timing, input files, and monitor progress in real-time.

---
*Developed by @bulutemresakarya*


