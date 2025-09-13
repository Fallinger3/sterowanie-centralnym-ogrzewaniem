Sterownik C.O na ESP32

Projekt sterownika pieca CO oparty na ESP32, z możliwością ustawienia harmonogramów czasowych, ręcznego sterowania przekaźnikiem oraz obsługą wielu sieci WiFi. Urządzenie synchronizuje czas z serwerem NTP i pozwala na konfigurację przez stronę WWW.

Działa zarówno w trybie klienta WiFi, jak i w trybie Access Point (AP), gdy nie ma dostępu do sieci.

⸻

Funkcje
	•	🔌 Sterowanie przekaźnikiem (LOW-active – włączony przy stanie LOW)
	•	📅 Obsługa 2 niezależnych harmonogramów (także przez północ, np. 23:00–05:00)
	•	🌍 Synchronizacja czasu przez NTP
	•	📡 Automatyczne łączenie z wieloma sieciami WiFi (WiFiMulti)
	•	📶 Tryb AP (Access Point), gdy ESP32 nie połączy się z WiFi
	•	SSID: ESP32-CO
	•	Hasło: 12345678
	•	Strona dostępna pod adresem: http://192.168.4.1
	•	🌐 Wbudowany serwer WWW do konfiguracji i podglądu
	•	⚡ Ręczne sterowanie (Włącz / Wyłącz / Automatyczny)
	•	✅ Pamięć ustawień zapisywana w NVS (Preferences)
	•	🟢 Strona WWW z automatycznym odświeżaniem co 1 minutę

⸻

Wymagania
	•	ESP32 (dowolna wersja z WiFi)
	•	Moduł przekaźnika aktywny w stanie LOW
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
wifiMulti.addAP("router name", "password");
wifiMulti.addAP("router name", "password");

ESP32 spróbuje połączyć się z pierwszą dostępną siecią.

⸻

Tryb Access Point (offline)

Jeśli ESP32 nie połączy się z żadną siecią WiFi w ciągu 30 sekund:
	•	Uruchomi własną sieć WiFi:
	•	SSID: ESP32-CO
	•	Hasło: 12345678
	•	Aby się połączyć:
	1.	Połącz się telefonem/PC z siecią ESP32-CO
	2.	W przeglądarce wejdź na http://192.168.4.1

⸻

Interfejs WWW

Po uruchomieniu ESP32 wejdź w przeglądarce na adres IP wyświetlony w Serial Monitorze (np. http://192.168.1.XX) lub http://192.168.4.1 w trybie AP.

Dostępne opcje:
	•	Ustawienie harmonogramów (godzina włączenia/wyłączenia + dni tygodnia)
	•	Podgląd aktualnego czasu (synchronizowanego przez NTP)
	•	Stan przekaźnika (WŁĄCZONY/WYŁĄCZONY)
	•	Ręczne sterowanie:
	•	Włącz
	•	Wyłącz
	•	Automatyczny (wg harmonogramu)

⸻

Screenshot (przykład strony WWW)

(Tu możesz dodać zrzut ekranu po wgraniu kodu)

⸻

Autor

Projekt przygotowany do sterowania instalacją C.O, łatwy do rozbudowy (np. o MQTT, czujniki temperatury, więcej przekaźników).
