# Logika
## Bevezetés

- Állítások amikhez egyértelműen igaz vagy hamis értéket tudunk rendelni
    - egyedre, vagy egyedekből álló csoportra
    - egyszerű konkrét állítások
    - elsőrendű logikában ilyeneket tudunk megfoglamazni

## Alapfogalmak

- **Halmazok direktszorzata (Descartes szorzat)**
    - A x B ...
- **Függvény**
    - D, R halmaz ekkor D -> R leképezést függvénynek nevezzük
    - D az ÉT, R az ÉK
    - Fajtái:
        - D = U, **egyváltozós**
        - D = U^n (n > 1), akkor **n változós**
        - R = N (N mint természetes számok) **egészértékű**
        - R = {i, h} **logikai fv.** vagy **reláció**
        - D = R^n (U^n -> U), **művelet** vagy **matematikai fv.**
        - {i, h}^n -> {i, h} **logikai művelet**
- **Szerkezeti rekurzió**
    - definiciós módszer
    - alaplépés + rekurzív lépés
- **Szerkezeti indukció**
    - alaplépés + indukciós lépés
    - pl.: Teljes ind.
- **Gondolkodás- vagy következtetésforma**
    - F = {A1, A2, ... , An} állításhalmazból és egy A állításból álló (F, A) pár
- **Helyes köztesforma**
    - F = {A1, A2, ... , An} állításhalmazból és egy A állításból álló (F, A) pár
        ha létezik olyan eset, hogy F-ben minden állítás igaz és ekkor A is igaz

## Ítéletlogika (állításlogika)

- **Nyelv def**.:
    - Nyelv = abc + szintaxis + szemantika
- Állítás
    - **Egyszerű állítás**
        - Olyan kijelentés amelynek tartalmáról eldönthető, hogy igaz vagy hamis-e.
    - **Összetett állítás**
        - Egyszerű állításokból álló összetett mondat, amelynek igazságértéke az egyszerű állításoktól függ.
        - Csak olyan összekötő szavakat tartalmazhat amik logikai műveletnek megfeleltethetőek.

### Ítéletlogika nyelvének abc-je

- Ítéletváltozók (X, Y, Xi, ...)
- Unér logikai műveleti jel: negáció
- Binér logikai műveleti jelek:
    - konjunkció
    - diszjunkció
    - implikáció
- Elválasztó jelek: () (konkrétan a zátójel)

### Ítéletlogika nyelvének szintaxisa

- **Formula**
    1. alaplépés: minden ítéletváltozó ítéletlogikai formula.
    2. rekurzív lépés
        - Ha A ítéletlogikai formula, akkor neglált A is
        - Ha A és B -||-, akkor (A o B) is
    3. Minden [...] formula az 1,2 szabályok véges sokszori alkalmazásával áll elő

**Zárójelezés komolyan van véve**

- **Formula szerkezetek**
    - negációs (¬A)
    - konjukciós (A && B)
    - diszjunkciós (A || B)
    - implikációs (A ⊃ B)

**Összetettnél mindig a legkülső alapján van elnevezve**

- **Közvetlen részformula**
    1. Prímformulának nincs közvetlen részformulája
    2. ¬A közvetlen részformulája A
    3. (A o B) közvetlen részformulái A és B
- **Szerkezeti fa**
    - Gyökere formula
    - Minden csúcs közvetlen részformula
- **Szintaxis fa**
    - gyökere a formula fő logikai összekötője
    - csúcs gyerekei pedig a részformulák fő logikai összekotői
    - fa levelei pedig ítéletváltozók
- **Zárójelelhagyás**
    - Ha bevezetjük a műveleti priorítást
    - Szerkezet megtartása
- **Műveletek priorítása**
    - ¬, &&, ||, ⊃
- **Literál**
    - Ha X ítéletváltozó, akkor X és ¬X formulákat literálnak nevezzük
- **Elemi konjunckció**
    - Kül. literálok konjukciója
- **Elemi diszj.**
    - -||- diszjunkciója
- **Logikai összetettség**
    - l(A) = 0,
    - l(¬A) = l(A) + 1
    - l(AoB) = l(A) + l(B) + 1
- **Műveletek hatásköre, Fő logikai összekötőjele**

### Ítéletlogika nyelvének szemantikája (értelmezés, interpretáció)

- **Igazságkiértékelés, interpretáció**
    - I = Vv ⊃ {i, h}
- **Szemantikus fa**
    - összes lehetséges interpretáció szűrése
- **Formula helyettesítési értéke**
- **Formula igazságtáblája**
- **Gamma-igazságértékelés fv.**
    - gamma(A)^i azok az I interpret. teljesítik ahol I(A) = i
    - gamma(A)^h azok az I interpret. teljesítik ahol I(A) = h

### Formulák, Formulahalmazok szem. tul.

#### Formulák

- **Interpretáció kielégít egy formulát**
- **Kielégíthetőség / kielégíthetetlenség / tautológia**

#### Formulahalmazok

- **Interpretáció kielégít egy formulahalmazt**
- **Kielégíthetőség / kielégíthetetlenség**
- **Szemantikus köv.**

## Szemantikus köv. fogalma

- **|=₀** G szemantikus, vagy tautológikus köv. F = {F1, F2, ..., Fn}-nek, ha minden interpr. I |=₀ {F1, F2, ..., Fn}, és I |=₀ G
- F |=₀ G1 és F |=₀ G2 és {G1, G2} |=₀ A akkor F |=₀ A
- **Eldöntésprobléma**
    - (F, G) pár szemantukus következményfogalom szerint helyes gondolkodásforma-e.
    - **Tétel** F (formulahalmaz) akkor és csak akkor következménye G, ha FU¬G formulahalmaz, vagy F1 && F2 && ... && Fn && ¬G formula kielégíthetetlen
    - **Tétel (dedukciós)** {F1, F2, ..., Fn} |=₀ G akkor és csak akkor, ha {F1, F2, ..., Fn-1} |=₀ (Fn ⊃ G)
    - **Tétel (eldöntésprobléma)** {F1, F2, ..., Fn} |=₀ G akkor és csak akkor, ha |=₀ F1⊃(F2⊃...(Fn-1⊃(Fn⊃G))...)

## Tautologikusan ekvivalens

- **Def.**
    - ~₀: két vagy több formula igazságtáblája ugyanaz
    - A és B tautologikusan ekvivalens, ha A |=₀ B és B |=₀ A, ekkor |=₀ (A⊃B) && (B⊃A)
- **Átalakítási szabályok**
    - X ⊃ Y ~₀ ¬X ∨ Y
    - ¬¬X ~₀ X
    - De Morgan szabályok:
        1. ¬(X ∧ Y ) ~₀ ¬X ∨ ¬Y
        2. ¬(X ∨ Y ) ~₀ ¬X ∧ ¬Y
    - Egyszerűsítési szabályok:
        1. (X ∨ d) ∧ (¬X ∨ d) ~₀ d
        2. (X ∧ k) ∨ (¬X ∧ k) ~₀ k
            -ahol d elemi diszjunkció és k elemi konjunkció.

## Formalizálás

- **Az egyszerű kijelentő mondatok formalizálására bevezetűnk egy azonosítót**
- **Az össszetett mondatokat átalakítjuk azonos értelmű kijelentésekre, amiket logikai összekötőkkel kötünk**
- Pl.: Ha férfi a tettes (F), akkor kistermetű (K). F ⊃ K

## Elsőrendű logika

Ha a logikai kijelentő mondat alanya konkrét dolog, akkor az állítás nulladrendű
Ha a logikai kij. mondat alanya halmaz akkor az állítás elsőrendű

- **Definíció**
    - (U, R, M, K) halmaznégyes
        - U: nem üres halmaz, struktúra ÉT-je
        - R: az U-n értelmezett n-változós logikai függvények (alaprelációk) halmaza
        - M: az U-n értelmezett n-változós matematikai függvények halmaza
        - K: az U megjelölt elemeinek egy részhalmaza
    - struktúra szignatúrája megadja az alaprelációk és alapműveletek aritását, valamint K elemszámát

- **ABC-ben individumváltozók (x, y, yk, ...) és kvantorok is vannak**
- **A nyelv alkalmas kell, hogy legyen tetszőleges szignatúrájú matematikai struktúrák leírására.**
- **Egyféle elemből álló U esetén:**
    - L nyelv abc-je: (Pr, Fn, Cnst), szignatúrája: (v1, v2, v3)
        - Pr: predikátumszimbólumok halmaza, v1: P ∈ Pr-re megadja P aritását (k)
        - Fn: függvényszimbólumok halmaza, v2: f ∈ Fn-re megadja f aritását (k)
        - Cnst: konstansszimbólumok halmaza, v3: megadja a konstansok számát
- **Többféle elemből álló U esetén:**
    - L nyelv abc-je: (Srt, Pr, Fn, Cnst), szignatúrája: (v1, v2, v3)
        - Srt: nemüres, πj elemei fajtákat szimbolizálnak
        - Pr: predikátumszimbólumok halmaza, v1: P ∈ Pr-re megadja P aritását (k), és hogy milyen fajtájúak az egyes argumentumok
        - Fn: függvényszimbólumok halmaza, v2: f ∈ Fn-re megadja f aritását (k), -||-, valamint a fv. értéke
        - Cnst: konstansszimbólumok halmaza, v3: megadja a konstansok számát

### Elsőrendű logika szintaxisa

- nyelv kifejezései informálisan
    - **termek**: matematikai leképezéseket szimbolizálják
    - **formulák**: logikai leképezéseket szimbolizálják
- Egyfajtájú eset:
    - Termek
        1. (alaplépés) Minden individuumváltozó és konstans szimbólum term
        2. (rekurzív lépés) Ha az f ∈ Fn k-változós fv szimbólum és t1,...,tk termek, akkor f(t1,...,tk) is term.
        - Minden term 1, 2 szabályok véges alkalmazásával áll elő
    - Formulák
        1. (alaplépés) Ha a P ∈ Pr k-változós predikátumszimbólum és t1,..., tk termek akkor P(t1,..., tk) formula.
        2. (rekurzív lépés)
            - Ha A formula akkor ¬A is az.
            - Ha A és B formulák, akkor (A o B) is formula, ahol o a három binér művelet egyike
        3. Ha A formula, akkor ∀xA és ∃xA is az.
        - Minden formula az 1, 2, 3 szabályok véges sokszori alkalmazásával áll elő
- Többfajtájú eset
    - Termek
        1. (alaplépés) Minden π ∈ Srt fajtájú individuumváltozó és konstans szimbolúm π fajtájú
        2. (rekurzív lépés) Ha az f ∈ F n (π1, π2, . . . , πk; πf ) fajtájú függvényszimbólum és t1, t2, . . . , tk rendre π1, π2, . . . , πk fajtájú termek, akkor f (t1, t2, . . . , tk) πf fajtájú term
    - Formulák
        1. (alaplépés)
            - [...]
- Formulaelnevezések (egyértelmű + kvantáltak)
- Fogalmak
    - () elhagyások
    - hatáskörök
    - komponens, **prímkomponens**
        - prímkomponensnek nevezzük azokat a prímformulákat, amelyekből a formula kizárólag a ¬, ∧, ∨, ⊃ műveletek segítségével épül fel.
    - fő műveleti jel
    - **Közvetlen részterm**
        - Az f (t1, t2, . . . , tk) term közvetlen résztermjei a t1, t2, . . . , tk termek.
    - **Közvetlen részformula**
        - ¬A => A
        - [...]
        - QxA (Q ∈ {∀, ∃}) => A
    - **Prímformula**
        - Egy atomi formula prímformula.
        - Egy QxA formula prímformula.
- **Term szerkezeti fája**
    - a gyökeréhez a t term van rendelve,
    - ha valamelyik csúcsához egy t′ term van rendelve, akkor az
    adott csúcs gyerekeihez a t′ term közvetlen résztermjei vannak
    rendelve,
    - leveleihez individuumváltozók vagy konstansok vannak rendelve.
- **Formula szerkezeti fája**
    - a gyökeréhez az F formula van rendelve,
    - ha valamelyik csúcsához egy F′ formula van rendelve, akkor
    az adott csúcs gyerekeihez az F′ formula közvetlen
    részformulái vannak rendelve,
    - leveleihez atomi formulák vannak rendelve.
- **Szabad/kötött**
    - Egy formulában egy x változó egy előfordulása
        - szabad, ha nem esik x-re vonatkozó kvantor hatáskörébe
        - kötött, ha x-re vonatkozó kvantor hatáskörébe esik
    - Egy x változó egy formulában
        - kötött változó, ha x minden előfordulása kötött
        - szabad változó, ha x minden előfordulása szabad
        - vegyes változó, ha x-nek van szabad és kötött előfordulása is
- **Zárt**
    - Egy formula zárt, ha minden változója kötött.
    - Egy formula nyitott, ha legalább egy individuumváltozónak
    van legalább egy szabad előfordulása.
    - Egy formula kvantormentes, ha nem tartalmaz kvantort
- Példák:
    - A formula: ∀xP (x) ⊃ ∃yQ(w, y) ∨ P (v) ⊃ ∀zQ(w, z)
    - A prímkomponensek: ∀xP (x), ∃yQ(w, y), P (v), ∀zQ(w, z)
    - A szabad individuumváltozók: v, w

### Elsőrendű logika szintaxisa

- **I interpretáció**
    - Az I interpretáció működése: I = 〈ISrt, IPr, IFn, ICnst〉függvénynégyes, ahol:
        - ISrt : π → Uπ , ahol ha Srt egyelemű, akkor az interpretáció U
        univerzuma egyfajtájú elemekből áll
        - az IPr : P → P^I , ahol P^I a struktúra R halmazázak egy eleme
        - az IFn : f → f^I , ahol f^I a struktúra M halmazának egy eleme
        - az ICnst : c → c^I , ahol c^I a struktúra K halmazának egy eleme
- Változókiértékelés
    - κ : V → U
- Változókiértékelés variánsa
    - κ∗(y) = κ(y)
- Termek szemantikája
    1. ha c konstansszimbólum, |c|I,κ az U -beli cI elem
    2. ha x individuumváltozó, |x|I,κ a κ(x) ∈ U elem
    (ahol κ egy változókiértékelés)
    3. |f (t1, t2, . . . , tn)|I,κ = f I ((|t1|I,κ, |t2|I,κ, . . . , |tn|I,κ))
- **Értéktáblájában** az első sorba a formula szabad változói, a prímkomponensek és a formula kerülnek

### Formulák, Formulahalmazok szem. tul.

- Az L egy I interpretációja adott κ változókiértékelés mellett kielégít egy 1. rendű A formulát (I, κ |= A) , ha a formula |A|I,κ értéke i.
- Azt mondjuk, hogy egy G formula kielégíthető ha L-hez van legalább egy I interpretáció és κ változókiértékelés, hogy I, κ |= G.
- Azt mondjuk, hogy F zárt formulahalmaz kielégíthető ha L-nek legalább egy I interpretációja kielégíti, azaz I |= F.
- Azt mondjuk, hogy egy G formula logikailag igaz (logikai törvény), ha G igaz minden lehetséges I interpretációra és minden κ változókiértékelésre
- zt mondjuk, hogy egy G formula tautológia, ha G értéktáblájában a prímkomponensekhez rendelhető összes lehetséges igazságérték hozzárendelés esetén a formula helyettesítési értéke i.
- Azt mondjuk, hogy G illetve F kielégíthetetlen (nem kielégíthető), ha L-hez nincs olyan I interpretáció, hogy I |= G illetve, hogy I |= F.

### Következményfogalom elsőrendű logikában

- Azt mondjuk, hogy a G formula logikai (szemantikus) következménye az F formulahalmaznak, ha minden olyan I interpretációra, amelyre I |= F teljesül, az I |= G is fennáll.
- Ha egy G formula bármely F feltételhalmaznak következménye, akkor G logikailag igaz.
- F-nek szemantikus következménye G, akkor és csak akkor, ha az F ∪ {¬G} kielégíthetetlen.
- Ha F-nek következménye G1 és F-nek következménye G2, valamint, {G1, G2}-nek következménye A, akkor az F-nek következménye A.
- Ha minden interpretáló struktúrában, a G a közös értéktáblának pontosan azokban a soraiban igaz, ahol F1, F2, . . . , Fn mindegyike igaz, akkor G a **legszűkebb következménye** F-nek.
- Az A és B elsőrendű formulák **logikailag ekvivalensek**, ha {A} |= B és {B} |= A.
- **Eldöntésprobléma tétel**: {F1, F2, . . . , Fn} |= G ⇐⇒ |= F1 ⊃ (F2 ⊃ (. . . ⊃ (Fn−1 ⊃ (Fn ⊃ G)) . . .)) (logikailag igaz).

## Tablókalkulus

**A tablókalkulus egy formula kielégíthetetlensének igazolására szolgáló szintaktikus kalkulus.**
- Jelölt/jelöletlen

### Ítéletlogikában

- Vezessük be a nyelvbe a T , F szimbólumokat. Jelölt formulának nevezzük a TA, FA kifejezéseket, ahol A jelöletlen formula. (Ezek olvasata TA – A igaz; FA - A hamis.) Egy interpretációban TA igaz, ha A igaz, és hamis, ha A hamis; és FA igaz, ha A hamis, és hamis, ha A igaz.
- Egy C ítéletlogikai formula analitikus tablója egy olyan bináris fa, melynek csúcsai „jelöletlen” ítéletlogikai formulák. A fa gyökere a C formula. Előállítjuk C közvetlen tablóját a táblázat alapján.
- A tabló egy ága zárt, ha megjelenik rajta egy már nem feldolgozható formula és annak a negáltja is.
- A tablókalkulus megállási feltétele, a tabló lezárása. Ha a tabló zárt, akkor azt mondjuk, hogy a formulának van tablócáfolata.
- Ha egy C formulának van tablócáfolata (tablója zárt), akkor C kielégíthetetlen.
- Ha C kielégíthetetlen, akkor T tablója zárt.
- **Hintikka halmaz**nak nevezünk egy formulahalmazt, ha lefele zárt és nem tartalmaz komplemens párt.
    - Egy H Hintikka halmaz kielégíthető.
    - A tabló egy nyitott ágán Hintikka halmaz áll elő, ami kielégíthető.

### Elsőrendű logikában

**∀xA =>  [A(x ‖ t)], ¬∃xA => ¬[A(x ‖ t)]** t tetszőleges term
**∃xA => A(x ‖ y), ¬∀xA => ¬A(x ‖ y)** y kritikus változó (megkötéssel)
- ∀xA és ¬∃xA – γ típusú (univerzális típus),
- ∃xA és ¬∀xA – δ típusú (egzisztenciális típus).

- Term: minden indivíduum változó és indivíduum paraméter.
- Formula:
    1. Ha P n-változós predikátumszimbólum, t1, . . . tn termek, akkor P(t1, . . . , tn ) formula (atomi formula)
    2. Ha A, B formulák, akkor ¬A és (A ◦ B) (◦ az {∧, ∨, ⊃} valamelyike) formulák.
    3. Ha A formula, akkor ∀xA és ∃xA formulák

- Ha az elsőrendű G formula tablója zárt, akkor G kielégíthetetlen.
    - *Bizonyítás: Tegyük fel, hogy G tablója zárt, de G kielégíthető egy σ0 interpretációban. Ebben az esetben G formula tablójának lesz legalább egy nyitott ága, amelynek miden formulája igaz a σ0 interpretációban. Tehát G is igaz. G tablója nem lehet zárt.*
- Egy U univerzum feletti elsőrendű Hintikka halmaznak nevezik azt az S formulahalmazt, amelyre fennállnak az alábbi tulajdonságok.
    - H0 Komplemens pár nem fordul elő benne. (U feletti atom és a negáltja)
    - H1 α ∈ S ⇒ α1 ∈ S és α2 ∈ S
    - H2 β ∈ S ⇒ β1 ∈ S vagy β2 ∈ S
    - H3 γ ∈ S ⇒ γ(k) ∈ S minden k ∈ U -ra
    - H4 δ ∈ S ⇒ δ(k) ∈ S legalább egy k ∈ U -ra
    - Minden az U feletti S Hintikka halmaz elsőrendben kielégíthető (az U felett).
- Ha az elsőrendű G formula kielégíthetetlen, akkor G tablója zárt.
    - *Bizonyítás: (indirekt) Tegyük fel, hogy G kielégíthetetlen, de G tablója nem zárt (van nyitott ága). Egy nyitott ágon Hintikka halmaz áll elő, ami kielégíthető és G is eleme. Tehát G nem lehet kielégíthetetlen.*
- G szisztematikus tablójának nevezzük azt a tablót, ahol a tablóépítési stratégia biztosítja, hogy minden teljes nyitott ágon Hintikka halmaz álljon elő, ahol U a kritikus paraméterek halmaza.
    - Az A, B, D szabályok végrehajtása, amíg lehet.
    - A C szabály végrehajtása, ahol a γ(a), γ formulák kerülnek be az ág végére.
- Löwenheim tétel
    - Ha G kielégíthető egyáltalán, akkor kielégíthető legfeljebb megszámlálható univerzumon.
    - *Bizonyítás: Legyen T a G befejezett szisztematikus tablója. Mivel G kielégíthető, a T -nek van nyitott ága. Egy nyitott ágon véges sok vagy megszámlálhatóan végtelen kritikus paraméter fordul elő. A kapott halmaz Hintikka halmaz, így a G is ezen a halmazon kielégíthető.*
- Kompaktsági tétel
    - Ha az S megszámlálható formulahalmaz minden véges részhalmaza kielégíthető, akkor S kielégíthető.

## Eldöntésprobléma megoldása szemantikai eszközökkel

- Elsőrendű n változós B formula logikailag igaz, ha
    - minden U univerzumon, a változók minden behelyettesítése mellett kapott B′ alapformulák igazak minden, a nyelvnek megfelelő struktúrában.
    - ¬B kielégíthetetlen. Egyetlen interpretációban sem igaz. Ezek a problémák szemantikailag világosak, de megoldásuk a teljes kipróbálást tételezi fel.

- Gödel bebizonyította, hogy ”A szemantikus eldöntésprobléma algoritmikusan nem oldható meg – nem létezik univerzális eldöntési algoritmus”.

- Kutatások ”eldönthető formulaosztályok” keresésére. Logikailag ekvivalens formulaátalakítások.
    - Az egyik, eldönthető formulaosztályokhoz tartozó formulákkal leírt szemantikus eldöntésproblémára kalkulus keresése (tabló rezolúciós elv).
    - A másik, a logika szintaktikai alapon való felépítése, szintaktikus eldöntésprobléma megadása és arra kalkulus kidolgozása.

## A logika szintaktikus tárgyalása

- Az ítéletlogika szintaktikai alapokon való felépítése az ítéletkalkulus.
- Az elsőrendű logika szintaktikai alapokon való felépítése a predikátumkalkulus vagy logikai függvénykalkulus.

- Ítéletlogika, mint matematikai struktúra: 〈{i, h}, ¬, ⊃〉
- Axiómák (axiómasémák): megadják a műveletek tulajdonságait.
- Az ítéletlogikai nyelvben itt a logikai összekötőjelekből csak a ¬, ⊃ párt használjuk (funkcionálisan teljes művelethalmaz).
- Axiómasémák – ítéletlogika
    - (A1) X ⊃ (Y ⊃ X )
    - (A2) (X ⊃ (Y ⊃ Z )) ⊃ ((X ⊃ Y ) ⊃ (X ⊃ Z ))
    - (A3) (¬X ⊃ Y ) ⊃ ((¬X ⊃ ¬Y ) ⊃ X )
- Az axiómák tautológiák/logikai törvények.
- Tétel: Legyen egy G formula, G(X | S) az a formula, amit G-ből X változójának egy S formulával való behelyettesítésével kaptunk. Ha G tautológia, akkor G(X | S) is az.
- **Tétel (modus ponens): {A ⊃ B, A} |=₀ B**

- Bizonyításelméleti levezetés fogalma
- G-nek F-ből való levezetése egy olyan ϕ1, ϕ2, . . . , ϕk , . . . , ϕn formulasorozat, amelynek utolsó formulája a G, ahol
    - ϕk ∈ F, vagy
    - ϕk -t axiómasémákból kaptuk, vagy
    - ϕk -t a levezetési szabállyal kaptuk ϕs, ϕt -ből (s, t < k), azaz ϕk = mp(ϕs, ϕt )
- Egy G formula az F = {F1, F2, . . . , Fn } formulahalmazból levezethető
(F = {F1, F2, . . . , Fn } |-₀ G), ha van G-nek F-ből való levezetése. Ez a szintaktikus következményfogalom.

- Az elsőrendű logika bizonyításelméleti felépítése: predikátumkalkulus.
- Axiómasémák – elsőrendű logika
    - (B1) A ⊃ (B ⊃ A)
    - (B2) (A ⊃ (B ⊃ C )) ⊃ ((A ⊃ B) ⊃ (A ⊃ C ))
    - (B3) (¬A ⊃ B) ⊃ ((¬A ⊃ ¬B) ⊃ A)
    - (B4) ∀xA ⊃ [A(x ‖ t)]
    - (B5) ∀x(A ⊃ B) ⊃ (∀xA ⊃ ∀xB)
    - (B6) A ⊃ ∀xA, ahol x 6 ∈ Par(A)
    - (B7) a (B1)–(B6) axiómák általánosításai

- Tétel: A bizonyításelméleti kalkulus helyes, azaz ha {F1, F2, . . . , Fn } |-₀ G, akkor {F1, F2, . . . , Fn } |=₀ G.
- Tétel: A bizonyításelméleti kalkulus teljes, azaz ha {F1, F2, . . . , Fn } |=₀ G, akkor {F1, F2, . . . , Fn } |-₀ G.
    - *Biz.: ítéletkalkulus esetén ld. később; predikátumkalkulus teljességét nem bizonyítjuk.*

- Tulajdonságok:
    - Egy G formula az F = {F1, F2, . . . , Fn } formulahalmazból levezethető (F = {F1, F2, . . . , Fn } |-₀ G), ha van G-nek F-ből való levezetése.
    - G bizonyítható (|-₀ G), ha a G formula bármely F feltételhalmazból levezethető.
    - Egy F = {F1, F2, . . . , Fn } formulahalmaz ellentmondásos (inkonzisztens), ha F |-₀ G és F |-₀ ¬G. Egyébként a formulahalmaz nem ellentmondásos (konzisztens).

### Még több tétel:
- Tétel: Két levezetés konkatenációja is levezetés. Ha F-ből levezethető G1 és S-ből levezethető G2, akkor a két levezetés konkatenációja az F ∪ S-ből való levezetés.
- Tétel: Ha F-ből levezethető G1 és S-ből levezethető G2, valamint {G1, G2}-ből levezethető A, akkor az F ∪ S-ből levezethető A.
- Tétel: Az {F1, F2, . . . , Fn } |−₀ G ⇐⇒ |−₀ F1 ⊃ (F2 ⊃ (. . . ⊃ (Fn−1 ⊃ (Fn ⊃ G)) . . .)).
    - Biz.: a dedukciós tétel következménye
- Tétel: Ha F-ből levezethető G, akkor az F ∪ {¬G} ellentmondásos.
- Tétel: Ha {F1, F2, . . . , Fn } ellentmondásos, akkor kielégíthetetlen.
- Tétel: Legyen A egy formula, és F egy konzisztens formulahalmaz, ekkor
    - (a) F, ¬A ellentmondásos, akkor és csak akkor, ha F |−₀ A.
    - (b) F, A ellentmondásos, akkor és csak akkor, ha F |−₀ ¬A.
    - Biz.:
        - (a) 
            - ⇒: Ha F, ¬A ellentmondásos, akkor F, ¬A |−₀ B és F, ¬A |−₀ ¬B. A dedukciós tétel miatt F |−₀ ¬A ⊃ B és F |−₀ ¬A ⊃ ¬B. A két  levezetés konkatenációját folytatva a 3. axióma (¬A ⊃ B) ⊃ (¬A ⊃ ¬B) ⊃ A alakjával, majd a ¬A ⊃ B és a ¬A ⊃ ¬B leválasztásával megkapjuk az A levezetését az F-ből.
            - ⇐: Ha F |−₀ A, akkor F, ¬A ellentmondásos, mivel F, ¬A |−₀ A és F, ¬A |−₀ ¬A
        - (b)
            - ⇒: F, A ellentmondásos, akkor mivel minden, ami F, A-ból levezethető, az F, ¬¬A-ból is levezethető; tehát, ha F, A ellentmondásos, akkor F, ¬¬A is az. Használva a tétel (a) részét, A helyett ¬A-ra: F |=0 ¬A.
            - ⇐: Ha F |−₀ ¬A, akkor F, A ellentmondásos, mivel F , A |−₀ A és F , A |−₀ ¬A.
- Tétel: Kalmár László lemmája: Egy k változós G formula igazságtáblájának minden sorában X ′1, X ′2, . . . , X ′k |−₀ G′.
- Tétel: Ha X′1, X′2, . . . , X′k |−₀ G′ és ¬X′1, X′2, . . . , X′k |−₀ G′, akkorX′2, . . . , X′k |−₀ G′.
- Tétel: Ha G tautológia, akkor G bizonyítható.
- Tétel (gyenge teljesség): Legyen {F1, F2, . . . , Fn } véges formulahalmaz. Ha {F1, F2, . . . , Fn } |=0 G, akkor {F1, F2, . . . , Fn } |−₀ G.
- Tétel: Ha {F1, F2, . . .} |=0 G, akkor {F1, F2, . . .} |−₀ G.
    - Biz.: Gödel-féle gondolatmenettel:
        1. Ha {F1, F2, . . .} |=0 G, akkor {F1, F2, . . .} ∪ {¬G} kielégíthetetlen.
        2. Ha {F1, F2, . . .} ∪ {¬G} ellentmondásos (inkonzisztens), akkor {F1, F2, . . .} |−₀ G.
    
### Összegzés
Az ítéletkalkulus tehát a szemantikus tárgyalásával ekvivalens szintaktikus tárgyalásmód. A bizonyításelméleti levezetés  konstrukciója a tételbizonyítás eszköze, szintaktikus kalkulus.

## Természetes levezetés

### Eldöntésprobléma

- A bizonyításelmélet általános eldöntésproblémája ítéletlogikában és elsőrendű logikában: létezik-e {F1, F2, . . .}-ből tetszőleges (nem feltétlenül véges) bizonyításelméleti levezetése G-nek.
- A bizonyításelmélet gyönge eldöntésproblémája: bizonyítható-e tetszőleges Q ítéletlogikai illetve elsőrendű formula
- Előrekövetkeztetés és visszakövetkeztetés a bizonyításelméletben az általános illetve a gyönge eldöntésprobléma megoldása.

### Gentzen stílusú kalkulusok:

- Természetes technika
- Gentzen szekvent módszer

### Természetes technika strukturális szabályai (Fentről lefele, vonalat odaképzelni)

- az azonosság törvénye
    - Γ, A |−₀ A
- a bővítés szabálya 
    - Γ |−₀ A/Γ, B |−₀ A
- a szűkítés szabálya
    - Γ, B, B, ∆ |−₀ A/Γ, B, ∆ |−₀ A
- a felcserélés szabálya 
    - Γ, B, C , ∆ |−₀ A/Γ, C , B, ∆ |−₀ A
- a vágás szabálya
    - Γ |−₀ A ∆, A |−₀ B/Γ, ∆ |−₀ B

### Logikai szabályai

- A természetes technika logikai szabályai
    - bevezető szabályok
    - alkalmazó szabályok
        - biz.:
            - Az implikáció bevezetésének szabálya épp a dedukciós tétel.
            - Az implikációt alkalmazó szabály : Ha adottak a Γ |−₀ A és a Γ |−₀ A ⊃ B állításokat megalapozó levezetések, a kettő konkatenációja után alkalmazható a modus ponens, és így épp B-nek egy, a Γ-ból való levezetését állítottuk elő.
            - A diszjunkció bevezetése: Ha adott Γ-ból A-nak a levezetése, akkor az A ⊃ A ∨ B axiómát beírva a levezetésbe alkalmazhatjuk a modus ponenst, és máris megkaptuk a Γ-ból az A ∨ B egy levezetését.
            - A diszjunkció alkalmazása: Ha adottak a Γ, A |−₀ C és a Γ, B |−₀ C állításokat megalapozó levezetések, akkor a dedukciós tétel miatt megkonstruálhatók a Γ |−₀ A ⊃ C és a Γ |−₀ B ⊃ C állításokat megalapozó levezetések is. Ezt a két levezetést konkatenáljuk,és írjuk le az (A ⊃ C ) ⊃ ((B ⊃ C ) ⊃ (A ∨ B ⊃ C )) axiómát. Kétszer alkalmazva a modus ponenst megalapoztuk, hogy Γ |−₀ A ∨ B ⊃ C .  Irjuk be a levezetésbe a vonal alatti szekvenciából az A ∨ B hipotézist, és ha most újból alkalmazzuk a modus ponenst, megkapjuk a Γ, A ∨ B |−₀ C -t megalapozó levezetést.
- - A természetes technika logikai szabályai elsőrendben
    - bevezető szabályok
    - alkalmazó szabályok
        - biz.:
            - Az egzisztenciális kvantort bevezet˜o szabály : Ha adott a Γ ' [A(x ‖ t)] szekvenciát megalapozó levezetés, akkor írjuk be az [A(x ‖ t)] ⊃ ∃xA axiómát a levezetésbe, és alkalmazzuk a modus ponenst. ´Igy Γ-ból levezettük ∃xA-t.
            - Az egzisztenciális kvantor alkalmazásának szabálya: Ha adott a Γ, A ' B szekvenciát megalapozó levezetés, akkor a dedukciós tétel miatt megkonstruálható a Γ ' A ⊃ B szekvenciát megalapozó levezetés is. Ebből az általánosítás szabálya miatt (mivel x /∈ Par(Γ)) Γ ' ∀x(A ⊃ B) adódik. Ha most a levezetésbe beírjuk a ∀x(A ⊃ B) ⊃ (∃xA ⊃ B) axiómát (lényeges, hogy x /∈ Par(B)), alkalmazhatjuk a modus ponenst. Ezzel megkapjuk a ∃xA ⊃ B egy levezetését Γ-ból. A dedukciós tétel újbóli alkalmazásával pedig igazoltuk, hogy Γ, ∃xA ' B.

## Szekvent kalkulus

### Szintaxisa

- Γ, ∆: véges formulahalmazok (véges, nem rendezett formulasorozatok)
- A, B, . . .: formulák
- (Γ, ∆) pár: szekvent; jelölése: Γ → ∆. A → jel szándék szerint implikációt reprezentál.
- Megengedjük, hogy a (Γ, ∆) szekventben akár Γ, akár ∆ egyetlen formulát se tartalmazzon.
    - Ha Γ üres, a ∅ → ∆ helyett → ∆ -t írunk.
    - Ha ∆ üres, a Γ → ∅ helyett Γ → -t írunk.
    - Mindkét formulahalmaz lehet üres szekvent: →.
    - Ha Γ = {A1, A2, . . . , An } és ∆ = {B1, B2, . . . , Bn } véges nem rendezett formulasorozatok, és A, B ítéletlogikai formulák, akkor A, Γ → ∆, B -t írunk, ami az A, A1, A2, . . . , An → B1, B2, . . . , Bm , B szekventet jelenti.

### Szemantikája

Legyen I az ítéletlogika nyelvének egy interpretációja, BI pedig I-beli Boole értékelés. <br>
Legyen BI (Γ → ∆) pontosan akkor i igazságértékű, ha van olyan Ak a Γ-ban, hogy BI (Ak ) = h vagy van olyan Br a ∆-ban, hogy BI (Br ) = i.<br>
Egyébként BI legyen h igazságértékű.<br>

Szekvent jelentése szemantika alapján:
- BI (→) = h,
- BI (→ B) = BI (B),
- BI (A →) = BI (¬A),
- BI (A → B) = BI (A ⊃ B),
- BI (A1, A2 → B1, B2) = BI (A1 ∧ A2 ⊃ B1 ∨ B2),

ahol a baloldal tautológia (T), ha Γ üres, <br>a jobboldal pedig azonosan hamis (⊥), ha ∆ üres.

Azt mondjuk, hogy egy szekvent teljesül, ha valahányszor a nyíl baloldalán lévő minden formula igaz a nyíl jobboldalán lévő formulák legalább egyike igaz.

A szekventkalkulus szabályrendszere:
- Gentzen féle (G-kalkulus)
- Curry-féle (C-kalkulus) – szabályai megfordíthatók

### Szabályai

[...]

### Levezetésfa

A K-kalkulusbeli levezetésfa és a levezetésfa magassága
1. A K-kalkulus minden axiómaszekventje egy levezetésfa, ez a szekvent lesz a levezetésfa gyökere. A levezetésfa magassága 1.
2. Ha D m magasságú olyan K-kalkulusbeli levezetésfa, amelynek gyökere valamely K-kalkulusbeli levezetési szabályban épp vonal feletti szekvent, akkor a levezetési szabállyal a vonal alatti S szekventet előállítva D/S is K-kalkulusbeli levezetésfa, ahol az S szekvent a kapott levezetésfa gyökere, és a levezetésfa magassága m + 1.
3. Ha D1 és D2 rendre m1 és m2 magasságú olyan K-kalkulusbeli levezetésfák, melyek gyökerei valamely K-kalkulusbeli levezetési szabályban épp vonal feletti szekventek, akkor előállítva a levezetési szabállyal a vonal alatti S szekventet, (D1 D2)/S is levezetésfa a K-kalkulusban, amelyben az S szekvent lesz a levezetésfa gyökere, és a levezetésfa magassága max(m1, m2) + 1.
4. Minden levezetésfa az 1–3. szabályok véges sokszori alkalmazásával áll elő. 

### Bizonyíthatóság

Egy S szekvent a K-kalkulusban bizonyítható, ha van olyan K-kalkulusbeli levezetésfa, melynek S a gyökere. Jelölése: 'K S.

### Elérhető szabály

elölje K1 a G- és C-kalkulusok egyikét, és K2 a másikat. Azt mondjuk, hogy egy a K1-kalkulusbeli S1/S2 levezetési szabály elérhető a K2-kalkulusból, ha minden olyan esetben, amikor 'K2 S1, akkor 'K2 S2 is. Hasonlóan, egy a K1-kalkulusbeli (S1 S2)/S3 levezetési szabály elérhető a K2-kalkulusból, ha minden olyan esetben, amikor 'K2 S1 és 'K2 S2, akkor 'K2 S3 is

### G és C kalkulus ekvivalenciája

Ha egy szekvent bizonyítható C kalkulusban, akkor bizonyítható G kalkulusban is<br>
Ha egy szekvent bizonyítható G kalkulusban, akkor bizonyítható C kalkulusban is<br>
Bizonyítás: levezetésfa magassága szerinti indukcióval

### Helyesség

Ha egy szekvent bizonyítható a C kalkulusban, akkor a megfelelő
A1 ∧ A2 ∧ . . . ∧ An ⊃ B1 ∨ B2 ∨ . . . ∨ Bk formulának van bizonyítása az ítéletkalkulusban.<br>
*Bizonyítás: tegyük fel, hogy 'C Γ → ∆. A C-kalkulusbeli levezetésfa magassága szerinti indukcióval bizonyítjuk be, hogy A1 ∧ A2 ∧ . . . ∧ An ⊃ B1 ∨ B2 ∨ . . . ∨ Bk . Az egyes indukciós lépésekben A1 ∧ A2 ∧ . . . ∧ An ⊃ B1 ∨ B2 ∨ . . . ∨ Bk ítéletkalkulusbeli bizonyíthatóságát természetes technikával igazoljuk.*

### Teljesség

Ha |−₀ B, azaz B bizonyítható az ítéletkalkulusban, akkor → B bizonyítható a C kalkulusban, azaz ha |−₀ B, akkor 'C→ B.<br>
*Bizonyítás: Tegyük fel, hogy |−₀ B, azaz adott a D1, D2, . . . , Dm = B levezetés. Meg kell mutatni, hogy minden Dk (1 ≤ k ≤ m) formulára 'C Dk . Ha Dk -t modus ponenssel kaptuk, akkor a lenti lemma miatt tudjuk ezt igazolni.*

### Megfordíthatóság

Azt mondjuk, hogy egy szekventkalkulusbeli S1/S2 levezetési szabály megfordítható, ha minden olyan esetben, amikor S2 szekvent bizonyítható, akkor S1 is bizonyítható. Hasonlóan, egy (S1 S2)/S3 levezetési szabály megfordítható, ha minden olyan esetben, amikor S3 bizonyítható, akkor S1 és S2 is bizonyíthatók.

Lemma: <br>
A C-kalkulus levezetési szabályai megfordíthatók.

## Rezolúció

A logika bizonyításelméleti tárgyalásához definiáltunk a bizonyításelméleti levezetés fogalmának bevezetésével egy szintaktikus következményfogalmat, a levezethetőséget. Majd a levezetés vagy a bizonyítás előállításával körvonalaztuk az eldöntésprobléma megoldására a helyes és teljes kalkulust. <br><br> A továbbiakban a szemantikus eldötésprobléma szintaktikai eszközökkel való megoldásával foglalkozunk.

### Kalkulus

Döntési ”algoritmus”, levezető eljárás egy olyan algoritmus/lépéssorozat, amely adott input adatokkal dolgozik, azokat a megfelelő szabályok szerint használja fel, a levezetési szabály szerint alakítja át, és akkor áll meg, amikor a kitűzött célt (az eljárás megállási feltétele) elérte.<br>
Egy ilyen eljárást kalkulusnak hívunk.

### Logikai műveletekre érvényes azonosságok

#### Ekvivalens átalakítások:
1. X ∧ (Y ∨ Z ) = (X ∧ Y ) ∨ (X ∧ Z )
2. X ∨ (Y ∧ Z ) = (X ∨ Y ) ∧ (X ∨ Z )
3. X ∧ ¬X = h
4. X ∨ ¬X = i
#### DeMorgan szabályok (Biz.: Tk.91.o.)
1. ¬(X ∧ Y ) = ¬X ∨ ¬Y 
2. ¬(X ∨ Y ) = ¬X ∧ ¬Y
#### Egyszerűsítési szabályok (biz.: Tk.98.o.)
1. (X ∨ d) ∧ (¬X ∨ d) = d 
2. (X ∧ k) ∨ (¬X ∧ k) = k
<br>ahol d elemi diszjunkció és k elemi konjukció

### Definíciók

#### Literál
Egy prímformula (ítéletváltozó) vagy annak negáltja. A literál
alapja a benne szereplő prímformula. A literált
egységkonjunkciónak vagy egységdiszjunkciónak (egységklóz) is
nevezhetünk.

#### Elemi konjunkció/diszjunkció
Egységkonjunkció/diszjunkció, illetve különböző alapú literálok
konjunkciója/diszjunkciója. Az elemi diszjunkciót klóznak is
nevezzük.

#### Teljes elemi konjunkció/diszjunkció
Egy elemi konjunkció/diszjunkció teljes egy adott n változós
logikai műveletre nézve, ha mind az n ítéletváltozó alapja
valamelyik benne szereplő literálnak.

#### KNF/KKNF
A KNF elemi diszjunkciók (klózok) konjunkciója. KKNF, ha teljes
elemi diszjunkciók konjunkciója.

#### DNF/KDNF
A DNF elemi konjunkciók diszjunkciója. KDNF, ha teljes elemi
konjunkciók diszjunkciója.

#### Igaz/hamis halmaz
Egy formula igazhalmaza azon I interpretációk halmaz amelyekre a formula helyettesítési értéke igaz.<br>
Egy formula hamishalmaza azon I interpretációk halmaza amelyekre a formula helyettesítési értéke hamis.<br>

### Rezolúciós kalkulus

*Egy KNF alakú formula kielégíthetetlenségének vizsgálata a KNF-ben szereplő klózok S halmaza kielégíthetetlenségének vizsgálatával ekvivalens. Hogyan lehet eldönteni, hogy egy S klózhalmaz kielégíthetetlen? Meg kell mutatni, hogy az S tetszőleges interpretációjában legalább egy C ∈ S hamis. Egy C klóz hamis egy interpretációban, ha minden literálja hamis. Ha az összes interpretációt az S összes ítéletváltozóinak rögzített sorrendje/bázis alapján előálló szemantikus fával adjuk meg, akkor egy C ítéletlogikai klóz abban az interpretációban hamis, amelyikben a klóz literáljai ellenkező negáltságúak. Az X ∨ Z klóz hamis az ¬XY ¬Z és az ¬X ¬Y ¬Z interpretációkban, az interpretáció kiválasztását a klóz szemantikus fára illesztésének hívjuk.*

**Szemantikus fák**

#### Tételek: 
- Ha egy S véges klózhalmaz szemantikus fája zárt, akkor S kielégíthetetlen.
- {C1, C2} |=0 C A rezolvensképzés a rezolúciós kalkulus levezetési szabálya (helyes következtetésforma).

#### Egyszerűsítési szabály
(X ∨ C ) ∧ (¬X ∨ C ) ∼₀ C
Az (X ) ∧ (¬X ) ∼₀ □ – azonosan hamis.

#### Rezolvens
Legyenek C1, C2 olyan klózok, amelyek pontosan egy komplemens literálpárt tartalmaznak: C1 = C ′1 ∨ L1 és C2 = C ′2 ∨ L2 és L1 = ¬L2, ekkor létezik a rezolvensük: a res(C1, C2) = C klóz, ami C = C ′1 ∨ C ′2.

#### Rezolúciós levezetés
Egy S klózhalmazból való rezolúciós levezetés egy olyan véges k1, k2, . . . , km (m ≥ 1) klózsorozat, ahol minden j = 1, 2, . . . , m-re
1. vagy kj ∈ S,
2. vagy van olyan 1 ≤ s, t < j, hogy kj a (ks, kt ) klózpár rezolvense.

A levezetés célja az üres klóz levezetése / megállási feltétel.

#### Rezolúciós kalkulus helyes
- Lemma: Legyen S tetszőleges klózhalmaz és k1, k2 . . . , kn klózsorozat rezolúciós levezetés S-ből. Ekkor minden kj , j = 1, 2 . . . , n-re szemantikus következménye S-nek.
- Tétel: Legyen S tetszőleges klózhalmaz. Ha S-ből levezethető az üres klóz, akkor S kielégíthetetlen.Bizonyítások indukcióval.

#### Rezolúciós kalkulus teljes
- Tétel: Ha az S véges klózhalmaz kielégíthetetlen, akkor S-ből levezethető az üres klóz.
- Bizonyítás: tetszőleges zárt szemantikus fa esetén előállítunk egy rezolúciós cáfolatot.
    1. j := 0, Sj := S, LIST := ∅.
    2. állítsuk elő Sj szemantikus fáját. nj := a szemantikus fa szintjeinek száma. Ha nj = 0, akkor levezettük az üres klózt, a levezetés LIST -b˜ol kiolvasható. 
    3. Egyébként válasszuk ki a fa egy levezető csúcsát. A levezető csúcsot tartalmazó két ágra illesztett klózok legyenek k′ j és k′′ j , rezolvensük pedig kj . Tegyük a LIST végére a k′ j , k′′ j , kj klózokat. 
    4. Sj+1 := Sj ∪ {kj }, j := j + 1. Folytassuk a 2. lépéssel.

#### Levezetési fa
Egy rezolúciós levezetés szerkezetét mutatja. Olyan gráf, amelynek csúcsaiban klózok vannak. Két csúcsból akkor vezet él egy harmadik csúcsba, ha abban a két csúcsban lévő klózok rezolvense található.

### Levezetési stratégiák

#### Lineáris rezolúciós levezetés
Egy S klózhalmazból egy olyan k1, l1, k2, l2, . . . , km−1, lm−1, km klózsorozat, ahol k1, l1 ∈ S a ki (i = 2, 3, . . . , m) esetben a ki a ki−1, li−1 rezolvense, ahol li−1 ∈ S, vagy egy korábban megkapott centrális klóz(rezolvense valamely ks, ls(s < i)-nek).

#### Lineáris inputrezolúciós levezetés
S klózhalmazból egy olyan k1, l1, k2, l2, . . . , km−1, lm−1, km klózsorozat, ahol k1, l1 ∈ S, az li (i = 2, 3, . . . , m − 1) esetben li ∈ S és a ki pedig a ki−1, li−1 rezolvense.

#### Egységrezolúciós stratégia
Rezolvens csak akkor képezhető, ha legalább az egyik klóz egységklóz.

### Horn klózok, Horn logika

#### Definiciók
- Egy klózt Horn klóznak nevezünk, ha legfeljebb egy literálja nem negált.
- Horn logika az összes, csak Horn klózokat tartalmazó KNF alakú formulák halmaza.

#### Tételek
- A lineáris input és az egységrezolúciós stratégia teljes a Horn logikában.
- Ha az □ levezethető lineáris input rezolúcióval egy K klózhalmazból, akkor K -ban van legalább egy egységklóz. 
    - Biz.: Az □-t mint rezolvenst egy centrális egységklózból és egy klózhalmazbeli klózból kapjuk. Ez utóbbi csak egységklóz lehet.
- Kielégíthetetlen Horn klózhalmazban van legalább egy egységklóz

## Elsőrendű rezolúció

### Alapok
- Literál: egy atomi formula, vagy annak a negáltja pl.: P(x), ¬P(x), ¬P(f (g (h(x, a), b)))
- Prenex formula: Kvantált formula, ahol a kvantorok a formula elejébe vannak tömörítve. pl.: ∀x∃y ∀z(P(x) ∧ Q(x, y ) ∨ R(z))
- Skolem formula: Olyan Prenex formula, amiben csak univerzális kvantor van. pl.: ∀x∀y ∀z(P(x) ∧ Q(x, y ) ∨ R(z))
- Elsőrendű klóz: Olyan zárt Skolem formula, aminek a magja literálok diszjunkciós lánca. pl.: ∀x∀y ∀z(P(x) ∨ ¬Q(x, y ) ∨ ¬R(z))

### Vizsgálat rezolúcióval
1. Kérdés kielégíthetetlenség vizsgálatává alakítása:
    - {F1, ..., Fn} |= G ⇒ {F1, ..., Fn, ¬G } kielégíthetetlen?
    - {F1, ..., Fn} |= G ⇒ {F1, ..., Fn, ¬G } kielégíthetetlen?
2. Klózhalmaz készítése
    - Implikáció átírása: A ⊃ B = ¬A ∨ B
    - Negálás bevitele atomi formuláig:
        - ¬(A ∧ B) = ¬A ∨ ¬B
        - ¬(A ∨ B) = ¬A ∧ ¬B
        - ¬¬A = A
        - ¬∀xA = ∃x¬A
        - ¬∃xA = ∀x¬A
    - Prenex formula előállítása - kvantorkiemelési szabályok
        - QxA[x] ◦ B = Qx(A[x] ◦ B) <br>pl.: ∀xP(x) ∧ Q(y , a) = ∀x(P(x) ∧ Q(y , a))
        - ∀xA[x] ∧ ∀xB[x] = ∀x(A[x] ∧ B[x]) <br>pl.: ∀xP(x) ∧ ∀xQ(x, x) = ∀x(P(x) ∧ Q(x, x))
        - ∃xA[x] ∨ ∃xB[x] = ∃x(A[x] ∨ B[x]) <br>pl.: ∃xP(x) ∨ ∃xQ(x, x) = ∃x(P(x) ∨ Q(x, x))
        - Q1xA[x] ◦ Q2xB[x] = Q1xQ2y (A[x] ◦ B[x||y ]) <br>pl.: ∀xP(x) ∨ ∃xQ(x, x) = ∀x∃y (P(x) ∨ Q(y , y ))
    - Skolem formula előállítása - skolemizálás, egzisztenciális kvantor elhagyása.
        - ∃xP(x) ⇒ P(¯a)
        - ∃x∀yQ(x, y ) ⇒ ∀yQ(¯a, y )
        - ∀x∃yQ(x, y ) ⇒ ∀xQ(x, f (x))
        - ∀x∃y ∀zR(x, y , z) ⇒ ∀x∀zR(x, f (x), z)
        - ∃x∃y ∀zR(x, y , z) ⇒ ∀zR(¯a, ¯b, z)
        - ∀x∀y ∃zR(x, y , z) ⇒ ∀x∀yR(x, y , g (x, y ))
        - ∃x∀y ∃zR(x, y , z) ⇒ ∀yR(¯a, y , g (y ))
    - Elsőrendű klózok előállítása - plusz átalakítások, A ∧ B → {A, B}
        - A ∧ (B ∨ C ) = (A ∧ B) ∨ (A ∧ C )
        - A ∨ (B ∧ C ) = (A ∨ B) ∧ (A ∨ C )
        - KNF alak után: A ∧ B → {A, B}