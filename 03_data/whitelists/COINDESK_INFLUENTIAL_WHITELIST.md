# CoinDesk Most Influential — Canonical Whitelist

**Purpose:** Seed dataset for Hodlneer Platinum (Origin) tier recognition. Individuals appearing on CoinDesk's annual "Most Influential in Crypto/Blockchain" lists are candidates for automatic Platinum badge assignment upon verified onboarding.

**Source:** CoinDesk "Most Influential" annual lists, 2014–2025
**Compiled:** 2026-04-17
**Version:** 1.1.0
**Coverage:** 2014–2025 (CoinDesk launched 2013; first influential list was 2014)

See also: [[HODLNEER_PRD]] | [[Hodlneer/CANON/TIER_SYSTEM|TIER_SYSTEM]]

---

## Coverage Summary

| Year | List Size | Coverage | Notes |
|------|-----------|----------|-------|
| 2014 | 10 | ~60% | Earliest list; partial coverage |
| 2015 | 10 | ~80% | Includes symbolic Satoshi entry |
| 2016 | 10 | ~40% | Several names UNCERTAIN via secondary sources |
| 2017 | 10 | ~60% | Heavy Asia/China representation |
| 2018 | 10 | ~60% | Bear market year; CZ ranked #1 |
| 2019 | 10 | **100%** | All 10 names confirmed |
| 2020 | 12 | **100%** | All 12 names confirmed |
| 2021 | 50 | ~80% | Top 10 + ~30 of honorable 40 confirmed |
| 2022 | 50 | ~45% | Collapse year partial coverage |
| 2023 | 50 | ~76% | 38 of 50 confirmed |
| 2024 | 50 | ~95% | Near-complete; most reliable year |
| 2025 | 50 | ~25% | Political cycle; early data only |

**Total unique matchable individuals:** ~153 (deduplicated, excluding ANON/SYMBOLIC/ORG)
**Total EXCLUDED entries (anonymous, symbolic, org):** ~18

---

## Data Quality Flags

- `[ANON]` — anonymous individual or pseudonym; cannot be onboarded by name → **EXCLUDE from matching**
- `[ORG]` — organization or group entry, not an individual → **EXCLUDE from matching**
- `[UNCERTAIN]` — name partially confirmed; verify before backend use
- `[SYMBOLIC]` — historical/symbolic inclusion → **EXCLUDE from matching**
- `[INCOMPLETE_YEAR]` — year coverage below 50%; additional names likely exist

---

## Master Deduplicated List

Sorted by first appearance year, then alphabetically within year. Entries marked EXCLUDE in Confidence column must not be used in automated matching.

| # | Name | Known As | Years Appeared | First | Last | Count | Confidence |
|---|------|----------|---------------|-------|------|-------|------------|
| 1 | Andreas M. Antonopoulos | @aantonop | 2014, 2016 | 2014 | 2016 | 2 | HIGH |
| 2 | Marc Andreessen | @pmarca | 2014 | 2014 | 2014 | 1 | HIGH |
| 3 | Gavin Andresen | | 2014, 2015 | 2014 | 2015 | 2 | HIGH |
| 4 | Vitalik Buterin | @VitalikButerin | 2014, 2015, 2022, 2023 | 2014 | 2023 | 4 | HIGH |
| 5 | Benjamin Lawsky | | 2014 | 2014 | 2014 | 1 | HIGH |
| 6 | Roger Ver | @rogerkver | 2014, 2015, 2016 | 2014 | 2016 | 3 | HIGH |
| 7 | Satoshi Nakamoto | | 2015 | 2015 | 2015 | 1 | EXCLUDE [SYMBOLIC] |
| 8 | Blythe Masters | | 2015 | 2015 | 2015 | 1 | HIGH |
| 9 | Bobby Lee | @bobbyclee | 2015 | 2015 | 2015 | 1 | HIGH |
| 10 | Balaji Srinivasan | @balajis | 2015, 2020, 2023, 2024 | 2015 | 2024 | 4 | HIGH |
| 11 | Theymos | theymos | 2015 | 2015 | 2015 | 1 | HIGH |
| 12 | The DAO Attacker | | 2016 | 2016 | 2016 | 1 | EXCLUDE [ANON] |
| 13 | Adam Back | @adam3us | 2016 | 2016 | 2016 | 1 | MEDIUM [UNCERTAIN] |
| 14 | Daniel Larimer | @bytemaster7 | 2016 | 2016 | 2016 | 1 | MEDIUM [UNCERTAIN] |
| 15 | Chris Larsen | | 2016 | 2016 | 2016 | 1 | MEDIUM [UNCERTAIN] |
| 16 | Barry Silbert | @barrysilbert | 2016, 2021, 2023 | 2016 | 2023 | 3 | HIGH |
| 17 | Emin Gün Sirer | @el33th4xor | 2016 | 2016 | 2016 | 1 | MEDIUM [UNCERTAIN] |
| 18 | Zooko Wilcox-O'Hearn | @zooko | 2016 | 2016 | 2016 | 1 | MEDIUM [UNCERTAIN] |
| 19 | Amber Baldet | @AmberBaldet | 2017 | 2017 | 2017 | 1 | HIGH |
| 20 | Charlie Lee | @SatoshiLite | 2017 | 2017 | 2017 | 1 | HIGH |
| 21 | Joe Lubin | @ethereumJoseph | 2017 | 2017 | 2017 | 1 | HIGH |
| 22 | Naval Ravikant | @naval | 2017 | 2017 | 2017 | 1 | HIGH |
| 23 | Jihan Wu | | 2017 | 2017 | 2017 | 1 | HIGH |
| 24 | Yao Qian | | 2017 | 2017 | 2017 | 1 | HIGH |
| 25 | Jeremy Allaire | @jerallaire | 2018 | 2018 | 2018 | 1 | HIGH |
| 26 | Changpeng Zhao (CZ) | @cz_binance | 2018, 2021, 2022 | 2018 | 2022 | 3 | HIGH |
| 27 | Brenna Sparks | @BrennaSparks | 2018 | 2018 | 2018 | 1 | HIGH |
| 28 | Jed McCaleb | | 2018 | 2018 | 2018 | 1 | HIGH |
| 29 | Nouriel Roubini | @Nouriel | 2018 | 2018 | 2018 | 1 | HIGH |
| 30 | Stark | | 2018 | 2018 | 2018 | 1 | MEDIUM [UNCERTAIN — first name unconfirmed] |
| 31 | Caitlin Long | @CaitlinLong_ | 2019 | 2019 | 2019 | 1 | HIGH |
| 32 | Jack Dorsey | @jack | 2019, 2021 | 2019 | 2021 | 2 | HIGH |
| 33 | Gerald Cotten | | 2019 | 2019 | 2019 | 1 | HIGH |
| 34 | Hodlonaut | @hodlonaut | 2019 | 2019 | 2019 | 1 | EXCLUDE [ANON] |
| 35 | David Marcus | @davidmarcus | 2019 | 2019 | 2019 | 1 | HIGH |
| 36 | Meltem Demirors | @Meltem_Demirors | 2019 | 2019 | 2019 | 1 | HIGH |
| 37 | Muneeb Ali | @muneeb | 2019 | 2019 | 2019 | 1 | HIGH |
| 38 | Sergey Nazarov | @sergeynazarov | 2019, 2023 | 2019 | 2023 | 2 | HIGH |
| 39 | Rune Christensen | @RuneKek | 2019, 2023, 2024 | 2019 | 2024 | 3 | HIGH |
| 40 | Justin Sun | @justinsuntron | 2019, 2024 | 2019 | 2024 | 2 | HIGH |
| 41 | Juan Benet | @juanbenet | 2020 | 2020 | 2020 | 1 | HIGH |
| 42 | Bitcoin Protesters | | 2020 | 2020 | 2020 | 1 | EXCLUDE [ORG/ANON] |
| 43 | Cathie Wood | @CathieDWood | 2020 | 2020 | 2020 | 1 | HIGH |
| 44 | Charles Cascarilla | | 2020 | 2020 | 2020 | 1 | HIGH |
| 45 | Andre Cronje | @AndreCronjeTech | 2020, 2021 | 2020 | 2021 | 2 | HIGH |
| 46 | Hayden Adams | @haydenzadams | 2020, 2023 | 2020 | 2023 | 2 | HIGH |
| 47 | Linda Lacewell | | 2020 | 2020 | 2020 | 1 | HIGH |
| 48 | Jesse Powell | @jessepowell | 2020 | 2020 | 2020 | 1 | HIGH |
| 49 | Michael Saylor | @saylor | 2020, 2021, 2024 | 2020 | 2024 | 3 | HIGH |
| 50 | Amiti Uttarwar | @amizi | 2020 | 2020 | 2020 | 1 | HIGH |
| 51 | Zhou Xiaochuan | | 2020 | 2020 | 2020 | 1 | HIGH |
| 52 | Bitcoin Taproot Developers | | 2021 | 2021 | 2021 | 1 | EXCLUDE [ORG/ANON] |
| 53 | Brian Armstrong | @brian_armstrong | 2021, 2023 | 2021 | 2023 | 2 | HIGH |
| 54 | Arianna Simpson | @AriannaSimpson | 2021 | 2021 | 2021 | 1 | HIGH |
| 55 | Mike Winkelmann (Beeple) | @beeple | 2021 | 2021 | 2021 | 1 | HIGH |
| 56 | Bitfinex'ed | @Bitfinexed | 2021 | 2021 | 2021 | 1 | EXCLUDE [ANON] |
| 57 | Camila Russo | @CamiRusso | 2021 | 2021 | 2021 | 1 | HIGH |
| 58 | Charles Hoskinson | @IOHK_Charles | 2021 | 2021 | 2021 | 1 | HIGH |
| 59 | Cynthia Lummis | @CynthiaMLummis | 2021, 2024 | 2021 | 2024 | 2 | HIGH |
| 60 | Devin Finzer | @dfinzer | 2021 | 2021 | 2021 | 1 | HIGH |
| 61 | Do Kwon | @stablekwon | 2021, 2022 | 2021 | 2022 | 2 | HIGH |
| 62 | Elon Musk | @elonmusk | 2021 | 2021 | 2021 | 1 | HIGH |
| 63 | Francis Suarez | @FrancisSuarez | 2021 | 2021 | 2021 | 1 | HIGH |
| 64 | Gary Gensler | | 2021, 2022, 2023 | 2021 | 2023 | 3 | HIGH |
| 65 | Gavin Wood | @gavofyork | 2021 | 2021 | 2021 | 1 | HIGH |
| 66 | Isaiah Jackson | @bitcoinzay | 2021 | 2021 | 2021 | 1 | HIGH |
| 67 | Jack Mallers | @jackmallers | 2021 | 2021 | 2021 | 1 | HIGH |
| 68 | Jerome Powell | | 2021 | 2021 | 2021 | 1 | HIGH |
| 69 | John Watkinson | | 2021 | 2021 | 2021 | 1 | HIGH |
| 70 | Katie Haun | @katie_haun | 2021 | 2021 | 2021 | 1 | HIGH |
| 71 | Kristin Smith | @kristin_smith_ | 2021 | 2021 | 2021 | 1 | HIGH |
| 72 | Mark Cuban | @mcuban | 2021 | 2021 | 2021 | 1 | HIGH |
| 73 | Matt Hall | | 2021 | 2021 | 2021 | 1 | HIGH |
| 74 | Michael Shaulov | | 2021 | 2021 | 2021 | 1 | HIGH |
| 75 | Naveen Jain | | 2021 | 2021 | 2021 | 1 | MEDIUM [UNCERTAIN] |
| 76 | Anatoly Yakovenko | @aeyakovenko | 2021, 2023 | 2021 | 2023 | 2 | HIGH |
| 77 | Paolo Ardoino | @paoloardoino | 2021, 2023, 2024, 2025 | 2021 | 2025 | 4 | HIGH |
| 78 | Polynetwork Hacker | | 2021 | 2021 | 2021 | 1 | EXCLUDE [ANON] |
| 79 | Ray Youssef | @RayYoussef | 2021 | 2021 | 2021 | 1 | HIGH |
| 80 | Robert Leshner | @rleshner | 2021 | 2021 | 2021 | 1 | HIGH |
| 81 | Roham Gharegozlou | @rohamg | 2021 | 2021 | 2021 | 1 | HIGH |
| 82 | Roneil Rumburg | @roneil1 | 2021 | 2021 | 2021 | 1 | HIGH |
| 83 | Ryan Selkis | @twobitidiot | 2021, 2023 | 2021 | 2023 | 2 | HIGH |
| 84 | Sam Bankman-Fried | @SBF_FTX | 2021, 2022 | 2021 | 2022 | 2 | HIGH |
| 85 | Serey Chea | | 2021 | 2021 | 2021 | 1 | HIGH |
| 86 | All Seeing Seneca | @allseeingnfts | 2021 | 2021 | 2021 | 1 | HIGH |
| 87 | Tim Beiko | @TimBeiko | 2021 | 2021 | 2021 | 1 | HIGH |
| 88 | Trung Nguyen | | 2021 | 2021 | 2021 | 1 | HIGH |
| 89 | Willy Woo | @woonomic | 2021 | 2021 | 2021 | 1 | HIGH |
| 90 | Xi Jinping | | 2021 | 2021 | 2021 | 1 | HIGH |
| 91 | Alex Mashinsky | | 2022 | 2022 | 2022 | 1 | HIGH |
| 92 | Arthur Hayes | @CryptoHayes | 2022, 2024 | 2022 | 2024 | 2 | HIGH |
| 93 | BowTiedBull | @BowTiedBull | 2022 | 2022 | 2022 | 1 | EXCLUDE [ANON] |
| 94 | cobie | @cobie | 2022 | 2022 | 2022 | 1 | EXCLUDE [ANON] |
| 95 | Gary Vaynerchuk | @garyvee | 2022 | 2022 | 2022 | 1 | HIGH |
| 96 | Nic Carter | @nic__carter | 2022 | 2022 | 2022 | 1 | HIGH |
| 97 | Rostin Behnam | | 2022 | 2022 | 2022 | 1 | HIGH |
| 98 | Su Zhu | @zhusu | 2022 | 2022 | 2022 | 1 | HIGH |
| 99 | Brad Garlinghouse | @bgarlinghouse | 2023 | 2023 | 2023 | 1 | HIGH |
| 100 | Caroline Ellison | | 2023 | 2023 | 2023 | 1 | HIGH |
| 101 | Casey Rodarmor | @rodarmor | 2023 | 2023 | 2023 | 1 | HIGH |
| 102 | Cuy Sheffield | @cuysh | 2023 | 2023 | 2023 | 1 | HIGH |
| 103 | Elizabeth Warren | | 2023 | 2023 | 2023 | 1 | HIGH |
| 104 | Ian Allison | @ianallisonuk | 2023 | 2023 | 2023 | 1 | HIGH |
| 105 | Jenny Johnson | | 2023 | 2023 | 2023 | 1 | HIGH |
| 106 | Jesse Pollak | @jessepollak | 2023 | 2023 | 2023 | 1 | HIGH |
| 107 | Jose Fernandez da Ponte | | 2023 | 2023 | 2023 | 1 | HIGH |
| 108 | Judge Analisa Torres | | 2023 | 2023 | 2023 | 1 | HIGH |
| 109 | Julia Leung | | 2023, 2024 | 2023 | 2024 | 2 | HIGH |
| 110 | Karl Floersch | @karl_dot_tech | 2023 | 2023 | 2023 | 1 | HIGH |
| 111 | Larry Fink | | 2023, 2024 | 2023 | 2024 | 2 | HIGH |
| 112 | Lisa Neigut | @niftynei | 2023 | 2023 | 2023 | 1 | HIGH |
| 113 | Luca Schnetzler | | 2023 | 2023 | 2023 | 1 | MEDIUM [UNCERTAIN — may be same person as Luca Netz in 2024] |
| 114 | Martin Köppelmann | @koeppelmann | 2023 | 2023 | 2023 | 1 | HIGH |
| 115 | Mike Belshe | | 2023 | 2023 | 2023 | 1 | HIGH |
| 116 | Pacman | @0xpacman | 2023 | 2023 | 2023 | 1 | EXCLUDE [ANON] |
| 117 | Pascal Gauthier | | 2023 | 2023 | 2023 | 1 | HIGH |
| 118 | Patrick McHenry | | 2023, 2024 | 2023 | 2024 | 2 | HIGH |
| 119 | Paul Sztorc | @Truthcoin | 2023 | 2023 | 2023 | 1 | HIGH |
| 120 | Ravi Menon | | 2023 | 2023 | 2023 | 1 | HIGH |
| 121 | Refik Anadol | @refikanadol | 2023 | 2023 | 2023 | 1 | HIGH |
| 122 | Ria Bhutoria | @riabhutoria | 2023 | 2023 | 2023 | 1 | HIGH |
| 123 | Richard Teng | | 2023, 2024 | 2023 | 2024 | 2 | HIGH |
| 124 | Sam Altman | @sama | 2023 | 2023 | 2023 | 1 | HIGH |
| 125 | Shytoshi Kusama | @ShytoshiKusama | 2023 | 2023 | 2023 | 1 | EXCLUDE [ANON/ORG — listed with SHIB community] |
| 126 | Yat Siu | @ysiu | 2023, 2024 | 2023 | 2024 | 2 | HIGH |
| 127 | Adam Sullivan | | 2024 | 2024 | 2024 | 1 | HIGH |
| 128 | Andy Ayrey | @RonanMcGovern | 2024 | 2024 | 2024 | 1 | HIGH |
| 129 | Ansem | @blknoiz06 | 2024 | 2024 | 2024 | 1 | EXCLUDE [ANON] |
| 130 | Avery Ching | | 2024 | 2024 | 2024 | 1 | HIGH |
| 131 | Brian Nelson | | 2024 | 2024 | 2024 | 1 | HIGH |
| 132 | David Tse | | 2024 | 2024 | 2024 | 1 | HIGH |
| 133 | Donald Trump | @realDonaldTrump | 2024, 2025 | 2024 | 2025 | 2 | HIGH |
| 134 | Eric Balchunas | @EricBalchunas | 2024 | 2024 | 2024 | 1 | HIGH |
| 135 | Eric Semler | | 2024 | 2024 | 2024 | 1 | HIGH |
| 136 | Eric Wall | @ercwl | 2024 | 2024 | 2024 | 1 | HIGH |
| 137 | Erik Voorhees | @ErikVoorhees | 2024 | 2024 | 2024 | 1 | HIGH |
| 138 | Evan Cheng | | 2024 | 2024 | 2024 | 1 | HIGH |
| 139 | Fairshake | | 2024 | 2024 | 2024 | 1 | EXCLUDE [ORG] |
| 140 | Francisco Alarcon | | 2024 | 2024 | 2024 | 1 | HIGH |
| 141 | Frank Mong | | 2024 | 2024 | 2024 | 1 | HIGH |
| 142 | Fred Thiel | | 2024 | 2024 | 2024 | 1 | HIGH |
| 143 | Greg Osuri | @gregosuri | 2024 | 2024 | 2024 | 1 | HIGH |
| 144 | Howard Lutnick | | 2024 | 2024 | 2024 | 1 | HIGH |
| 145 | Hunter Horsley | | 2024 | 2024 | 2024 | 1 | HIGH |
| 146 | Illia Polosukhin | @ilblackdragon | 2024 | 2024 | 2024 | 1 | HIGH |
| 147 | James Seyffart | @JSeyff | 2024 | 2024 | 2024 | 1 | HIGH |
| 148 | Jinglan Wang | @jinglanW | 2024 | 2024 | 2024 | 1 | HIGH |
| 149 | Johnny Ng | | 2024 | 2024 | 2024 | 1 | HIGH |
| 150 | Keone Hon | | 2024 | 2024 | 2024 | 1 | HIGH |
| 151 | Lily Liu | @lily_liu_ | 2024 | 2024 | 2024 | 1 | HIGH |
| 152 | Luca Netz | @LucaNetz | 2024 | 2024 | 2024 | 1 | MEDIUM [UNCERTAIN — may be same person as Luca Schnetzler in 2023] |
| 153 | Luuk Strijers | | 2024 | 2024 | 2024 | 1 | HIGH |
| 154 | Mahesh Ramakrishnan | | 2024 | 2024 | 2024 | 1 | HIGH |
| 155 | Matt Hougan | @Matt_Hougan | 2024 | 2024 | 2024 | 1 | HIGH |
| 156 | Matthew Long | | 2024 | 2024 | 2024 | 1 | HIGH |
| 157 | Pavel Durov | | 2024 | 2024 | 2024 | 1 | HIGH |
| 158 | Ray Chan | | 2024 | 2024 | 2024 | 1 | HIGH |
| 159 | Richard Teng | | 2024 | 2024 | 2024 | 1 | — (see #123) |
| 160 | Robin Linus | @robin_linus | 2024 | 2024 | 2024 | 1 | HIGH |
| 161 | Sergio Demian Lerner | | 2024 | 2024 | 2024 | 1 | HIGH |
| 162 | Shayne Coplan | | 2024 | 2024 | 2024 | 1 | HIGH |
| 163 | Sreeram Kannan | | 2024 | 2024 | 2024 | 1 | HIGH |
| 164 | Steve Yun | | 2024 | 2024 | 2024 | 1 | HIGH |
| 165 | Tigran Gambaryan | | 2024 | 2024 | 2024 | 1 | HIGH |
| 166 | Udi Wertheimer | @udiWertheimer | 2024 | 2024 | 2024 | 1 | HIGH |
| 167 | ZachXBT | @zachxbt | 2024 | 2024 | 2024 | 1 | EXCLUDE [ANON] |
| 168 | Cameron Winklevoss | @cameron | 2025 | 2025 | 2025 | 1 | HIGH |
| 169 | David Sacks | @DavidSacks | 2025 | 2025 | 2025 | 1 | HIGH |
| 170 | French Hill | | 2025 | 2025 | 2025 | 1 | HIGH |
| 171 | Ross Ulbricht | @RealRossU | 2025 | 2025 | 2025 | 1 | HIGH |
| 172 | Tyler Winklevoss | @tyler | 2025 | 2025 | 2025 | 1 | HIGH |

> **Note (row 159):** Richard Teng appears twice in the table above due to deduplication — his canonical entry is #123. Row 159 should be ignored; it is listed here only to preserve reference integrity during backend import.

---

## Yearly Breakdown

### 2014 — 10 entries, ~60% coverage [INCOMPLETE_YEAR]

| Name | Role at Time |
|------|-------------|
| Andreas M. Antonopoulos | Bitcoin educator, author of Mastering Bitcoin |
| Vitalik Buterin | Ethereum co-founder (pre-mainnet) |
| Gavin Andresen | Bitcoin Core lead developer |
| Benjamin Lawsky | NY Superintendent of Financial Services (BitLicense author) |
| Roger Ver | Bitcoin investor, evangelist ("Bitcoin Jesus") |
| Marc Andreessen | Partner, Andreessen Horowitz (a16z) |

### 2015 — 10 entries, ~80% coverage

| Name | Role at Time |
|------|-------------|
| Satoshi Nakamoto | Bitcoin creator — symbolic/historical inclusion [SYMBOLIC] |
| Blythe Masters | CEO, Digital Asset Holdings; former JPMorgan executive |
| Bobby Lee | CEO, BTCC (China's first Bitcoin exchange) |
| Balaji Srinivasan | CEO, 21.co; Stanford lecturer |
| Vitalik Buterin | Ethereum founder (post-mainnet) |
| Gavin Andresen | Bitcoin Core developer |
| Theymos | Bitcointalk.org admin; r/Bitcoin moderator |
| Roger Ver | Bitcoin.com |

### 2016 — 10 entries, ~40% coverage [INCOMPLETE_YEAR]

> Many entries from secondary sources; flagged UNCERTAIN until independently verified.

| Name | Role at Time |
|------|-------------|
| Andreas M. Antonopoulos | Bitcoin educator |
| The DAO Attacker | Anonymous; exploited The DAO for ~$60M ETH [ANON] |
| Adam Back | CEO, Blockstream; Hashcash inventor [UNCERTAIN] |
| Daniel Larimer | BitShares/Steem/EOS founder [UNCERTAIN] |
| Chris Larsen | CEO, Ripple [UNCERTAIN] |
| Barry Silbert | Founder and CEO, Digital Currency Group [UNCERTAIN] |
| Emin Gün Sirer | Cornell professor; Bitcoin-NG, AVA Labs [UNCERTAIN] |
| Zooko Wilcox-O'Hearn | CEO, Electric Coin Company (Zcash) [UNCERTAIN] |
| Roger Ver | Bitcoin.com |

### 2017 — 10 entries, ~60% coverage

| Name | Role at Time |
|------|-------------|
| Jihan Wu | Co-founder and CEO, Bitmain |
| Yao Qian | Head of digital currency research, People's Bank of China |
| Joe Lubin | Founder, ConsenSys; Ethereum co-founder |
| Charlie Lee | Creator, Litecoin; Director of Engineering, Coinbase |
| Naval Ravikant | Co-founder, AngelList; prolific crypto angel investor |
| Amber Baldet | Head of Blockchain, JPMorgan Chase |

### 2018 — 10 entries, ~60% coverage

| Name | Role at Time |
|------|-------------|
| Changpeng Zhao (CZ) | CEO, Binance (#1 ranking) |
| Nouriel Roubini | NYU economist; prominent crypto critic |
| Jeremy Allaire | CEO, Circle |
| Jed McCaleb | Co-founder, Stellar; founder, Mt. Gox |
| Brenna Sparks | Content creator and Bitcoin advocate |
| Stark | [Full name unconfirmed] [UNCERTAIN] |

### 2019 — 10 entries, **100% coverage**

| Name | Role at Time |
|------|-------------|
| Caitlin Long | Wyoming crypto legal advocate; later founded Avanti Bank |
| David Marcus | Head of Libra / Facebook payments; former PayPal CEO |
| Rune Christensen | Founder, MakerDAO (DAI stablecoin) |
| Jack Dorsey | CEO, Twitter and Square; Bitcoin maximalist |
| Muneeb Ali | Co-founder, Stacks (Bitcoin Layer 2) |
| Hodlonaut | Pseudonymous Bitcoin advocate; won defamation case vs Craig Wright [ANON] |
| Justin Sun | Founder, TRON |
| Meltem Demirors | CSO, CoinShares |
| Sergey Nazarov | Co-founder, Chainlink |
| Gerald Cotten | CEO, QuadrigaCX (posthumous; died in custody of ~$250M of user funds) |

### 2020 — 12 entries, **100% coverage**

| Name | Role at Time |
|------|-------------|
| Juan Benet | Founder, Protocol Labs (IPFS, Filecoin) |
| Andre Cronje | Creator, Yearn Finance; DeFi Summer architect |
| Amiti Uttarwar | Bitcoin Core developer; first full-time female contributor |
| Balaji Srinivasan | Former Coinbase CTO; COVID-19 early warning; network state theorist |
| Linda Lacewell | Superintendent, New York DFS |
| Michael Saylor | CEO, MicroStrategy (pioneered corporate Bitcoin treasury) |
| Jesse Powell | CEO, Kraken; Wyoming banking license pioneer |
| Zhou Xiaochuan | Former PBOC Governor; "father of the digital yuan" |
| Cathie Wood | CEO, ARK Invest; Bitcoin ETF and equity evangelist |
| Bitcoin Protesters | Collective entry — BLM and related movements using crypto [ORG/ANON] |
| Hayden Adams | Creator, Uniswap |
| Charles Cascarilla | Co-founder and CEO, Paxos |

### 2021 — 50 entries, ~80% coverage

**Top 10:**

| # | Name | Role at Time |
|---|------|-------------|
| 1 | Sam Bankman-Fried (SBF) | CEO, FTX |
| 2 | Roham Gharegozlou | CEO, Dapper Labs (NBA Top Shot) |
| 3 | Bitcoin Taproot Developers | Collective — dev group behind Bitcoin's Taproot upgrade [ORG/ANON] |
| 4 | Trung Nguyen | CEO, Axie Infinity / Sky Mavis |
| 5 | Jack Mallers | Founder and CEO, Strike |
| 6 | Elon Musk | CEO, Tesla and SpaceX; crypto meme market mover |
| 7 | Cynthia Lummis | U.S. Senator (WY); Bitcoin bill co-author |
| 8 | Gary Gensler | SEC Chair (newly appointed) |
| 9 | Do Kwon | CEO, Terraform Labs (LUNA/UST) |
| 10 | Katie Haun | General Partner, a16z crypto |

**Honorable 40 (confirmed):**

| Name | Role at Time |
|------|-------------|
| Brian Armstrong | CEO, Coinbase (IPO year) |
| Jack Dorsey | CEO, Twitter + Square; Bitcoin maximalist |
| Charles Hoskinson | Co-founder, Ethereum; CEO, IOG / Cardano |
| Gavin Wood | Co-founder, Ethereum; founder, Polkadot |
| Anatoly Yakovenko | Co-founder, Solana |
| Devin Finzer | Co-founder and CEO, OpenSea |
| Matt Hall | Co-founder, Larva Labs (CryptoPunks) |
| John Watkinson | Co-founder, Larva Labs (CryptoPunks) |
| Mike Winkelmann (Beeple) | Digital artist; $69M Christie's NFT sale |
| Barry Silbert | Founder and CEO, Digital Currency Group |
| Jerome Powell | Chair, Federal Reserve |
| Michael Saylor | CEO, MicroStrategy |
| Paolo Ardoino | CTO, Tether |
| Andre Cronje | Yearn Finance; continued DeFi building |
| Ray Youssef | CEO, Paxful |
| Ryan Selkis | CEO, Messari |
| Tim Beiko | Ethereum developer; coordination lead |
| Arianna Simpson | General Partner, a16z crypto |
| Kristin Smith | Executive Director, Blockchain Association |
| Willy Woo | On-chain Bitcoin analyst |
| Isaiah Jackson | Bitcoin educator and author |
| All Seeing Seneca | NFT artist (World of Women) |
| Polynetwork Hacker | Anonymous; stole and returned $600M+ in largest DeFi hack [ANON] |
| Roneil Rumburg | Co-founder and CEO, Audius |
| Michael Shaulov | Co-founder and CEO, Fireblocks |
| Francis Suarez | Mayor, Miami (Bitcoin city initiative) |
| Camila Russo | Founder, The Defiant; DeFi journalist |
| Mark Cuban | Billionaire investor; Dallas Mavericks; heavy NFT/DeFi participation |
| Serey Chea | Head of Cambodia's Bakong CBDC system |
| Xi Jinping | President, China (ordered mining ban and crypto crackdown) |
| Changpeng Zhao (CZ) | CEO, Binance |
| Robert Leshner | Founder, Compound Finance |
| Bitfinex'ed | Pseudonymous Tether critic [ANON] |
| Naveen Jain | [Role unconfirmed] [UNCERTAIN] |

### 2022 — 50 entries, ~45% coverage [INCOMPLETE_YEAR]

| Name | Role at Time |
|------|-------------|
| Vitalik Buterin | Ethereum (The Merge year) |
| Sam Bankman-Fried (SBF) | CEO, FTX (before collapse) |
| Do Kwon | CEO, Terraform Labs (LUNA/UST collapse) |
| Alex Mashinsky | CEO, Celsius Network (before bankruptcy) |
| Su Zhu | Co-founder, Three Arrows Capital (before collapse) |
| Arthur Hayes | Former CEO, BitMEX |
| Changpeng Zhao (CZ) | CEO, Binance |
| Gary Gensler | SEC Chair (crypto enforcement escalation) |
| Rostin Behnam | CFTC Chair |
| Nic Carter | Partner, Castle Island Ventures; founder, Coin Metrics |
| Gary Vaynerchuk | Founder, VeeFriends; NFT creator |
| BowTiedBull | Pseudonymous crypto/finance commentator [ANON] |
| cobie | Pseudonymous crypto trader and podcast host [ANON] |

### 2023 — 50 entries, ~76% coverage (38 confirmed)

**Top 10:**

| # | Name | Role at Time |
|---|------|-------------|
| 1 | Sam Altman | CEO, OpenAI; co-founder, Worldcoin |
| 2 | Gary Gensler | SEC Chair (enforcement peak) |
| 3 | Ryan Selkis | CEO, Messari; Washington D.C. crypto advocate |
| 4 | Casey Rodarmor | Creator, Bitcoin Ordinals and Runes protocol |
| 5 | Brian Armstrong | CEO, Coinbase; launched Base L2 |
| 6 | Jose Fernandez da Ponte | SVP Blockchain, PayPal; led PYUSD launch |
| 7 | Paolo Ardoino | New CEO, Tether |
| 8 | Brad Garlinghouse | CEO, Ripple; won partial XRP ruling |
| 9 | Jenny Johnson | CEO, Franklin Templeton; pushed asset manager into crypto |
| 10 | Larry Fink | CEO, BlackRock (Bitcoin ETF application) |

**Honorable 40 (confirmed):**

| Name | Role at Time |
|------|-------------|
| Caroline Ellison | Former CEO, Alameda Research; gave testimony against SBF |
| Barry Silbert | CEO, Digital Currency Group; navigated Genesis bankruptcy |
| Judge Analisa Torres | U.S. District Judge; partial Ripple/XRP ruling set legal precedent |
| Elizabeth Warren | U.S. Senator (MA); leading crypto skeptic in Congress |
| Patrick McHenry | House Financial Services Committee Chair; pro-crypto legislation |
| Richard Teng | New Binance CEO after CZ's departure |
| Anatoly Yakovenko | Solana co-founder; drove Solana's 2023 comeback |
| Hayden Adams | Uniswap founder; V4 release |
| Rune Christensen | MakerDAO co-founder; brought U.S. Treasuries on-chain at scale |
| Refik Anadol | Digital artist; brought blockchain-generated art to world's largest screens |
| Jesse Pollak | Coinbase; creator of the Base L2 blockchain |
| Karl Floersch | CEO, OP Labs; built developer tools for L2 chains |
| Lisa Neigut | Blockstream/Lightning developer; building Lightning v2 |
| Sergey Nazarov | Chainlink co-founder; predicted TradFi/crypto convergence |
| Pascal Gauthier | CEO, Ledger |
| Cuy Sheffield | Head of Visa crypto unit |
| Mike Belshe | CEO, BitGo; raised capital at elevated valuation in down market |
| Ria Bhutoria | Partner, Castle Island Ventures |
| Balaji Srinivasan | $1M USD collapse bet; Network State evangelist |
| Yat Siu | Co-founder/Chairman, Animoca Brands; Web3 gaming |
| Paul Sztorc | Bitcoin developer; BIP 300 / DriveChains |
| Pacman | Co-founder, Blur NFT marketplace (pseudonymous) [ANON] |
| Luca Schnetzler | CEO, Pudgy Penguins [UNCERTAIN — may be Luca Netz] |
| Shytoshi Kusama + SHIB community | Led Shibarium launch — listed as collective [ANON/ORG] |
| Martin Köppelmann | Gnosis co-founder; critic of Ethereum direction |
| Julia Leung | Hong Kong SFC head; powerful financial regulator |
| Ravi Menon | Head of Monetary Authority of Singapore |
| Ian Allison | CoinDesk reporter; broke the Alameda/FTX story that triggered collapse |

### 2024 — 50 entries, ~95% coverage

**Top 10:**

| # | Name | Role at Time |
|---|------|-------------|
| 1 | Andy Ayrey | Creator, Truth Terminal (AI/crypto agent) |
| 2 | Ansem | Memecoin influencer (pseudonymous) [ANON] |
| 3 | Cynthia Lummis | U.S. Senator (WY); Bitcoin Strategic Reserve bill |
| 4 | Donald Trump | President-elect; pro-crypto platform |
| 5 | Fairshake | Crypto super PAC [ORG] |
| 6 | Jinglan Wang | Co-founder, Optimism |
| 7 | Larry Fink | CEO, BlackRock; Bitcoin spot ETF approved |
| 8 | Shayne Coplan | CEO, Polymarket |
| 9 | Sreeram Kannan | Founder, EigenLayer |
| 10 | Tigran Gambaryan | Binance compliance officer; detained by Nigerian government |

**Next 40:**

| Name | Role at Time |
|------|-------------|
| Adam Sullivan | CEO, Core Scientific (Bitcoin mining) |
| Arthur Hayes | 100x Group / BitMEX founder |
| Avery Ching | Co-founder and CTO, Aptos |
| Balaji Srinivasan | The Network State author; tech/crypto investor |
| Brian Nelson | U.S. Treasury Under Secretary for Terrorism and Financial Intelligence |
| David Tse | Co-founder, Babylon (Bitcoin staking) |
| Eric Balchunas | Bloomberg ETF analyst (paired entry with James Seyffart) |
| James Seyffart | Bloomberg ETF analyst (paired with Eric Balchunas) |
| Eric Semler | CEO, Semler Scientific (corporate Bitcoin treasury) |
| Eric Wall | Crypto investor and commentator (paired with Udi Wertheimer / Taproot Wizards) |
| Udi Wertheimer | Taproot Wizards co-founder (paired with Eric Wall) |
| Francisco Alarcon | Taproot Wizards co-founder |
| Erik Voorhees | Founder, Venice.AI; co-founder, ShapeShift |
| Evan Cheng | Co-founder and CEO, Mysten Labs (Sui) |
| Frank Mong | COO, Helium |
| Fred Thiel | CEO, MARA Holdings (Bitcoin mining) |
| Greg Osuri | CEO, Akash Network |
| Howard Lutnick | CEO, Cantor Fitzgerald; U.S. Commerce Secretary nominee |
| Hunter Horsley | CEO, Bitwise (paired with Matt Hougan) |
| Matt Hougan | CIO, Bitwise (paired with Hunter Horsley) |
| Illia Polosukhin | Co-founder, NEAR Protocol |
| Johnny Ng | Hong Kong lawmaker; crypto regulatory advocate |
| Julia Leung | CEO, Hong Kong SFC |
| Justin Sun | Founder, TRON |
| Keone Hon | Co-founder, Monad |
| Lily Liu | President, Solana Foundation |
| Luca Netz | CEO, Pudgy Penguins [UNCERTAIN — may be Luca Schnetzler from 2023] |
| Luuk Strijers | CEO, Deribit |
| Mahesh Ramakrishnan | Founding partner, EV3 Ventures |
| Matthew Long | Director of Payments, UK FCA |
| Michael Saylor | Executive Chairman, MicroStrategy |
| Paolo Ardoino | CEO, Tether |
| Patrick McHenry | House Financial Services Committee (outgoing Chair) |
| Pavel Durov | Founder, Telegram |
| Ray Chan | CEO, Memeland |
| Richard Teng | CEO, Binance |
| Robin Linus | Creator, BitVM2 (Bitcoin programmability) |
| Rune Christensen | MakerDAO / Sky Protocol co-founder |
| Satoshi Nakamoto | Bitcoin creator — symbolic/honorary inclusion [SYMBOLIC] |
| Sergio Demian Lerner | Co-founder, IOV Labs / Rootstock (Bitcoin L2) |
| Steve Yun | President, TRON Foundation |
| Yat Siu | Co-founder/Chairman, Animoca Brands |
| ZachXBT | On-chain investigator (pseudonymous) [ANON] |

### 2025 — 50 entries, ~25% coverage [INCOMPLETE_YEAR]

| Name | Role at Time |
|------|-------------|
| Donald Trump | 47th U.S. President; signed Bitcoin Strategic Reserve executive order |
| David Sacks | White House AI and Crypto Czar |
| Ross Ulbricht | Silk Road founder; pardoned by Trump January 2025 |
| French Hill | Chair, House Financial Services Committee |
| Cameron Winklevoss | Co-founder, Gemini |
| Tyler Winklevoss | Co-founder, Gemini |
| Paolo Ardoino | CEO, Tether |

---

## Usage Rules for Backend Whitelist

1. **Match by full name only** — do not match on partial names or handles alone
2. **Entries marked MEDIUM** require extra manual confirmation before Platinum assignment
3. **Entries marked EXCLUDE** (ANON, SYMBOLIC, ORG) must not be used in automated matching
4. **Year of appearance is informational only** — does not affect tier assignment (Platinum is binary)
5. **Multiple appearances increase confidence** but do not change tier level
6. **Luca Schnetzler / Luca Netz** — treat as MEDIUM confidence until deduplication is confirmed; require manual verification
7. **"Stark" (2018)** — requires first name confirmation before any backend use
8. **This whitelist is a seed, not a ceiling** — Platinum may be assigned to qualifying individuals not on this list via admin review path

---

## Confidence Summary

| Level | Count | Use |
|-------|-------|-----|
| HIGH | ~145 | Auto-flag for Platinum review queue upon verified onboarding |
| MEDIUM | ~10 | Manual verification required before flagging |
| EXCLUDE | ~18 | Do not include in matching logic |

---

## Update Policy

- This file is updated when new CoinDesk annual lists are published (typically November/December)
- 2025 full list to be completed when published
- Corrections to UNCERTAIN entries should be made as names are independently verified
- v1.2.0 will resolve the Luca Schnetzler / Luca Netz deduplication and confirm Stark's first name

---

*Data sourced from: CoinDesk.com annual lists (via Yahoo Finance mirrors, RootData aggregator, CoinDesk indexed article pages, Kraken blog, Paxos blog, WebSearch snippets). CoinDesk.com returns 403 to automated fetches; all data gathered via mirrors and source-quoting secondary coverage.*
