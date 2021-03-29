# CeneoScraper
## Etap 1 - pobranie opinii
### Etap 1.1 - pobranie składowych pojedynczej opinii
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

### Etap 2 - Ekstrakcja wszystkich opinii 