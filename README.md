# CeneoScraper
## Etap 1 - pobranie opinii
### Etap 1.1 - pobranie składowych pojedynczej opinii
- pobranie kodu pojedynczej strony z opiniami o produkcie 
- wydobycie z kodu strony fragmentu odpowiadającego pojedynczej opinii
- zapisanie do pojedynczych zmiennych wartośći skladowych opinii

|Składowa|Selektor CSS|Nazwa zmiennej|Typ danych|
|--------|------------|--------------|----------|
|Opinia|div.js_product-review|opinion||
|Identyfikator opinii|["data-entry-id"]|opinionId||
|Autor|span.user-post__author-name|author||
|Rekomendacja|span.user-post__author-recomendation >em|rcmd||
|Liczba gwiazdek|span.user-post__score-count|stars||
|Treść opinii|div.user-post__text|content||
|Lista zalet|div[class*="positives"] ~div.review-feature_item|pros||
|Lista wad|div[class*="negatives"] ~div.review-feature_item|cons||
|Czy podtwierdzona zakupem|div.review-pz|purchased||
|Data wystawienia|span.user-post__published > time:nth-child(1)["datetime"]|publishDate||
|Data zakupu|span.user-post__published > time:nth-child(2)["datetime"]|purchaseDate||
|Dla ilu osób przydatna|span[id^="votes-yes"]|useful||
|Dla ilu osób nieprzydatna|span[id^="votes-no"]|useless||