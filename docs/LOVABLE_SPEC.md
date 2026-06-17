# Lovable spec — MIKO Ostrzenie Narzędzi

## Nazwa projektu

`miko-ostrzenie-narzedzi`

## Lovable project

https://lovable.dev/projects/fd3cd6de-9d28-4830-ac18-17839ac6ade2

## Główna intencja

Zbudować premium stronę/aplikację dla lokalnej usługi ostrzenia narzędzi: **MIKO Ostrzenie Narzędzi**.

Strona ma przede wszystkim konwertować odwiedzających na kontakt telefoniczny albo wysłanie formularza zapytania.

## Styl wizualny

- ciemny warsztat premium,
- tła: czarny / grafit / antracyt,
- akcenty: czerwień, stal, iskry,
- klimat: lokalna fachowość + precyzja + solidność,
- motyw graficzny: ostrze, piła tarczowa, szlif, iskry,
- bez przesadnego chaosu i bez taniego efektu gamingowego.

## Sekcje strony

1. Hero
   - mocny nagłówek,
   - krótka obietnica jakości,
   - CTA: „Zamów ostrzenie” / „Zadzwoń teraz”.

2. Usługi
   - nożyczki fryzjerskie,
   - noże kuchenne,
   - narzędzia groomerskie,
   - narzędzia rzemieślnicze,
   - ostrza specjalistyczne.

3. Cennik orientacyjny
   - proste karty usług,
   - informacja, że ostateczna cena zależy od stanu narzędzia.

4. Jak to działa
   - kontakt,
   - wycena,
   - ostrzenie,
   - odbiór / dostawa.

5. Formularz zgłoszeniowy
   - imię i nazwisko,
   - telefon,
   - e-mail,
   - typ narzędzia,
   - liczba sztuk,
   - preferowany termin,
   - odbiór/dostawa,
   - uwagi.

6. Galeria / przed i po
   - placeholdery pod zdjęcia.

7. Opinie
   - placeholdery pod przyszłe rekomendacje.

8. FAQ
   - czas realizacji,
   - typy narzędzi,
   - odbiór/dostawa,
   - płatność,
   - gwarancja jakości.

9. Kontakt
   - telefon,
   - e-mail,
   - lokalizacja Warszawa,
   - godziny pracy do edycji.

## Model danych do przyszłej rozbudowy

```ts
type Booking = {
  id: string;
  name: string;
  phone: string;
  email?: string;
  toolType: string;
  quantity: number;
  preferredDate?: string;
  deliveryOption: 'pickup' | 'delivery' | 'in_person';
  notes?: string;
  status: 'new' | 'contacted' | 'priced' | 'in_progress' | 'ready' | 'done' | 'cancelled';
  createdAt: string;
};

type Service = {
  id: string;
  title: string;
  description: string;
  startingPrice?: number;
  isActive: boolean;
};

type Testimonial = {
  id: string;
  author: string;
  content: string;
  rating?: number;
  source?: string;
  isPublished: boolean;
};
```

## Priorytety MVP

1. Szybki landing z dobrym copy.
2. Formularz kontaktowy z walidacją.
3. Mobile-first.
4. SEO pod frazy lokalne: ostrzenie narzędzi Warszawa, ostrzenie nożyczek, ostrzenie noży, ostrzenie narzędzi fryzjerskich.
5. Łatwe późniejsze dodanie backendu / Supabase / panelu admina.
