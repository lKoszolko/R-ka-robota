🤖 Smart Robotic Hand Controller
Status Tech AI

📝 O Projekcie
Zaawansowany system sterowania robotyczną dłonią w czasie rzeczywistym, łączący sztuczną inteligencję z inżynierią sterowania. Projekt umożliwia bezdotykowe sterowanie fizycznym manipulatorem poprzez mapowanie ruchów ludzkiej dłoni na sygnały sterujące serwomechanizmami.

🛠️ Stos Technologiczny (Tech Stack)
Python 3.x: OpenCV & MediaPipe – odpowiedzialne za tracking 21 punktów dłoni i analizę gestów.
LabVIEW 2025: Centrum dowodzenia – odbiór danych UDP, parsująca logika sterowania i GUI.
LINX Toolkit: Interfejs komunikacyjny między LabVIEW a mikrokontrolerem.
Hardware: Arduino + Serwomechanizmy (sterowanie PWM).
✨ Główne Funkcje
Precyzyjny Hand Tracking: Detekcja zgięcia 5 palców oraz rotacji nadgarstka (Yaw).
Komunikacja UDP: Błyskawiczny przesył danych między modułem wizyjnym (Python) a sterownikiem (LabVIEW) na porcie 5010.
Filtrowanie Sygnału: Stabilizacja ruchu za pomocą filtrów EMA (Exponential Moving Average) oraz filtrów medianowych, eliminujących drgania.
Bezpieczne Mapowanie: Przeliczanie kątów na sygnał Duty Cycle według precyzyjnego wzoru: 
D
u
t
y
C
y
c
l
e
=
(
A
n
g
l
e
3600
)
+
0.05
Gesture Recognition: System rozpoznaje unikalne ID gestów, co pozwala na automatyczne wyzwalanie sekwencji ruchowych.
🚀 Jak to uruchomić?
Firmware: Wgraj oprogramowanie LINX na Arduino.
AI Module: Uruchom skrypt main.py w folderze Kod, aby zainicjować kamerę i tracking.
Control: Otwórz arduinoTest.vi w LabVIEW, wybierz port COM i uruchom program.
📂 Zawartość Projektu
Kod – Kompletna logika sterująca (Python & LabVIEW).
REKA ROBOTA – Pliki projektowe dłoni.
ADAPTER / PRZEDRAMIE – Elementy konstrukcyjne do druku/montażu.
👥 Autor
Adam Jastrzębski
Łukasz Koszołko
