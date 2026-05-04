# 🤖 Autonomiczne Ramię Robota (Wizja i Sterowanie w Pythonie)

[![Raspberry Pi](https://img.shields.io/badge/-Raspberry_Pi-C51A4A?logo=Raspberry-Pi&logoColor=white)]()
[![Python](https://img.shields.io/badge/Python-3.x-blue.svg)](https://www.python.org/)
[![Hardware](https://img.shields.io/badge/Hardware-PCA9685_%7C_ATX-green.svg)]()

Ten projekt to w pełni funkcjonalne ramię robota sterowane za pomocą gestów i ruchu przechwytywanego przez kamerę w czasie rzeczywistym. Cały system został zaprojektowany jako **urządzenie bezobsługowe (standalone)** działające na Raspberry Pi. Zarówno analiza obrazu, jak i niskopoziomowe sterowanie sprzętem zostały zrealizowane w 100% w języku Python.

## ✨ Główne cechy projektu

* **🍓 W pełni autonomiczne (Standalone):** Całość oprogramowania działa bezpośrednio na Raspberry Pi. Projekt działa bezobsługowo – system wstaje automatycznie po podłączeniu zasilania.
* **👀 Sterowanie wizyjne:** Skrypt w Pythonie obsługuje kamerę, śledzi ruch w przestrzeni i natychmiast tłumaczy go na docelowe pozycje ramienia.
* **⚙️ Kontrola sprzętu (Python + PCA9685):** Logika ramienia oraz sterowanie serwomechanizmami poprzez magistralę I2C do płytki PCA9685 są realizowane natywnie za pomocą skryptów w Pythonie.
* **⚡ Niestandardowy system zasilania:** Aby sprostać dużemu zapotrzebowaniu na prąd przez serwomechanizmy, do zasilania układu wykorzystano **zmodyfikowany zasilacz komputerowy (ATX)**. Napięcie trafiające do serw jest precyzyjnie regulowane za pomocą **przetwornicy step-down**, co zapewnia stabilną i bezpieczną pracę pod obciążeniem.

---

## 📸 Historia budowy (Galeria)

Projekt ewoluował od prototypu na biurku do finalnego, autonomicznego urządzenia z potężnym zasilaniem.

*1. Składanie mechaniki. | 2. Integracja Raspberry Pi, przetwornicy i zasilacza ATX. | 3. Gotowy system.*

---

## 🛠️ Architektura Sprzętowa

Sercem układu jest **Raspberry Pi**, które działa jako jednostka centralna i przetwarza wszystko w ramach jednego spójnego środowiska (Python):

1. **Kamera USB/CSI** stale rejestruje obraz.
2. **Główny skrypt Python** równolegle analizuje obraz i wylicza docelowe kąty obrotu dla każdego z przegubów ramienia.
     Skrypt wysyła polecenia po szynie **I2C** bezpośrednio do płytki **PCA9685**.
4. **Zasilanie:** 
   * Zasilacz komputerowy dostarcza duży prąd do układu.
   * Przetwornica napięcia dba o obniżenie i stabilizację napięcia trafiającego bezpośrednio do serwomechanizmów (chroniąc Raspberry Pi i płytkę PCA).
5. Płytka PCA generuje sygnały PWM sterujące poszczególnymi serwami ramienia.
