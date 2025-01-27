# Rozdziały
1. Wstęp
    - 1.1 opis z jakimi problemami musi się zmagać operator sieci telco (https://www.ericsson.com/en/blog/2019/4/what-is-closed-loop-automation)
      - sekcja, która: przedstawi dziedzinę (Telekomunikacja), przedstawi motywację do podjęcia tematu (aktualność zagadnienia, znaczenie, rozówj technologiczny, konkretny problem), wskaże lukę badawczą lub problem (brak narzędzia do modelowania i uruchamiania pętli pokazanych przez ENI)
      - sekcja, która: jasno określi co praca ma osiągnąć (jaki jest cel), znaczenie pracy, jakie problemy rozwiązuje, kto może z niej skorzystać
      - sekcja, która: przedstawi zakres, czego ona dotyczy a czego nie
   - 1.2 Opis następnych sekcji i załączników
2. **Stan wiedzy**
   - 2.1 background skąd się wzięła praca	czyli odniesienia do ENI
     - krótki opis ENI
     - krótki opis pętli przedstawionych w [Overview of Prominent Control Loop Architectures](https://www.etsi.org/deliver/etsi_gr/ENI/001_099/017/02.01.01_60/gr_ENI017v020101p.pdf)

3. **Architektura**
   - 3.1 Wstęp
       - 3.1.1 Wymagania i Założenia na platformę
   - 3.2 Krótki wstęp czym jest w odniesieniu do pojęć z 2.1 oraz, że w oparciu o Kubernetes
     - Tak jak tu [readme#intro](https://github.com/0x41gawor/lupus?tab=readme-ov-file#lupus)
     - Architektura w odniesieniu do 2.1 
     - Tak jak tu [top-level-arch.png](https://github.com/0x41gawor/lupus/blob/master/_img/readme/1.png)
   - 3.4 Podstawowe pojęcia i zasady 
     - Tak jak tu: [detailed-docs](https://github.com/0x41gawor/lupus/blob/master/docs/detailed-docs.md)
     - Odniesienia do [definitions](https://github.com/0x41gawor/lupus/blob/master/docs/defs.md), które będą w załączniku
     - Odniesienia do pełnych specyfikacji [specs/](https://github.com/0x41gawor/lupus/tree/master/docs/spec), które będą w załącznikach
     - Tu też daj Open Policy Agent
   - 3.5 Krótka instrukcja jak używać
     - Może opis jak tu: [Getting-Started](https://github.com/0x41gawor/lupus/blob/master/docs/getting-started.md)
     - A może same potrzebne kroki jak tu: [readme#how-to-use-it](https://github.com/0x41gawor/lupus/tree/master?tab=readme-ov-file#how-to-use-it)
     > Architektura wg. definicji ENI -> "set of rules and methods that describe the functionality, organization, and implementation of a system"
4. **Implementacja**
   - 4.1 Wstęp
   - 4.2 Mechanizmy stojące za Lupus
     - Opis [controller](https://kubernetes.io/docs/concepts/architecture/controller/) w Kubernetes na built-in resources
     - Opis [CRD](https://kubernetes.io/docs/tasks/extend-kubernetes/custom-resources/custom-resource-definitions/) i [OperatorPattern](https://kubernetes.io/docs/concepts/extend-kubernetes/operator/)
     - Opis platformy [Kubebuilder](https://book.kubebuilder.io)
       - Koniecznie architektura oraz flow controllera (operatora)
   - 4.3 Decyzje podjęte podczas developmentu (każda wynikająca z wymagań następnie opis implementacji)
     - To tu objawia się badawcza natura pracy
     - [Komunikacja pomiędzy lupus-elements](https://github.com/0x41gawor/lupus/blob/master/docs/com-bet-lup-ele.md)
     - [Data](https://github.com/0x41gawor/lupus/blob/master/docs/spec/data.md)
     - [Actions](https://github.com/0x41gawor/lupus/blob/master/docs/spec/actions.md)
     - [Polimorfizm w LupN](https://github.com/0x41gawor/lupus/blob/master/docs/go-style-polymorphism.md)
     - [2 workflows](https://github.com/0x41gawor/lupus/blob/master/docs/2-workflows.md)
     - [Open Policy Agents](https://github.com/0x41gawor/lupus/blob/master/docs/open-policy-agents.md)
     - [User-functions](https://github.com/0x41gawor/lupus/blob/master/docs/user-functions.md)
     - Może historia zmian w developmencie? Jak to się zmieniało na przestrzeni sprintów. Tak jak tu: [journal.md](https://github.com/0x41gawor/lupus/blob/master/journal.md) to raczej inny rozdział niż implementacja. Może architektura? Napisz go oddzielnie 
5. **Test platformy na Open5GS**
    - 5.1 Wstęp
    - 5.2 Opis podobny jak w [examples/open5gs](https://github.com/0x41gawor/lupus/tree/master/examples/open5gs), jednocześnie stanowiący walk-through guide dla usera na żywym przykładzie, krok po kroku, cały kod Ingress-Agent, LupN, Egress-Agent, rysunek workflow i przepływ Date'y w załącznikach.
6. **Wnioski**
   - Co się udało a co nie, czy nadaje się to do użycia itp.
   - Co można poprawić
   - Dalszy rozwój

**Załącznik 1 - definicje**

- [defs.md](https://github.com/0x41gawor/lupus/blob/master/docs/defs.md)

**Załącznik 2 - specyfikacja interfejsów Lupin i Lupout**

- [lupin-lupout.md](https://github.com/0x41gawor/lupus/blob/master/docs/spec/lupin-lupout.md)

**Załącznik 3 - specyfikacja notacji LupN**

- [LupN](https://github.com/0x41gawor/lupus/blob/master/docs/spec/lupn.md)

**Załącznik 4 - Open5GS**

- Wszelki kody źródłowe i rysunki związane z testem na Open5GS