Sterownik kotła C.O na ESP32 

Projekt sterownika pieca CO oparty na ESP32, z możliwością ustawienia harmonogramów czasowych, ręcznego sterowania przekaźnikiem oraz obsługą wielu sieci WiFi. Urządzenie synchronizuje czas z serwerem NTP i pozwala na konfigurację przez stronę WWW.

⸻

Funkcje
	•	🔌 Sterowanie przekaźnikiem (LOW-active – włączony przy stanie LOW)
	•	📅 Obsługa 2 niezależnych harmonogramów (z możliwością działania przez północ)
	•	🌍 Synchronizacja czasu przez NTP
	•	📡 Automatyczne łączenie z kilkoma sieciami WiFi (WiFiMulti)
	•	🌐 Wbudowany serwer WWW do konfiguracji i podglądu
	•	⚡ Ręczne sterowanie (Włącz / Wyłącz / Automatyczny)
	•	✅ Pamięć ustawień zapisywana w NVS (Preferences)
	•	🟢 Status przekaźnika wyświetlany na stronie (kolory, auto-odświeżanie)

⸻

Wymagania
	•	ESP32 (dowolna wersja z WiFi)
	•	Moduł przekaźnika z optoizolacja zgodny z arduino
	•	Arduino IDE lub PlatformIO
	•	Biblioteki:
	•	WiFi.h
	•	WiFiMulti.h
	•	WebServer.h
	•	Preferences.h

⸻

Podłączenie
	•	GPIO 5 → sterowanie przekaźnikiem
	•	Zasilanie modułu ESP32 i przekaźnika zgodnie z dokumentacją

⸻

Konfiguracja WiFi

W pliku .ino możesz dodać swoje sieci WiFi:
wifiMulti.addAP("Siec wifi", "haslo wifi");
wifiMulti.addAP("sieć2", "hasło2");
ESP32 spróbuje połączyć się z pierwszą dostępną siecią.

⸻

Interfejs WWW

Po uruchomieniu ESP32 wejdź w przeglądarce na adres IP wyświetlony w Serial Monitorze.

Dostępne opcje:
	•	Ustawienie harmonogramów (godzina włączenia/wyłączenia + dni tygodnia)
	•	Podgląd aktualnego czasu
	•	Stan przekaźnika (WŁĄCZONY/WYŁĄCZONY)
	•	Ręczne sterowanie:
	•	Włącz
	•	Wyłącz
	•	Automatyczny (wg harmonogramu)

⸻

Przykład działania
	•	Harmonogram 1: 10:00 – 13:00 (Pn-Pt)
	•	Harmonogram 2: 14:00 – 16:00 (Pn-Pt)
	•	Poza tymi godzinami przekaźnik jest wyłączony
	•	Możliwość ręcznego włączenia/wyłączenia niezależnie od harmonogramu
 
Autor 

Projekt przygotowany do sterowania instalacją CO, łatwy do rozbudowy (np. o MQTT, czujniki temperatury, więcej przekaźników).
