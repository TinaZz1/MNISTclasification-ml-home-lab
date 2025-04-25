# MNISTclasification-ml-home-lab

## Opis ##

Projekt składa się z dwóch etapów:  
  1 - zbudowania najmniejszej możliwej sieci neuronowej, która osiągnie co najmniej 95% dokładności danych testowych.  
  2 - zmniejszenia liczby poziomów szarości obrazów MNIST z 256 na 16.


Projekt był wykonywany w celach edukacyjnych oraz jako element uzupełniający portfolio.


## Środowiska ##

- **Google Colab**
- **Visual Studio Code**


## Narzędzia i Biblioteki ##

- **Python 3.13.1**
- **TensorFlow**
- **NumPy**
- **Matplotlib**
- **Pandas**


---


## Podgląd otrzymanych rezultatów ##

### 1. Sieć neuronowa ###

#### Importowanie bibliotek i wczytanie MNIST  ####
![Importowanie bibliotek i wczytanie MNIST](https://i.imgur.com/GNBazMJ.png)


#### Budowa sieci neuronowej ####

![Budowa sieci neuronowej](https://i.imgur.com/OIVsB8F.png)


#### Trenowanie modelu sieciowego ####

![Trenowanie modelu sieciowego](https://i.imgur.com/2fZJeuc.png)


#### Ewaluacja na zbiorze testowym ####

![Ewaluacja na zbiorze testowym](https://i.imgur.com/Omxto12.png)


#### Wyświetlenie ostatnich pięciu epok trenowania ####

![Wyświetlenie ostatnich pięciu epok trenowania](https://i.imgur.com/XDY6uxn.png)

### Podsumowanie ###

Wnioski z trenowania sieci neuronowej:

1. Architektura sieci:
   
     * Warstwa wejściowa: Spłaszczenie obrazu 28x28 na wektor 784.
     * Warstwa ukryta: 64 neurony z aktywacją ReLU.
     * Warstwa wyjściowa: 10 neuronów z aktywacją softmax.  
    
3. Wydajność modelu:
   
    * Model osiągnął 97,54% dokładności na zbiorze testowym, co przekracza wymagane 95%.
    * Sieć jest wystarczająco mała i efektywna, aby skutecznie klasyfikować cyfry.
    
3. Stabilność trenowania:
    
    * W ostatnich 5 epokach zarówno strata, jak i dokładność były stabilne.
    * Nie wystąpiło przeuczenie (overfitting), mimo że strata walidacyjna jest nieco wyższa niż strata treningowa.

    
4. Potencjalne ulepszenia:
   
Można by spróbować zmniejszyć liczbę neuronów w warstwie ukrytej (np. z 64 do 32) i ponownie przetestować sieć. 

---

### Otrzymane wyniki testowania:  ###

  * Dokładność na zbiorze testowym: 97,54%
  * Dokładność walidacyjna (ostatnie 5 epok): Stabilnie utrzymywała się na poziomie ~97,2%.
  * Strata walidacyjna (val_loss): Utrzymywała się w okolicach 0.098.

---
---


### 2. Redukcja poziomów szarości ###


![Redukcja poziomów szarości](https://i.imgur.com/ahD3abG.png)


![Trenowanie modelu](https://i.imgur.com/8f3t4hP.png)


![Test accuracy](https://i.imgur.com/U2vZFUc.png)



### Podsumowanie ###

Wnioski z trenowania sieci neuronowej:

1. Architektura sieci:
   
    * Warstwa wejściowa: Spłaszczenie obrazu 28x28 na wektor 784.
    * Warstwa ukryta: 64 neurony z aktywacją ReLU.
    * Warstwa wyjściowa: 10 neuronów z aktywacją softmax.

2. Wydajność modelu:
   
    * Model osiągnął 97,4% dokładności na zbiorze testowym, co jest wynikiem bliskim temu z poprzedniego zadania (97,54%).
    * Redukcja liczby poziomów szarości z 256 do 16 nie miała dużego wpływu na dokładność modelu, co sugeruje, że sieć jest w stanie skutecznie klasyfikować cyfry mimo uproszczenia danych wejściowych.
    * Model jest wystarczająco efektywny, aby rozpoznawać cyfry, nawet przy zmniejszonej rozdzielczości obrazu.

4. Stabilność trenowania:

    * Model szybko osiągnął wysoką dokładność, osiągając 97,4% na zbiorze testowym.
    * Nie wystąpiło przeuczenie (overfitting), ponieważ różnice między dokładnością na zbiorze treningowym a walidacyjnym są minimalne.
    * Strata walidacyjna utrzymywała się na stabilnym poziomie, a dokładność na zbiorze walidacyjnym również była stabilna (~97,2%).

6. Potencjalne ulepszenia:
   
    * Można rozważyć zwiększenie liczby poziomów szarości lub zastosowanie innych metod redukcji wymiarów (np. PCA), aby sprawdzić, czy uda się poprawić wyniki.
    * Testowanie różnych funkcji aktywacji, jak np. Leaky ReLU, mogłoby wpłynąć na dalszą optymalizację modelu.


---

### Otrzymane wyniki testowania:  ###

  * Dokładność na zbiorze testowym: 97,4%
  * Dokładność walidacyjna (ostatnie 5 epok): Stabilnie utrzymywała się na poziomie ~97,2%.
  * Strata walidacyjna (val_loss): Utrzymywała się w okolicach 0.1.
