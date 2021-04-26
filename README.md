# CeneoScraper
## Etap 1 - Ekstrakcja pojedynczej opinii o produkcie, którego kod będzie wpisany w kodzie programu.
- pobranie kodu pojedynczej strony z opiniami o produkcie 
- wydobycie z kodu strony fragmentu odpowiadającego pojedynczej opinii
- zapisanie do pojedynczych zmiennych wartośći skladowych opinii
-obsługa blędów
-transformacja danych do docelowych typów

|Składowa|Selektor CSS|Nazwa zmiennej|Typ danych|
|--------|------------|--------------|----------|
|Opinia|div.js_product-review|opinion|bs4.element.Tag|
|Identyfikator opinii|["data-entry-id"]|opinionId|str|
|Autor|span.user-post__author-name|author|str|
|Rekomendacja|span.user-post__author-recomendation >em|rcmd|bool|
|Liczba gwiazdek|span.user-post__score-count|stars|float|
|Treść opinii|div.user-post__text|content|str|
|Lista zalet|div[class*="positives"] ~div.review-feature_item|pros|list|
|Lista wad|div[class*="negatives"] ~div.review-feature_item|cons|list|
|Czy podtwierdzona zakupem|div.review-pz|purchased|bool|
|Data wystawienia|span.user-post__published > time:nth-child(1)["datetime"]|publishDate|str|
|Data zakupu|span.user-post__published > time:nth-child(2)["datetime"]|purchaseDate|str|
|Dla ilu osób przydatna|span[id^="votes-yes"]|useful|int|
|Dla ilu osób nieprzydatna|span[id^="votes-no"]|useless|int|

## Etap 2 - Ekstrakcja wszystkich opinii o produkcie z pojedynczej strony.
- utworzenie słownika do przechowywania wszystkich składowych pojedynczej opinii 
- utworzenie listy, do której będą dodawane słowniki reprezentjące pojedyncze opinie 
-dodanie pętli, w której pobierane były składowe kolejnych opinii z pojedynczej strony 
## Etap 3 - Ekstrakcja wszystkich opinii o produkcie z wszystkich stron 
-dodanie pętli, w której:
* pobierana jest strona z opiniami
* dla każdej opinii na stronie pobiearane są jej składowe 
* sprawdzane jest, czy istnieje kolejna strona z opiniami, ktore powinny zostać pobrane 
- zapisania wszystkich opinii o produkcie do pliku .json 
## Etap 4 - Refaktoryzacja kodu
-parametryzacja identyfikatora opinii