# MediVisit — UML Business Analysis Case Study

> **PL:** Portfolio project dla roli Business Analyst / IT Business Analyst — system rezerwacji wizyt medycznych online.  
> **EN:** Portfolio project for a Business Analyst / IT Business Analyst role — online medical appointment booking system.

![Business Analysis](https://img.shields.io/badge/Business%20Analysis-Requirements-blue)
![UML](https://img.shields.io/badge/UML-Use%20Case%20%7C%20Activity%20%7C%20Sequence%20%7C%20Class%20%7C%20State%20%7C%20Component-green)
![draw.io](https://img.shields.io/badge/Diagrams-draw.io-orange)
![Portfolio](https://img.shields.io/badge/Portfolio-IT%20Business%20Analyst-purple)

---

## 🇵🇱 Wersja polska

### Cel projektu

**MediVisit** to przykładowy system umożliwiający pacjentom rezerwację wizyt medycznych online, a placówce medycznej zarządzanie dostępnością specjalistów, wizytami, płatnościami i powiadomieniami.

Projekt pokazuje sposób pracy analityka biznesowego / IT Business Analysta: identyfikację procesu, aktorów, przypadków użycia, przebiegów systemowych, modelu domenowego, stanów obiektu oraz logicznych komponentów rozwiązania.

### Problem biznesowy

Placówka medyczna obsługuje znaczną część rezerwacji przez telefon, e-mail i recepcję. Powoduje to błędy w dostępności terminów, opóźnienia w potwierdzeniach, brak przejrzystej historii zmian oraz trudność w obsłudze przedpłat dla wybranych usług.

Celem rozwiązania jest cyfryzacja procesu rezerwacji wizyt, ograniczenie pracy manualnej oraz zapewnienie pacjentowi czytelnego procesu wyboru terminu, płatności i potwierdzenia wizyty.

### Zakres analizy

**W zakresie:**

- wyszukiwanie lekarza i dostępnego terminu,
- rezerwacja, zmiana i anulowanie wizyty,
- tymczasowa blokada terminu,
- obsługa płatności online dla wizyt wymagających przedpłaty,
- wysyłka potwierdzeń i przypomnień,
- podstawowe zarządzanie grafikiem lekarzy i użytkownikami.

**Poza zakresem:**

- pełna elektroniczna dokumentacja medyczna,
- e-recepty,
- teleporady wideo,
- pełna księgowość i fakturowanie,
- integracje z publicznymi systemami ochrony zdrowia.

### Kluczowe reguły biznesowe

- Wizyta może zostać potwierdzona dopiero po udanej płatności, jeśli wymagana jest przedpłata.
- Jeśli płatność zostanie odrzucona lub przekroczony zostanie czas płatności, tymczasowo zablokowany termin zostaje zwolniony.
- Jeśli przedpłata nie jest wymagana, wizyta może zostać potwierdzona bezpośrednio po rezerwacji.
- Pacjent otrzymuje potwierdzenie wizyty po udanej rezerwacji.
- Anulowanie wizyty może wywołać wysłanie powiadomienia o anulowaniu.
- Lekarz może mieć wiele dostępnych terminów.
- Jeden termin dostępności może być zarezerwowany maksymalnie przez jedną wizytę.

### Założenia

- System obsługuje zarówno pacjentów, jak i personel recepcji.
- Płatność online jest opcjonalna i zależy od tego, czy dla danej wizyty wymagana jest przedpłata.
- Obsługa płatności odbywa się przez zewnętrzną bramkę płatności.
- Powiadomienia są dostarczane przez zewnętrzny serwis e-mail/SMS.
- Terminy wizyt są tymczasowo blokowane na czas procesu płatności.
- Diagram komponentów przedstawia architekturę logiczną, a nie fizyczne wdrożenie systemu.

---

## Uzasadnienie doboru diagramów UML w projekcie MediVisit

Na początku projektu MediVisit punktem wyjścia była potrzeba opisania procesu rezerwacji wizyty medycznej z opcjonalną płatnością online. Zakres systemu nie ograniczał się wyłącznie do samego wyboru terminu, ale obejmował również wyszukiwanie lekarza, sprawdzanie dostępności terminów, utworzenie rezerwacji, obsługę płatności, potwierdzenie wizyty, wysyłkę powiadomień oraz obsługę sytuacji wyjątkowych, takich jak odrzucona płatność, anulowanie wizyty lub brak dostępnych terminów.

Na początku zostały zidentyfikowane główne potrzeby użytkowników systemu. Pacjent powinien mieć możliwość wyszukania lekarza, sprawdzenia dostępnych terminów oraz zarezerwowania wizyty. W niektórych przypadkach pacjent może być zobowiązany do dokonania przedpłaty online. System powinien potwierdzić wizytę po udanej płatności, zwolnić termin w przypadku niepowodzenia płatności oraz wysłać pacjentowi powiadomienie e-mail lub SMS. Dodatkowo administrator i personel medyczny powinni mieć możliwość zarządzania użytkownikami oraz grafikami lekarzy.

Na tej podstawie uznano, że pojedynczy diagram nie wystarczy do pełnego opisania systemu. Każdy diagram UML przedstawia system z innej perspektywy, dlatego dobrano zestaw diagramów pozwalający opisać wymagania funkcjonalne, przebieg procesu, komunikację między uczestnikami, strukturę danych, cykl życia wizyty oraz logiczną architekturę rozwiązania.

### Przebieg analizy

Analiza została przeprowadzona etapowo. Najpierw skupiono się na zrozumieniu, kto korzysta z systemu i jakie cele chce osiągnąć. Następnie przeanalizowano główny proces biznesowy, czyli rezerwację wizyty. Kolejnym krokiem było doprecyzowanie scenariuszy alternatywnych, szczególnie tych związanych z płatnością online.

W pierwszym etapie zidentyfikowano aktorów i przypadki użycia. Określono, że z systemu korzystają między innymi pacjent, administrator, personel medyczny, zewnętrzna bramka płatności oraz system powiadomień. Następnie opisano główny proces rezerwacji wizyty: od wyszukania lekarza, przez wybór dostępnego terminu, po ewentualną płatność i potwierdzenie wizyty.

Szczególną uwagę poświęcono scenariuszom alternatywnym, takim jak brak dostępnych terminów, wymagana przedpłata, brak konieczności przedpłaty, płatność zaakceptowana, płatność odrzucona oraz anulowanie wizyty. Następnie doprecyzowano odpowiedzialności poszczególnych elementów systemu, czyli obsługę rezerwacji, harmonogramów, płatności, powiadomień i danych pacjentów.

Na końcu uzgodniono wspólny słownik pojęć domenowych. Do najważniejszych pojęć zaliczono pacjenta, lekarza, wizytę, termin dostępności, płatność oraz powiadomienie. Dzięki temu możliwe było dobranie odpowiednich diagramów UML do poszczególnych aspektów systemu.

### 1. Diagram przypadków użycia — zakres funkcjonalny systemu

Jako pierwszy został przygotowany diagram przypadków użycia, ponieważ najlepiej pokazuje system z perspektywy użytkowników i interesariuszy. Diagram ten odpowiada na pytania: kto korzysta z systemu, jakie funkcje są dostępne, jakie są relacje między przypadkami użycia oraz które funkcje są obowiązkowe, a które opcjonalne.

W projekcie MediVisit diagram przypadków użycia pozwolił wskazać głównych aktorów: pacjenta, administratora, personel medyczny, bramkę płatności oraz system powiadomień. Głównym przypadkiem użycia jest rezerwacja wizyty. Płatność online nie zawsze jest obowiązkowa, dlatego została zamodelowana jako rozszerzenie przypadku użycia rezerwacji wizyty za pomocą relacji `<<extend>>` z warunkiem przedpłaty.

Diagram przypadków użycia był potrzebny, ponieważ określa zakres systemu i stanowi punkt wyjścia dla pozostałych diagramów.

### 2. Diagram aktywności — przebieg procesu biznesowego

Po określeniu przypadków użycia przygotowano diagram aktywności, aby pokazać przepływ procesu rezerwacji wizyty krok po kroku. Diagram ten pokazuje kolejne działania wykonywane przez pacjenta i system, miejsca podejmowania decyzji oraz możliwe ścieżki alternatywne.

Diagram aktywności porządkuje logikę procesu: wyszukanie lekarza, wybór dostępnego terminu, sprawdzenie dostępności, tymczasową blokadę terminu, decyzję o wymaganej przedpłacie, obsługę płatności, utworzenie wizyty oraz wysłanie potwierdzenia. Dzięki temu można było jasno przedstawić zarówno ścieżkę sukcesu, jak i sytuacje wyjątkowe, na przykład brak dostępności terminu lub odrzucenie płatności.

### 3. Diagram sekwencji — komunikacja między uczestnikami procesu

Następnie przygotowano diagram sekwencji, ponieważ diagram aktywności pokazuje proces ogólnie, ale nie wskazuje dokładnie, który uczestnik wysyła komunikat do którego komponentu i w jakiej kolejności.

Diagram sekwencji pokazuje komunikację między pacjentem, portalem pacjenta, systemem rezerwacji, bramką płatności oraz modułem powiadomień. Pozwala doprecyzować, kiedy pacjent wybiera termin, kiedy system tworzy tymczasową rezerwację, kiedy tworzona jest sesja płatności, jak bramka płatności zwraca wynik oraz kiedy system potwierdza wizytę i wysyła powiadomienie.

Szczególnie ważne było pokazanie fragmentu alternatywnego `alt`, w którym rozdzielono dwa przypadki: płatność zaakceptowaną oraz płatność odrzuconą. Dzięki temu uniknięto błędu logicznego, w którym potwierdzenie wizyty mogłoby zostać wysłane również po nieudanej płatności.

### 4. Diagram klas — model domenowy systemu

Kolejnym krokiem było przygotowanie diagramu klas, ponieważ po opisaniu procesu trzeba było zdefiniować najważniejsze obiekty domenowe i ich relacje. Diagram klas pokazuje, jakie dane są przechowywane w systemie oraz jak powiązane są ze sobą najważniejsze pojęcia domenowe.

W projekcie MediVisit wyróżniono między innymi klasy: pacjent, lekarz, placówka, termin dostępności, wizyta, płatność oraz powiadomienie. Diagram klas pozwolił powiązać proces biznesowy z modelem danych. Na przykład tymczasowa rezerwacja terminu została odzwierciedlona przez odpowiedni status wizyty oraz status terminu dostępności.

Takie rozwiązanie jest spójne z diagramem sekwencji i diagramem aktywności, ponieważ system najpierw blokuje termin, a dopiero po wyniku płatności potwierdza wizytę albo zwalnia termin.

### 5. Diagram maszyny stanów — cykl życia wizyty

Następnie przygotowano diagram maszyny stanów, ponieważ klasa reprezentująca wizytę ma wyraźny cykl życia. Sam diagram klas pokazuje strukturę danych, ale nie pokazuje, jak zmienia się status wizyty w czasie.

Diagram maszyny stanów przedstawia możliwe stany wizyty, takie jak nowa rezerwacja, oczekiwanie na płatność, wizyta potwierdzona, płatność nieudana, wizyta anulowana, wizyta w trakcie oraz wizyta zakończona. Diagram ten pokazuje również zdarzenia powodujące przejścia między stanami, na przykład zaakceptowanie płatności, odrzucenie płatności, rozpoczęcie wizyty, zakończenie wizyty lub anulowanie wizyty.

Ten diagram jest szczególnie ważny, ponieważ łączy się z modelem klas oraz z logiką płatności przedstawioną na diagramie sekwencji.

### 6. Diagram komponentów — logiczna architektura rozwiązania

Ostatnim diagramem był diagram komponentów, ponieważ po opisaniu zakresu funkcjonalnego, procesu, interakcji, modelu domenowego i cyklu życia wizyty należało pokazać logiczną strukturę rozwiązania.

Diagram komponentów pokazuje główne elementy systemu oraz zależności między nimi. W projekcie wyróżniono między innymi portal pacjenta, panel recepcji, usługę kont użytkowników, usługę rezerwacji, usługę harmonogramów, usługę płatności, usługę powiadomień, zewnętrzną bramkę płatności, zewnętrzny serwis e-mail/SMS oraz bazy danych wizyt i pacjentów.

Ten diagram był potrzebny, aby pokazać, że system nie jest monolitycznym blokiem, ale składa się z logicznych komponentów o jasno rozdzielonych odpowiedzialnościach. Usługa rezerwacji pełni rolę komponentu orkiestrującego proces rezerwacji, natomiast płatności, harmonogramy, konta użytkowników i powiadomienia są obsługiwane przez wyspecjalizowane komponenty.

### Dlaczego nie wybrano innych diagramów?

Nie wszystkie diagramy UML były potrzebne w tym projekcie. Nie wybrano diagramu wdrożenia, ponieważ projekt skupia się na analizie funkcjonalnej i logicznym opisie systemu, a nie na fizycznym rozmieszczeniu aplikacji na serwerach, środowiskach lub kontenerach.

Nie wybrano osobnego diagramu komunikacji, ponieważ jego rolę wystarczająco spełnia diagram sekwencji, który lepiej pokazuje kolejność komunikatów w czasie. Nie wybrano również diagramu obiektów, ponieważ diagram klas wystarczająco dobrze opisuje strukturę domenową systemu, a pojedyncze przykładowe instancje obiektów nie były konieczne do zrozumienia procesu. Nie przygotowano także diagramu pakietów, ponieważ projekt nie wymagał szczegółowego podziału modelu na pakiety.

### Logika doboru diagramów

Dobór diagramów wynikał z potrzeby pokazania systemu na kilku poziomach abstrakcji:

- diagram przypadków użycia pokazuje, co system ma robić i dla kogo,
- diagram aktywności opisuje przebieg procesu biznesowego,
- diagram sekwencji pokazuje komunikację uczestników i komponentów w czasie,
- diagram klas przedstawia główne obiekty domenowe i dane,
- diagram maszyny stanów pokazuje, jak zmienia się stan wizyty,
- diagram komponentów przedstawia logiczną architekturę rozwiązania.

Każdy diagram odpowiada na inne pytanie, ale razem tworzą spójny model systemu MediVisit.

### Podsumowanie

Wybrane diagramy zostały dobrane celowo, ponieważ projekt MediVisit wymagał pokazania perspektywy użytkownika, procesu biznesowego, komunikacji między elementami systemu, modelu danych, cyklu życia wizyty oraz logicznej architektury systemu.

Na początku analiza skupiła się na wymaganiach użytkowników i głównym procesie rezerwacji wizyty. Następnie doprecyzowano scenariusze alternatywne, w szczególności płatność online, brak dostępnych terminów, anulowanie wizyty i wysyłkę powiadomień.

Dzięki temu powstał zestaw sześciu diagramów UML, które wzajemnie się uzupełniają i opisują system MediVisit w sposób spójny:

1. diagram przypadków użycia,
2. diagram aktywności,
3. diagram sekwencji,
4. diagram klas,
5. diagram maszyny stanów,
6. diagram komponentów.

---

### Diagramy UML — PL

Diagramy są przygotowane w dwóch formatach:

- **PNG** — podgląd bezpośrednio na GitHubie,
- **draw.io** — plik do otwarcia w diagrams.net / draw.io.

| Diagram | Podgląd PNG | Plik draw.io |
|---|---|---|
| Diagram przypadków użycia | [PNG](diagrams/png/pl/01_diagram_przypadkow_uzycia.png) | [draw.io](diagrams/drawio/pl/01_diagram_przypadkow_uzycia.drawio.zip) |
| Diagram aktywności | [PNG](diagrams/png/pl/02_diagram_aktywnosci.png) | [draw.io](diagrams/drawio/pl/02_diagram_aktywnosci.drawio.zip) |
| Diagram sekwencji | [PNG](diagrams/png/pl/03_diagram_sekwencji.png) | [draw.io](diagrams/drawio/pl/03_diagram_sekwencji.drawio.zip) |
| Diagram klas | [PNG](diagrams/png/pl/04_diagram_klas.png) | [draw.io](diagrams/drawio/pl/04_diagram_klas.drawio.zip) |
| Diagram stanów | [PNG](diagrams/png/pl/05_diagram_stanow.png) | [draw.io](diagrams/drawio/pl/05_diagram_stanow.drawio.zip) |
| Diagram komponentów | [PNG](diagrams/png/pl/06_diagram_komponentow.png) | [draw.io](diagrams/drawio/pl/06_diagram_komponentow.drawio.zip) |

#### Podgląd — diagram aktywności

![Diagram aktywności](diagrams/png/pl/02_diagram_aktywnosci.png)

---

## 🇬🇧 English version

### Project purpose

**MediVisit** is a sample online medical appointment booking system. It allows patients to book appointments online and supports a healthcare provider in managing doctor availability, appointments, payments and notifications.

The project demonstrates the work of a Business Analyst / IT Business Analyst: process identification, actors, use cases, system interactions, domain model, object lifecycle and logical solution components.

### Business problem

The healthcare provider handles a large part of appointment booking through phone calls, e-mail and reception desk operations. This causes availability errors, delayed confirmations, limited change history and difficulty handling prepayments for selected services.

The target solution digitizes the appointment booking process, reduces manual work and provides the patient with a clear flow for selecting a slot, completing payment and receiving confirmation.

### Scope of analysis

**In scope:**

- searching for a doctor and available appointment slot,
- booking, changing and cancelling appointments,
- temporary slot reservation,
- online payment handling for appointments requiring prepayment,
- confirmation and reminder notifications,
- basic management of doctor schedules and users.

**Out of scope:**

- full electronic medical records,
- e-prescriptions,
- video consultations,
- full accounting and invoicing,
- integrations with public healthcare systems.

### Key business rules

- An appointment can be confirmed only after successful payment if prepayment is required.
- If payment is declined or times out, the temporarily held slot is released.
- If prepayment is not required, the appointment can be confirmed immediately after booking.
- A patient receives an appointment confirmation after successful booking.
- A cancelled appointment may trigger a cancellation notification.
- A doctor can have multiple availability slots.
- One availability slot can be reserved by at most one appointment.

### Assumptions

- The system supports both patients and reception staff.
- Online payment is optional and depends on whether prepayment is required for a given appointment.
- Payment processing is handled by an external payment gateway.
- Notifications are delivered through an external e-mail/SMS service.
- Appointment slots are temporarily held during the payment process.
- The component diagram presents logical architecture, not physical deployment.

### UML diagram selection rationale

At the beginning of the MediVisit project, the main need was to describe the process of booking a medical appointment with optional online payment. The scope of the system was not limited only to selecting an appointment slot. It also included searching for a doctor, checking slot availability, creating a booking, handling payment, confirming the appointment, sending notifications and handling exceptional cases such as declined payment, cancellation or unavailable slots.

The main user needs were identified first. The patient should be able to search for a doctor, check available slots and book an appointment. In some cases, the patient may be required to make an online prepayment. The system should confirm the appointment after successful payment, release the slot if payment fails and send an e-mail or SMS notification to the patient. Additionally, the administrator and medical staff should be able to manage users and doctor schedules.

Based on this, it was clear that a single diagram would not be enough to describe the system properly. Each UML diagram presents the system from a different perspective. Therefore, a set of diagrams was selected to describe functional requirements, business process flow, communication between participants, data structure, appointment lifecycle and logical architecture.

### Analysis process

The analysis was carried out step by step. First, the focus was on understanding who uses the system and what goals each user wants to achieve. Then, the main business process — appointment booking — was analysed. The next step was to refine alternative scenarios, especially those related to online payment.

In the first stage, actors and use cases were identified. The system users and external participants include the patient, administrator, medical staff, external payment gateway and notification system. Then, the main appointment booking process was described: from searching for a doctor, through selecting an available slot, to optional payment and appointment confirmation.

Special attention was given to alternative scenarios, such as unavailable slots, required prepayment, no prepayment required, payment accepted, payment declined and appointment cancellation. Then, the responsibilities of system elements were clarified, including booking, scheduling, payments, notifications and patient data handling.

Finally, a common domain vocabulary was defined. The key domain concepts included patient, doctor, appointment, availability slot, payment and notification. This made it possible to select the appropriate UML diagrams for different aspects of the system.

### 1. Use Case Diagram — functional scope

The use case diagram was prepared first because it best shows the system from the perspective of users and stakeholders. It answers questions such as who uses the system, what functions are available, what relationships exist between use cases and which functions are mandatory or optional.

In MediVisit, the use case diagram identifies the main actors: patient, administrator, medical staff, payment gateway and notification system. The main use case is booking an appointment. Online payment is not always mandatory, so it was modelled as an extension of appointment booking using the `<<extend>>` relationship with a prepayment condition.

The use case diagram was needed because it defines the system scope and serves as the starting point for the remaining diagrams.

### 2. Activity Diagram — business process flow

After defining the use cases, the activity diagram was prepared to show the appointment booking process step by step. It presents the actions performed by the patient and the system, decision points and possible alternative paths.

The activity diagram organises the process logic: searching for a doctor, selecting an available slot, checking availability, temporarily holding the slot, deciding whether prepayment is required, handling payment, creating the appointment and sending confirmation. This makes it possible to clearly show both the success path and exception paths, such as unavailable slots or declined payment.

### 3. Sequence Diagram — communication between process participants

The sequence diagram was prepared next because the activity diagram shows the process at a general level, but does not show exactly which participant sends a message to which component and in what order.

The sequence diagram presents communication between the patient, patient portal, booking system, payment gateway and notification module. It clarifies when the patient selects a slot, when the system creates a temporary booking, when the payment session is created, how the payment gateway returns the result and when the system confirms the appointment and sends the notification.

A particularly important part was the `alt` fragment, which separates two cases: payment accepted and payment declined. This prevents a logical error where appointment confirmation could be sent after failed payment.

### 4. Class Diagram — domain model

The class diagram was prepared after describing the process because it was necessary to define the key domain objects and their relationships. The class diagram shows what data is stored in the system and how the main domain concepts are related.

In MediVisit, the main classes include patient, doctor, facility, availability slot, appointment, payment and notification. The class diagram connects the business process with the data model. For example, temporary slot reservation is reflected through the appointment status and availability slot status.

This solution is consistent with the sequence and activity diagrams because the system first holds the slot and then, depending on the payment result, either confirms the appointment or releases the slot.

### 5. State Machine Diagram — appointment lifecycle

The state machine diagram was prepared because the appointment object has a clear lifecycle. The class diagram shows the data structure, but it does not show how the appointment status changes over time.

The state machine diagram presents possible appointment states, such as new booking, pending payment, confirmed, payment failed, cancelled, in progress and completed. It also shows events that trigger transitions between states, such as payment accepted, payment declined, appointment started, appointment completed or appointment cancelled.

This diagram is especially important because it connects with the class model and with the payment logic shown in the sequence diagram.

### 6. Component Diagram — logical solution architecture

The final diagram was the component diagram. After defining the functional scope, process flow, interactions, domain model and appointment lifecycle, it was necessary to show the logical structure of the solution.

The component diagram shows the main system components and their dependencies. In this project, the components include patient portal, reception panel, user account service, booking service, schedule service, payment service, notification service, external payment gateway, e-mail/SMS service, appointment database and patient database.

This diagram was needed to show that the system is not a single monolithic block, but consists of logical components with clearly separated responsibilities. The booking service orchestrates the appointment booking process, while payments, schedules, user accounts and notifications are handled by specialised components.

### Why other diagrams were not selected

Not all UML diagrams were needed in this project. The deployment diagram was not selected because the project focuses on functional analysis and logical system description, not on physical deployment to servers, environments or containers.

A separate communication diagram was not selected because its role is sufficiently covered by the sequence diagram, which better shows the order of messages over time. The object diagram was also not selected because the class diagram sufficiently describes the domain structure, and individual sample object instances were not necessary to understand the process. A package diagram was not prepared because the project did not require a detailed division of the model into packages.

### Diagram selection logic

The selection of diagrams resulted from the need to present the system at several levels of abstraction:

- the use case diagram shows what the system should do and for whom,
- the activity diagram describes the business process flow,
- the sequence diagram shows communication between participants and components over time,
- the class diagram presents the main domain objects and data,
- the state machine diagram shows how the appointment state changes,
- the component diagram presents the logical architecture of the solution.

Each diagram answers a different question, but together they create a consistent model of the MediVisit system.

### Summary

The selected diagrams were chosen intentionally because MediVisit required showing the user perspective, business process, communication between system elements, data model, appointment lifecycle and logical system architecture.

At the beginning, the analysis focused on user requirements and the main appointment booking process. Then, alternative scenarios were refined, especially online payment, unavailable slots, appointment cancellation and notification sending.

As a result, a set of six UML diagrams was created. These diagrams complement each other and describe the MediVisit system in a consistent way:

1. use case diagram,
2. activity diagram,
3. sequence diagram,
4. class diagram,
5. state machine diagram,
6. component diagram.

---

### UML diagrams — EN

The diagrams are prepared in two formats:

- **PNG** — direct GitHub preview,
- **draw.io** — source file for diagrams.net / draw.io.

| Diagram | PNG preview | draw.io file |
|---|---|---|
| Use case diagram | [PNG](diagrams/png/en/01_use_case_diagram.png) | [draw.io](diagrams/drawio/en/01_use_case_diagram.drawio.zip) |
| Activity diagram | [PNG](diagrams/png/en/02_activity_diagram.png) | [draw.io](diagrams/drawio/en/02_activity_diagram.drawio.zip) |
| Sequence diagram | [PNG](diagrams/png/en/03_sequence_diagram.png) | [draw.io](diagrams/drawio/en/03_sequence_diagram.drawio.zip) |
| Class diagram | [PNG](diagrams/png/en/04_class_diagram.png) | [draw.io](diagrams/drawio/en/04_class_diagram.drawio.zip) |
| State machine diagram | [PNG](diagrams/png/en/05_state_machine_diagram.png) | [draw.io](diagrams/drawio/en/05_state_machine_diagram.drawio.zip) |
| Component diagram | [PNG](diagrams/png/en/06_component_diagram.png) | [draw.io](diagrams/drawio/en/06_component_diagram.drawio.zip) |

#### Preview — activity diagram

![Activity diagram](diagrams/png/en/02_activity_diagram.png)

---

## Repository structure

```text
clinic-appointment-system-uml-ba-case/
├── README.md
└── diagrams/
    ├── png/
    │   ├── pl/
    │   └── en/
    └── drawio/
        ├── pl/
        └── en/
```

## Skills demonstrated

- Business Analysis,
- IT Business Analysis,
- UML modelling,
- use case modelling,
- process modelling,
- sequence modelling,
- domain modelling,
- state modelling,
- component modelling,
- business rules definition,
- requirements structuring,
- logical architecture modelling,
- bilingual PL/EN documentation.
