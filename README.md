# CeneoScraper

## Etap 1 - pobranie opinii o produkcie

- pobranie kodu pojedynczej strony z opiniami o produkcie
- wydobycie kodu ze strony fragmentu odpowiadajacego pojedynczej opinii

| Składowa                  | Selektor CSS                                                | Nazwa zmiennej | Typ danych |
| ------------------------- | ----------------------------------------------------------- | -------------- | ---------- |
| Opinia                    | div.js_product-review                                       | opinion        |
| ID opinii                 | [data-entry-id]                                             | opinionId      | str        |
| Autor                     | span.user-post\_\_author-name                               | author         | str        |
| Rekomendacja              | span.user-post\_\_author-recomendation > em                 | rcmd           | bool       |
| Liczba gwiazdek           | span.user-post\_\_score-count                               | stars          | float      |
| Treść opinii              | div.user-post\_\_text                                       | content        | str        |
| Lista zalet               | div[class*="positives"] ~ div.review-feature\_\_item        | pros           | list       |
| lista wad                 | div[class*="negatives"] ~ div.review-feature\_\_item        | cons           | list       |
| Czy potwierdzona zakupem  | div.review-pz                                               | purchased      | bool       |
| Data wystawienia          | span.user-post\_\_published > time:nth-child(1)["datetime"] | publishedDate  | str        |
| Data zakupu               | span.user-post\_\_published > time:nth-child(2)["datetime"] | puchaseDate    | str        |
| Dla ilu osób przydatna    | span[id^="votes-yes"]                                       | useful         | int        |
| Dla ilu osób nieprzydatna | span[id^="votes-no"]                                        | useless        | int        |

## Etap 2 - Ekstrakcja wszystkich opinii o produkcie z pojedynczej strony.

