# Specyfikacja Wymagań Oprogramowania (SRS)

## System HRflow - Zarządzanie Cyklem Życia Pracownika

**Zespół projektowy:** Adrian Jabłoński, Paweł Gorgolewski, Kamil Pierzchała, Łukasz Bartoszek,  Bartosz Balawender

---

## 1. Wstęp

### 1.1. Cel dokumentu

Ten dokument opisuje wymagania dla systemu **HRflow** w wersji 1.0 - kompleksowej platformy do zarządzania cyklem życia pracownika, od rekrutacji przez rozwój aż po offboarding.

**Dla kogo jest ten dokument:**

- Zespół deweloperski - jako podstawa do implementacji
- Product Owner - do weryfikacji zgodności z wizją produktu
- Testerzy - jako źródło scenariuszy testowych
- Interesariusze biznesowi - do akceptacji zakresu projektu

**Jak używać tego dokumentu:**

- Rozdział 4 (Wymagania Funkcjonalne) zawiera szczegółowe kryteria akceptacji w formacie Given-When-Then - to główne źródło dla deweloperów i testerów
- Rozdział 5 (Atrybuty Jakościowe) definiuje mierzalne wymagania niefunkcjonalne
- Dodatki zawierają materiały pomocnicze (persony, diagramy)

### 1.2. Wizja, Zakres i Cele Produktu

#### Wizja

> *"HRflow to inteligentna platforma HR, która automatyzuje żmudne procesy kadrowe i pozwala firmom skupić się na tym, co naprawdę ważne - ludziach. Łączymy rekrutację, onboarding, rozwój i zarządzanie talentami w jeden spójny ekosystem, który oszczędza czas i pomaga budować lepsze zespoły."*

#### Zakres systemu

System HRflow obejmuje następujące obszary:

**Moduł Rekrutacji:**

- Automatyczny screening CV z parsowaniem dokumentów
- Semantyczne dopasowanie kandydatów do ofert (Semantic Matching Engine)
- Giełda Talentów - rekrutacja wewnętrzna
- Portal Kandydata z real-time tracking statusu
- System poleceń pracowniczych (Employee Referral Engine)
- Anonimizacja danych w procesie selekcji (Diversity & Inclusion)
- Automatyczna publikacja ofert w social media

**Moduł Onboardingu:**

- Cyfrowy obieg dokumentów z e-podpisem
- Automatyczne generowanie umów
- Zgrywalizowany moduł wdrożeniowy
- Integracja z repozytoriami kodu i dokumentacją techniczną

**Moduł Rozwoju i Szkoleń:**

- Platforma LMS ze spersonalizowanymi ścieżkami rozwoju
- System OKR (Objectives and Key Results)
- Continuous Feedback (opinie peer-to-peer)
- System oceny potencjału (9-box grid)
- Kafeteryjna platforma benefitowa

**Moduł Analityki HR:**

- Predykcja rotacji pracowników (Retention AI)
- Dashboardy i raportowanie
- Ankiety pulsujące

**Moduł Offboardingu:**

- Automatyczne odbieranie dostępów (integracja z AD/LDAP)
- Program Alumni dla byłych pracowników

#### Cele biznesowe i KPI

| Cel                        | Metryka (KPI)                              | Wartość docelowa             | Horyzont czasowy |
|----------------------------|--------------------------------------------|------------------------------|------------------|
| Automatyzacja rekrutacji   | Time-to-Hire                               | Skrócenie z 45 do 20 dni     | 6 miesięcy       |
| Trafność dopasowania       | Interview Acceptance Rate                  | Wzrost z 10% do 15%          | 6 miesięcy       |
| Rekrutacja wewnętrzna      | % wakatów wypełnionych wewnętrznie         | 40%                          | 9 miesięcy       |
| Różnorodność               | Wzrost różnorodności kandydatów            | +30%                         | 6 miesięcy       |
| Candidate Experience       | Candidate NPS (cNPS)                       | +50                          | 6 miesięcy       |
| Szybkość wdrożenia         | Time-to-Productivity (programiści)         | Skrócenie z 3 mies. do 6 tyg.| 12 miesięcy      |
| Paperless HR               | Redukcja czasu na dokumentację             | -80%                         | 3 miesiące       |
| Upskilling                 | % przeszkolonej kadry technicznej          | 60%                          | 12 miesięcy      |
| Sukcesja                   | % kluczowych stanowisk z następcą          | 90%                          | 6 miesięcy       |
| Employer Branding          | Zasięg w social media                      | +50%                         | 6 miesięcy       |
| Continuous Feedback        | Średnia opinii peer-to-peer/pracownik      | 4/miesiąc                    | 6 miesięcy       |
| Transparentność celów      | Pokrycie OKR                               | 100%                         | 3 miesiące       |
| Retencja                   | Redukcja rotacji kluczowych specjalistów   | -15%                         | 12 miesięcy      |
| Wykorzystanie benefitów    | Utylizacja budżetu szkoleniowo-benefitowego| 95% (z 60%)                  | 12 miesięcy      |
| Bezpieczeństwo offboardingu| Automatyczne odbieranie dostępów           | 100%                         | od wdrożenia     |
| Program poleceń            | Udział zatrudnień z poleceń                | Wzrost z 8% do 25%           | 9 miesięcy       |

#### Poza zakresem

System HRflow **NIE BĘDZIE** obejmował:

- Pełnej obsługi płacowej (payroll) - integracja z zewnętrznymi systemami
- Zarządzania czasem pracy i grafikami (RCP)
- Obsługi podróży służbowych
- Systemu helpdesk IT
- Zarządzania flotą samochodową
- Obsługi BHP (szkolenia BHP będą w LMS, ale pełna dokumentacja BHP nie)

### 1.3. Definicje, Akronimy i Skróty

| Termin                       | Definicja                                                                    |
|------------------------------|------------------------------------------------------------------------------|
| **Time-to-Hire**             | Czas od publikacji oferty do podpisania umowy z kandydatem                   |
| **Time-to-Productivity**     | Czas od zatrudnienia do osiągnięcia pełnej produktywności                    |
| **cNPS**                     | Candidate Net Promoter Score - wskaźnik satysfakcji kandydatów               |
| **Semantic Matching Engine** | Silnik dopasowania oparty na analizie semantycznej kompetencji               |
| **9-box grid**               | Macierz oceny pracowników (potencjał vs. wydajność)                          |
| **OKR**                      | Objectives and Key Results - metodyka zarządzania przez cele                 |
| **LMS**                      | Learning Management System - platforma e-learningowa                         |
| **AD/LDAP**                  | Active Directory / Lightweight Directory Access Protocol                     |
| **Giełda Talentów**          | Internal Talent Marketplace - system dopasowania pracowników do wakatów      |
| **Retention AI**             | Moduł predykcji ryzyka odejścia pracownika                                   |
| **Employee Referral Engine** | System poleceń pracowniczych                                                 |
| **Kafeteria benefitowa**     | Elastyczny system wymiany punktów na benefity                                |
| **Ankiety pulsujące**        | Krótkie, regularne ankiety badające nastroje pracowników                     |
| **Alumni**                   | Program utrzymywania kontaktu z byłymi pracownikami                          |
| **MVP**                      | Minimum Viable Product - minimalna wersja produktu                           |
| **RODO/GDPR**                | Rozporządzenie o ochronie danych osobowych                                   |

### 1.4. Przegląd dokumentu

| Rozdział                     | Zawartość                                                           |
|------------------------------|---------------------------------------------------------------------|
| **2. Opis Ogólny**           | Główne funkcje systemu, klasy użytkowników, ograniczenia i założenia|
| **3. Interfejsy Zewnętrzne** | Makiety UI, opis integracji z zewnętrznymi systemami                |
| **4. Wymagania Funkcjonalne**| Szczegółowe user stories z kryteriami akceptacji (Given-When-Then)  |
| **5. Atrybuty Jakościowe**   | Wymagania niefunkcjonalne (wydajność, bezpieczeństwo, skalowalność) |
| **6. Analiza Wymagań**       | Analiza porównawcza konkurencji                                     |
| **Dodatki**                  | Diagram przypadków użycia, persony, kwestie do rozwiązania          |

---

## 2. Opis Ogólny

### 2.1. Główne Funkcje Produktu

System HRflow składa się z pięciu głównych modułów:

```
┌───────────────────────────────────────────────────────────────────────┐
│                               HRflow                                  │
├──────────────┬──────────────┬──────────────┬────────────┬─────────────┤
│  REKRUTACJA  │  ONBOARDING  │    ROZWÓJ    │  ANALITYKA │ OFFBOARDING │
├──────────────┼──────────────┼──────────────┼────────────┼─────────────┤
│• ATS         │• Dokumenty   │• LMS         │• Retention │• Odbieranie │
│• Screening   │• E-podpis    │• OKR         │  AI        │  dostępów   │
│• Matching    │• Gamifikacja │• Feedback    │• Dashboardy│• Alumni     │
│• Portal      │• Integracje  │• 9-box       │• Ankiety   │             │
│  Kandydata   │  dewelop.    │• Kafeteria   │            │             │
│• Polecenia   │              │              │            │             │
│• Social      │              │              │            │             │
│  Media       │              │              │            │             │
└──────────────┴──────────────┴──────────────┴────────────┴─────────────┘
```

#### Moduł Rekrutacji

| Funkcja                             | Opis                                                                            |
|-------------------------------------|---------------------------------------------------------------------------------|
| **ATS (Applicant Tracking System)** | Zarządzanie procesem rekrutacyjnym, publikacja ofert, śledzenie kandydatów      |
| **Automatyczny Screening CV**       | Parsowanie CV, ekstrakcja kompetencji, wstępna kwalifikacja                     |
| **Semantic Matching Engine**        | Inteligentne dopasowanie kandydatów do ofert z rozpoznawaniem hierarchii komp.  |
| **Portal Kandydata**                | Interfejs dla kandydatów z real-time tracking statusu aplikacji                 |
| **Giełda Talentów**                 | Dopasowanie obecnych pracowników do wewnętrznych wakatów                        |
| **Employee Referral Engine**        | System poleceń z gamifikacją i automatycznym naliczaniem nagród                 |
| **Anonimizacja D&I**                | Maskowanie danych wrażliwych w procesie selekcji                                |
| **Auto-publikacja Social Media**    | Automatyczne publikowanie ofert na LinkedIn, Facebook, Instagram                |
| **Integracja z kalendarzami**       | Automatyczne umawianie spotkań rekrutacyjnych                                   |

#### Moduł Onboardingu

| Funkcja                      | Opis                                                 |
|------------------------------|------------------------------------------------------|
| **Cyfrowy obieg dokumentów** | Elektroniczne formularze, workflow zatwierdzeń       |
| **E-podpis**                 | Podpisywanie umów i dokumentów elektronicznie        |
| **Generator umów**           | Automatyczne generowanie umów na podstawie szablonów |
| **Moduł wdrożeniowy**        | Zgrywalizowany onboarding z śledzeniem postępów      |
| **Integracje deweloperskie** | Połączenie z repozytoriami kodu, Confluence, Jira    |

#### Moduł Rozwoju i Szkoleń

| Funkcja                | Opis                                            |
|------------------------|-------------------------------------------------|
| **LMS**                | Platforma e-learningowa ze ścieżkami rozwoju    |
| **System OKR**         | Kaskadowanie celów, powiązanie z strategią firmy|
| **Continuous Feedback**| Ciągła wymiana opinii peer-to-peer              |
| **9-box grid**         | Ocena potencjału i planowanie sukcesji          |
| **Kafeteria benefitowa**| Elastyczna wymiana punktów na benefity         |

#### Moduł Analityki HR

| Funkcja               | Opis                                      |
|-----------------------|-------------------------------------------|
| **Retention AI**      | Predykcja ryzyka odejścia pracowników     |
| **Dashboardy**        | Wizualizacja kluczowych metryk HR         |
| **Ankiety pulsujące** | Regularne badanie nastrojów pracowników   |
| **Raportowanie**      | Generowanie raportów dla zarządu          |

#### Moduł Offboardingu

| Funkcja                   | Opis                                            |
|---------------------------|-------------------------------------------------|
| **Zarządzanie dostępami** | Automatyczne odbieranie dostępów przez AD/LDAP  |
| **Program Alumni**        | Portal dla byłych pracowników, networking       |

### 2.2. Klasy Użytkowników

System rozróżnia następujące role użytkowników:

#### Użytkownicy zewnętrzni

| Rola           | Opis                              | Dostęp do modułów  |
|----------------|-----------------------------------|--------------------|
| **Kandydat**   | Osoba aplikująca na stanowisko    | Portal Kandydata   |
| **Alumni**     | Były pracownik w programie Alumni | Moduł Alumni       |

#### Użytkownicy wewnętrzni

| Rola                    | Opis                                   | Dostęp do modułów                                            |
|-------------------------|----------------------------------------|--------------------------------------------------------------|
| **Rekruter**            | Prowadzi procesy rekrutacyjne          | Rekrutacja (pełny), Analityka (częściowy)                    |
| **HR Manager**          | Zarządza działem HR, definiuje procesy | Wszystkie moduły                                             |
| **HR Admin**            | Obsługa dokumentacji kadrowej          | Onboarding, Offboarding, Dokumenty                           |
| **Pracownik**           | Standardowy użytkownik systemu         | Rozwój, Feedback, Kafeteria, OKR                             |
| **Menedżer**            | Kierownik zespołu                      | Rekrutacja (hiring manager), Rozwój, Feedback, OKR, Analityka|
| **Trener wewnętrzny**   | Tworzy i prowadzi szkolenia            | LMS (tworzenie treści)                                       |
| **Administrator IT**    | Zarządza integracjami i konfiguracją   | Panel administracyjny, integracje                            |
| **Zarząd**              | Dostęp do strategicznych raportów      | Analityka, Dashboardy                                        |

#### Skrócone persony (pełne w Dodatku B)

**Anna - Rekruterka (28 lat)**
> *"Każdego dnia przeglądam setki CV. Potrzebuję narzędzia, które odsieje tych, którzy kompletnie nie pasują, ale nie przegapi diamentów ukrytych w niestandardowych CV."*

Anna pracuje w firmie IT od 2 lat. Prowadzi jednocześnie 8-12 procesów rekrutacyjnych. Jej główny ból to czas poświęcany na wstępną selekcję CV i koordynację terminów rozmów.

**Marek - Nowy programista (25 lat)**
> *"Pierwszy tydzień w nowej pracy to chaos. Loginy, hasła, dokumenty, spotkania... Chciałbym mieć jedno miejsce, gdzie wszystko jest ogarnięte."*

Marek właśnie dołączył do zespołu backend. Potrzebuje szybko wdrożyć się w projekt i poznać procesy firmy. Lubi gamifikację i jasne cele.

**Katarzyna - HR Manager (42 lata)**
> *"Zarząd pyta mnie o rotację, koszty rekrutacji, development pipeline... Zbieranie tych danych z Exceli to koszmar."*

Katarzyna zarządza 5-osobowym zespołem HR w firmie produkcyjnej (400 pracowników). Potrzebuje narzędzi analitycznych i automatyzacji procesów.

**Tomek - Menedżer zespołu (35 lat)**
> *"Chcę wiedzieć, kto w moim zespole ma potencjał na lidera, a kto może odejść. I chcę to wiedzieć zanim będzie za późno."*

Tomek zarządza 12-osobowym zespołem sprzedaży. Potrzebuje prostych narzędzi do oceny i rozwoju ludzi.

### 2.3. Ograniczenia Projektowe i Implementacyjne

#### Ograniczenia technologiczne

| Kategoria | Ograniczenie | Uzasadnienie |
|-----------|--------------|--------------|
| **Backend** | Python 3.11+ / FastAPI lub Node.js 20+ | Wymagana dobra obsługa ML i async |
| **Frontend** | React 18+ / TypeScript | Standard rynkowy, duża społeczność |
| **Baza danych** | PostgreSQL 15+ | Wsparcie dla JSON, full-text search |
| **Cache/Queue** | Redis | Sesje, kolejki zadań, real-time |
| **ML/AI** | Python + scikit-learn / spaCy | Matching Engine, Retention AI |
| **Wyszukiwarka** | Elasticsearch | Wyszukiwanie semantyczne CV |
| **Kontenery** | Docker + Docker Compose | Deployment, środowiska deweloperskie |
| **Hosting** | Minimum 8GB RAM, 4 vCPU dla MVP | Wymagania ML i Elasticsearch |

#### Ograniczenia organizacyjne

| Kategoria | Ograniczenie | Uwagi |
|-----------|--------------|-------|
| **Zespół** | 5-7 deweloperów | Ograniczona dostępność (projekt uczelniany) |
| **Czas** | MVP w 4 miesiące | Deadline wynikający z harmonogramu studiów |
| **Budżet** | Brak budżetu na płatne usługi | Tylko open-source i darmowe tiers |
| **Metodyka** | Scrum, sprinty 2-tygodniowe | Wymóg przedmiotu |
| **Dokumentacja** | SRS, dokumentacja techniczna w repo | Wymóg oddania projektu |
| **Code Review** | Wymagane PR z min. 1 review | Jakość kodu |

#### Ograniczenia prawne i środowiskowe

| Kategoria | Ograniczenie | Wpływ na system |
|-----------|--------------|-----------------|
| **RODO (GDPR)** | Pełna zgodność | Szyfrowanie danych, prawo do usunięcia, zgody |
| **RODO - retencja** | Dane kandydatów max 2 lata | Automatyczne usuwanie danych |
| **RODO - dostęp** | Prawo dostępu do swoich danych | Eksport danych użytkownika |
| **Kodeks Pracy** | Zgodność z polskim prawem pracy | Wzory umów, okresy wypowiedzenia |
| **Podpis elektroniczny** | eIDAS - kwalifikowany podpis | Integracja z dostawcą podpisu |
| **Accessibility** | WCAG 2.1 AA | Dostępność dla osób z niepełnosprawnościami |
| **Regulacje uczelniane** | Projekt akademicki | Kod jako własność intelektualna studentów |

### 2.4. Założenia Projektowe

#### Założenia biznesowe

| ID | Założenie | Ryzyko jeśli nieprawdziwe |
|----|-----------|---------------------------|
| **ZB-01** | Firma docelowa zatrudnia 100-1000 pracowników | Za mała firma = zbędne funkcje; za duża = problemy wydajnościowe |
| **ZB-02** | Istnieje dział HR z min. 2 osobami | Brak HR = brak użytkowników systemu |
| **ZB-03** | Firma prowadzi aktywną rekrutację (min. 5 wakatów/miesiąc) | Brak rekrutacji = moduł nieużywany |
| **ZB-04** | Pracownicy mają dostęp do komputera/smartfona | Brak dostępu = brak adopcji |
| **ZB-05** | Firma ma już podstawowe systemy IT (email, AD) | Brak = problemy z integracją |

#### Założenia techniczne

| ID | Założenie | Ryzyko jeśli nieprawdziwe |
|----|-----------|---------------------------|
| **ZT-01** | Użytkownicy korzystają z nowoczesnych przeglądarek (Chrome, Firefox, Edge - ostatnie 2 wersje) | Stare przeglądarki = problemy z UI |
| **ZT-02** | Dostępne stabilne łącze internetowe min. 10 Mbps | Wolne łącze = timeout przy uploadzie CV |
| **ZT-03** | CV są w formatach PDF/DOCX/DOC | Inne formaty = błędy parsowania |
| **ZT-04** | Dostępna integracja OAuth2 z firmowym IdP | Brak = osobne loginy, security risk |
| **ZT-05** | Elasticsearch dostępny jako managed service lub self-hosted | Brak = brak wyszukiwania semantycznego |

#### Założenia dotyczące użytkowników

| ID | Założenie | Ryzyko jeśli nieprawdziwe |
|----|-----------|---------------------------|
| **ZU-01** | HR i menedżerowie przejdą szkolenie z systemu (min. 2h) | Brak szkolenia = niska adopcja |
| **ZU-02** | Kandydaci są przyzwyczajeni do portali rekrutacyjnych | Nieintuicyjny UX = porzucone aplikacje |
| **ZU-03** | Pracownicy będą aktywnie korzystać z systemu feedbacku | Brak adopcji = puste metryki |
| **ZU-04** | Menedżerowie będą prowadzić regularne 1:1 | Brak spotkań = nieaktualne dane w systemie |

#### Zależności zewnętrzne

| ID | Zależność | Alternatywa |
|----|-----------|-------------|
| **ZZ-01** | API LinkedIn do publikacji ofert | Ręczna publikacja |
| **ZZ-02** | Dostawca e-podpisu (np. Autenti, DocuSign) | Podpis offline + skan |
| **ZZ-03** | Serwer SMTP do wysyłki maili | Zewnętrzny serwis (SendGrid, Mailgun) |
| **ZZ-04** | Active Directory / LDAP firmy | Lokalne konta w systemie |
| **ZZ-05** | System kalendarzowy (Google/Outlook) | Manualnie uzgadniane terminy |

---
