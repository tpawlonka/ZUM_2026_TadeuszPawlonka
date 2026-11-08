# Zgłoszenie tematu

Odpowiedź mieści się na jednej stronie. Projekt dotyczy nadzorowanej klasyfikacji jednolabelowej: każdy przykład ma dokładnie jedną klasę.

1. Roboczy tytuł: Klasyfikacja obrazów ze zbioru EuroSAT pod kątem rodzaju zagospodarowania przestrzennego
2. Modalność (tekst, obraz, audio albo dane multimodalne): obraz
3. Problem klasyfikacji (co jest klasą i ile jest klas): 10 klas (rodzaje zagospodarowania przestrzennego)
4. Pytanie eksperymentalne (co chcesz sprawdzić): czy niewielki foundation model specjalizujący się w klasyfikacji obrazów jest w stanie dorównać lub przewyższyć jakość klasycznego klasyfikatora obrazów, wyrażoną przy pomocy metryki macro-F1?
5. Źródło danych (link): https://github.com/phelber/eurosat
6. Przybliżona wielkość zbioru: 27000 zdjęć RGB w formacie jpg o wymiarach 64x64 pikseli
7. Lista klas i sposób oznaczenia etykiet: oznaczone kolejnymi liczbami naturalnymi
   1. AnnualCrop
   2. Forest
   3. HerbaceousVegatation
   4. Highway
   5. Industrial
   6. Pasture
   7. PermanentCrop
   8. Residential
   9. River
   10. SeaLake 
8. Licencja danych: MIT License
9. Proponowana jednostka generalizacji: zdjęcie satelitarne
10. Planowany baseline: spłaszczenie obrazu do wektora + klasyczny klasyfikator
11. Wstępny pomysł na model pretrained: DINOv2 ViT-S/14 distilled (21 mln parametrów)
12. Potencjalne ograniczenia obliczeniowe: vRAM i wydajność mojej karty graficznej (posiadam prywatnie RTX 3080 z 10 GB vRAM)
13. Dane osobowe, wrażliwe albo z ograniczeniami dostępu lub redystrybucji (tak albo nie; jeśli tak, jak je przechowasz): nie ma


