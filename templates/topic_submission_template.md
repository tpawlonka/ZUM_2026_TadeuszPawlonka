# Zgłoszenie tematu

Odpowiedź mieści się na jednej stronie. Projekt dotyczy nadzorowanej klasyfikacji jednolabelowej: każdy przykład ma dokładnie jedną klasę.

1. Roboczy tytuł: Klasyfikacja obrazów ze zbioru EuroSAT pod kątem rodzaju zagospodarowania przestrzennego
2. Modalność (tekst, obraz, audio albo dane multimodalne): obraz
3. Problem klasyfikacji (co jest klasą i ile jest klas): 10 klas (rodzaje zagospodarowania przestrzennego)
4. Pytanie eksperymentalne (co chcesz sprawdzić): czy foundation model specjalizujący się w klasyfikacji obrazów jest w stanie, po fine-tuningu, dorównać jakości tradycyjnego modelu konwolucyjnego trenowanego na wąskich danych?
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
10. Planowany baseline: convolutional neural network o następującej architekturze (albo, alternatywnie, ResNet-50)

| Warstwa | Typ       | Feature Map | Wymiar (rezultat) | Jądro | Padding | Stride |
|---------|-----------|-------------|-------------------|-------|---------|--------|
| Wejście | Obraz     | 3           | 64x64             | -     | -       | -      |
| 1       | Conv2d    | 32          | 64x64             | 3x3   | 1       | 1      |
| 2       | MaxPool2d | 32          | 32x32             | 2x2   | 0       | 2      |
| 3       | Conv2d    | 64          | 32x32             | 3x3   | 1       | 1      |
| 4       | MaxPool2d | 64          | 16x16             | 2x2   | 0       | 2      |
| 5       | Conv2d    | 128         | 16x16             | 3x3   | 1       | 1      |
| 6       | MaxPool2d | 128         | 8x8               | 2x2   | 0       | 2      |
| 7       | Flatten   | -           | 8192x1            | -     | -       | -      |
| 8       | Linear    | -           | 256x1             | -     | -       | -      |
| Wyjście | Linear    | -           | 10x1              | -     | -       | -      |
11. Wstępny pomysł na model pretrained: DINOv3 ViT-L/16 distilled albo DINOv2 ViT-B/14 distilled (oba mają 300M parametrów)
12. Potencjalne ograniczenia obliczeniowe: vRAM i wydajność mojej karty graficznej (posiadam prywatnie RTX 3080 z 10 GB vRAM)
13. Dane osobowe, wrażliwe albo z ograniczeniami dostępu lub redystrybucji (tak albo nie; jeśli tak, jak je przechowasz): nie ma


