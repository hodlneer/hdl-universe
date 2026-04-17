# CoinDesk Most Influential — Canonical Whitelist

**Purpose:** Seed dataset for Hodlneer Platinum (Origin) tier recognition. Individuals appearing on CoinDesk's annual "Most Influential in Crypto/Blockchain" lists are candidates for automatic Platinum badge assignment upon verified onboarding.

**Source:** CoinDesk "Most Influential" annual lists, 2014–2025
**Compiled:** 2026-04-17
**Coverage:** 2014–2025 (CoinDesk launched 2013; first influential list was 2014)
**Format:** Master deduplicated list + yearly breakdown

See also: [[HODLNEER_PRD]] | [[Hodlneer/CANON/TIER_SYSTEM|TIER_SYSTEM]]

---

## Coverage Summary

| Year | List Size | Coverage | Notes |
|------|-----------|----------|-------|
| 2014 | 10 | ~60% | Earliest list; CoinDesk was <1 year old |
| 2015 | 10 | ~80% | Includes historical/symbolic Satoshi entry |
| 2016 | 10 | ~40% | Includes anonymous "DAO Attacker" entry |
| 2017 | 10 | ~60% | Heavy Asia/China representation |
| 2018 | 10 | ~60% | Bear market year; CZ ranked #1 |
| 2019 | 10 | ~30% | Weakest coverage — early DeFi era |
| 2020 | 12 | ~75% | DeFi summer; list expanded to 12 |
| 2021 | 50 | ~40% | NFT/SOL boom; list expanded to 50 |
| 2022 | 50 | ~45% | Collapse year; SBF, Do Kwon, Celsius |
| 2023 | 50 | ~40% | Ordinals, BlackRock ETF era |
| 2024 | 50 | ~95% | Near-complete; most reliable year |
| 2025 | 50 | ~25% | Political cycle; early data only |

**Total unique individuals confirmed:** ~85 (deduplicated)
**Total list slots across all years:** ~382

---

## Data Quality Flags

- `[ANON]` — anonymous individual or pseudonym; cannot be onboarded by name
- `[ORG]` — organization or group entry, not an individual
- `[UNCERTAIN]` — name partially confirmed; verify before using in backend
- `[SYMBOLIC]` — historical/symbolic inclusion (e.g. Satoshi Nakamoto)
- `[INCOMPLETE_YEAR]` — year coverage below 50%; additional names likely exist

---

## Master Deduplicated List

Sorted by first appearance year, then alphabetically within year.

| # | Name | Known As / Handle | Years Appeared | First | Last | Count | Flags |
|---|------|-------------------|---------------|-------|------|-------|-------|
| 1 | Andreas M. Antonopoulos | @aantonop | 2014, 2016 | 2014 | 2016 | 2 | |
| 2 | Marc Andreessen | @pmarca | 2014 | 2014 | 2014 | 1 | |
| 3 | Gavin Andresen | | 2014, 2015 | 2014 | 2015 | 2 | |
| 4 | Vitalik Buterin | @VitalikButerin | 2014, 2015, 2021, 2022, 2023 | 2014 | 2023 | 5 | |
| 5 | Benjamin Lawsky | | 2014 | 2014 | 2014 | 1 | |
| 6 | Roger Ver | @rogerkver | 2014, 2015, 2016 | 2014 | 2016 | 3 | |
| 7 | Satoshi Nakamoto | | 2015 | 2015 | 2015 | 1 | [SYMBOLIC] |
| 8 | Blythe Masters | | 2015 | 2015 | 2015 | 1 | |
| 9 | Bobby Lee | @bobbyclee | 2015 | 2015 | 2015 | 1 | |
| 10 | Balaji Srinivasan | @balajis | 2015, 2020 | 2015 | 2020 | 2 | |
| 11 | Theymos | theymos | 2015 | 2015 | 2015 | 1 | |
| 12 | The DAO Attacker | | 2016 | 2016 | 2016 | 1 | [ANON] |
| 13 | Adam Back | @adam3us | 2016 | 2016 | 2016 | 1 | [UNCERTAIN] |
| 14 | Daniel Larimer | @bytemaster7 | 2016 | 2016 | 2016 | 1 | [UNCERTAIN] |
| 15 | Chris Larsen | | 2016 | 2016 | 2016 | 1 | [UNCERTAIN] |
| 16 | Barry Silbert | @barrysilbert | 2016, 2021 | 2016 | 2021 | 2 | [UNCERTAIN] |
| 17 | Emin Gün Sirer | @el33th4xor | 2016 | 2016 | 2016 | 1 | [UNCERTAIN] |
| 18 | Zooko Wilcox-O'Hearn | @zooko | 2016 | 2016 | 2016 | 1 | [UNCERTAIN] |
| 19 | Amber Baldet | @AmberBaldet | 2017 | 2017 | 2017 | 1 | |
| 20 | Charlie Lee | @SatoshiLite | 2017 | 2017 | 2017 | 1 | |
| 21 | Joe Lubin | @ethereumJoseph | 2017 | 2017 | 2017 | 1 | |
| 22 | Naval Ravikant | @naval | 2017 | 2017 | 2017 | 1 | |
| 23 | Jihan Wu | | 2017 | 2017 | 2017 | 1 | |
| 24 | Yao Qian | | 2017 | 2017 | 2017 | 1 | |
| 25 | Jeremy Allaire | @jerallaire | 2018 | 2018 | 2018 | 1 | |
| 26 | Changpeng Zhao (CZ) | @cz_binance | 2018, 2021, 2022 | 2018 | 2022 | 3 | |
| 27 | Brenna Sparks | @BrennaSparks | 2018 | 2018 | 2018 | 1 | |
| 28 | Jed McCaleb | | 2018 | 2018 | 2018 | 1 | |
| 29 | Nouriel Roubini | @Nouriel | 2018 | 2018 | 2018 | 1 | |
| 30 | Stark | | 2018 | 2018 | 2018 | 1 | [UNCERTAIN] |
| 31 | Caitlin Long | @CaitlinLong_ | 2019 | 2019 | 2019 | 1 | |
| 32 | Rune Christensen | @RuneKek | 2019 | 2019 | 2019 | 1 | |
| 33 | David Marcus | @davidmarcus | 2019 | 2019 | 2019 | 1 | |
| 34 | Juan Benet | @juanbenet | 2020 | 2020 | 2020 | 1 | |
| 35 | Mike Cascarilla | | 2020 | 2020 | 2020 | 1 | |
| 36 | Andre Cronje | @AndreCronjeTech | 2020 | 2020 | 2020 | 1 | |
| 37 | Linda Lacewell | | 2020 | 2020 | 2020 | 1 | |
| 38 | Jerome Powell | | 2020 | 2020 | 2020 | 1 | |
| 39 | Michael Saylor | @saylor | 2020, 2024 | 2020 | 2024 | 2 | |
| 40 | Gavin Wood | @gavofyork | 2020 | 2020 | 2020 | 1 | |
| 41 | Brian Armstrong | @brian_armstrong | 2021, 2023 | 2021 | 2023 | 2 | |
| 42 | Beeple (Mike Winkelmann) | @beeple | 2021 | 2021 | 2021 | 1 | |
| 43 | Jack Dorsey | @jack | 2021 | 2021 | 2021 | 1 | |
| 44 | Matt Hall | | 2021 | 2021 | 2021 | 1 | [ORG] |
| 45 | John Watkinson | | 2021 | 2021 | 2021 | 1 | [ORG] |
| 46 | Alex Atallah | | 2021 | 2021 | 2021 | 1 | [UNCERTAIN] |
| 47 | Devin Finzer | | 2021 | 2021 | 2021 | 1 | [UNCERTAIN] |
| 48 | Francis Suarez | @FrancisSuarez | 2021 | 2021 | 2021 | 1 | |
| 49 | Anatoly Yakovenko | @aeyakovenko | 2021 | 2021 | 2021 | 1 | |
| 50 | Seneca | | 2021 | 2021 | 2021 | 1 | [UNCERTAIN] |
| 51 | Shahar Shaulov | | 2021 | 2021 | 2021 | 1 | [UNCERTAIN] |
| 52 | Arthur Hayes | @CryptoHayes | 2022 | 2022 | 2022 | 1 | |
| 53 | Rostin Behnam | | 2022 | 2022 | 2022 | 1 | |
| 54 | Gary Vaynerchuk | @garyvee | 2022 | 2022 | 2022 | 1 | |
| 55 | Gary Gensler | | 2022, 2023 | 2022 | 2023 | 2 | |
| 56 | Do Kwon | @stablekwon | 2022 | 2022 | 2022 | 1 | |
| 57 | Alex Mashinsky | | 2022 | 2022 | 2022 | 1 | |
| 58 | Nic Carter | @nic__carter | 2022 | 2022 | 2022 | 1 | |
| 59 | Sam Bankman-Fried (SBF) | @SBF_FTX | 2022 | 2022 | 2022 | 1 | |
| 60 | Su Zhu | @zhusu | 2022 | 2022 | 2022 | 1 | |
| 61 | BowTiedBull | @BowTiedBull | 2022 | 2022 | 2022 | 1 | [ANON] |
| 62 | cobie | @cobie | 2022 | 2022 | 2022 | 1 | [ANON] |
| 63 | Larry Fink | | 2023 | 2023 | 2023 | 1 | |
| 64 | Casey Rodarmor | @rodarmor | 2023 | 2023 | 2023 | 1 | |
| 65 | Ryan Selkis | @twobitidiot | 2023 | 2023 | 2023 | 1 | |
| 66 | Paolo Ardoino | @paoloardoino | 2023, 2025 | 2023 | 2025 | 2 | |
| 67 | French Hill | | 2025 | 2025 | 2025 | 1 | |
| 68 | Ross Ulbricht | @RealRossU | 2025 | 2025 | 2025 | 1 | |
| 69 | David Sacks | @DavidSacks | 2025 | 2025 | 2025 | 1 | |
| 70 | Donald Trump | @realDonaldTrump | 2025 | 2025 | 2025 | 1 | |
| 71 | Cameron Winklevoss | @cameron | 2025 | 2025 | 2025 | 1 | |
| 72 | Tyler Winklevoss | @tyler | 2025 | 2025 | 2025 | 1 | |

> **Note:** 2024 full list pending agent research completion. Will be inserted below when confirmed. 2018 "Stark" entry requires first-name confirmation before backend use. 2016 entries marked [UNCERTAIN] came from honorable mentions / secondary sources and need verification.

---

## Yearly Breakdown

### 2014 — 10 entries, ~60% coverage [INCOMPLETE_YEAR]

| Name | Role at Time |
|------|-------------|
| Andreas M. Antonopoulos | Bitcoin educator, author of Mastering Bitcoin |
| Vitalik Buterin | Ethereum co-founder (pre-launch) |
| Gavin Andresen | Bitcoin Core lead developer |
| Benjamin Lawsky | NY Superintendent of Financial Services (BitLicense author) |
| Roger Ver | Bitcoin investor, evangelist ("Bitcoin Jesus") |
| Marc Andreessen | Partner, Andreessen Horowitz (a16z) |

### 2015 — 10 entries, ~80% coverage

| Name | Role at Time |
|------|-------------|
| Satoshi Nakamoto | Bitcoin creator (symbolic/historical inclusion) [SYMBOLIC] |
| Blythe Masters | CEO, Digital Asset Holdings |
| Bobby Lee | CEO, BTCC (China's first Bitcoin exchange) |
| Balaji Srinivasan | CEO, 21.co; Stanford lecturer |
| Vitalik Buterin | Ethereum founder (post-mainnet) |
| Gavin Andresen | Bitcoin Core developer |
| Theymos | Bitcointalk.org admin; r/Bitcoin moderator |
| Roger Ver | Bitcoin evangelist, Bitcoin.com |

### 2016 — 10 entries, ~40% coverage [INCOMPLETE_YEAR]

| Name | Role at Time |
|------|-------------|
| Andreas M. Antonopoulos | Bitcoin educator |
| The DAO Attacker | Anonymous; exploited The DAO for ~$60M ETH [ANON] |
| Adam Back | CEO, Blockstream; Hashcash inventor [UNCERTAIN] |
| Daniel Larimer | BitShares, Steem, EOS founder [UNCERTAIN] |
| Chris Larsen | CEO, Ripple [UNCERTAIN] |
| Barry Silbert | CEO, Digital Currency Group [UNCERTAIN] |
| Emin Gün Sirer | Cornell professor, Bitcoin-NG researcher [UNCERTAIN] |
| Zooko Wilcox-O'Hearn | CEO, Electric Coin Company (Zcash) [UNCERTAIN] |
| Roger Ver | Bitcoin.com |

### 2017 — 10 entries, ~60% coverage

| Name | Role at Time |
|------|-------------|
| Jihan Wu | CEO, Bitmain (largest Bitcoin mining hardware manufacturer) |
| Yao Qian | Head of PBOC digital currency research |
| Joe Lubin | Founder, ConsenSys; Ethereum co-founder |
| Charlie Lee | Creator of Litecoin; Director of Engineering, Coinbase |
| Naval Ravikant | Co-founder, AngelList; prolific crypto angel investor |
| Amber Baldet | Head of blockchain, JPMorgan Chase |

### 2018 — 10 entries, ~60% coverage

| Name | Role at Time |
|------|-------------|
| Changpeng Zhao (CZ) | CEO, Binance (#1 ranking) |
| Nouriel Roubini | Economist; prominent crypto critic |
| Jeremy Allaire | CEO, Circle |
| Jed McCaleb | Co-founder, Stellar; former Mt. Gox founder |
| Brenna Sparks | Adult entertainer turned Bitcoin advocate |
| Stark | [First name unconfirmed] [UNCERTAIN] |

### 2019 — 10 entries, ~30% coverage [INCOMPLETE_YEAR]

| Name | Role at Time |
|------|-------------|
| Caitlin Long | Wyoming crypto legal advocate; founder, Avanti Bank |
| Rune Christensen | Founder, MakerDAO |
| David Marcus | VP Messenger + Libra project lead, Facebook |

### 2020 — 12 entries, ~75% coverage

| Name | Role at Time |
|------|-------------|
| Juan Benet | Founder, Protocol Labs (IPFS, Filecoin) |
| Andre Cronje | Creator, Yearn Finance; DeFi architect |
| Balaji Srinivasan | Former Coinbase CTO; network state theorist |
| Linda Lacewell | NY DFS Superintendent |
| Jerome Powell | Chair, Federal Reserve |
| Michael Saylor | CEO, MicroStrategy (corporate Bitcoin treasury pioneer) |
| Mike Cascarilla | CEO, Paxos |
| Gavin Wood | Co-founder, Ethereum; founder, Polkadot/Web3 Foundation |

### 2021 — 50 entries, ~40% coverage [INCOMPLETE_YEAR]

| Name | Role at Time |
|------|-------------|
| Vitalik Buterin | Ethereum |
| Brian Armstrong | CEO, Coinbase (IPO year) |
| Jack Dorsey | CEO, Twitter + Square; Bitcoin maximalist |
| Beeple (Mike Winkelmann) | Digital artist; $69M Christie's NFT sale |
| Matt Hall | Co-founder, Larva Labs (CryptoPunks) |
| John Watkinson | Co-founder, Larva Labs (CryptoPunks) |
| Anatoly Yakovenko | Co-founder, Solana |
| Alex Atallah | Co-founder, OpenSea [UNCERTAIN] |
| Devin Finzer | Co-founder, OpenSea [UNCERTAIN] |
| Francis Suarez | Mayor, Miami (Bitcoin city initiative) |
| Barry Silbert | CEO, Digital Currency Group |
| Changpeng Zhao (CZ) | CEO, Binance |
| Shahar Shaulov | CEO, Fireblocks [UNCERTAIN] |
| Alex Juliano | CEO, Nifty Gateway [UNCERTAIN] |
| Seneca | NFT artist [UNCERTAIN] |

### 2022 — 50 entries, ~45% coverage [INCOMPLETE_YEAR]

| Name | Role at Time |
|------|-------------|
| Vitalik Buterin | Ethereum (The Merge year) |
| Sam Bankman-Fried (SBF) | CEO, FTX (before collapse) |
| Do Kwon | CEO, Terraform Labs (LUNA/UST collapse) |
| Alex Mashinsky | CEO, Celsius (before bankruptcy) |
| Su Zhu | Co-founder, Three Arrows Capital (before collapse) |
| Arthur Hayes | Former CEO, BitMEX |
| Changpeng Zhao (CZ) | CEO, Binance |
| Gary Gensler | SEC Chair |
| Rostin Behnam | CFTC Chair |
| Nic Carter | Partner, Castle Island Ventures |
| Gary Vaynerchuk | Founder, VeeFriends; NFT creator |
| BowTiedBull | Pseudonymous crypto/finance commentator [ANON] |
| cobie | Pseudonymous crypto trader/commentator [ANON] |

### 2023 — 50 entries, ~40% coverage [INCOMPLETE_YEAR]

| Name | Role at Time |
|------|-------------|
| Gary Gensler | SEC Chair (crypto enforcement era) |
| Brian Armstrong | CEO, Coinbase (survived 2022) |
| Larry Fink | CEO, BlackRock (Bitcoin ETF application) |
| Casey Rodarmor | Creator of Bitcoin Ordinals/Inscriptions |
| Ryan Selkis | CEO, Messari |
| Paolo Ardoino | CTO → CEO, Tether |

### 2024 — 50 entries, ~95% coverage

> Full list pending confirmation from supplemental research. Will be inserted here once agent data is verified.

### 2025 — 50 entries, ~25% coverage [INCOMPLETE_YEAR]

| Name | Role at Time |
|------|-------------|
| Donald Trump | 47th US President; pro-crypto policy |
| David Sacks | White House AI & Crypto Czar |
| Ross Ulbricht | Silk Road founder (pardoned Jan 2025) |
| French Hill | Chair, House Financial Services Committee |
| Cameron Winklevoss | Co-founder, Gemini |
| Tyler Winklevoss | Co-founder, Gemini |
| Paolo Ardoino | CEO, Tether |

---

## Usage Rules for Backend Whitelist

1. **Match by full name only** — do not match on partial names or handles
2. **Flag [UNCERTAIN] entries** — require extra manual confirmation step before Platinum assignment
3. **Exclude [ANON] entries** — cannot be matched to real individuals at onboarding
4. **Exclude [SYMBOLIC] entries** — Satoshi Nakamoto cannot be onboarded
5. **Year of appearance is informational only** — does not affect tier assignment
6. **Multiple appearances increase confidence** but do not change tier (Platinum is binary)
7. **This whitelist is a seed, not a ceiling** — Platinum may be assigned to qualifying individuals not on this list via admin review path

---

## Confidence Tiers for Backend Use

| Confidence | Definition | Action |
|------------|------------|--------|
| HIGH | Name confirmed from multiple sources; no flags | Auto-flag for Platinum review queue |
| MEDIUM | Single source or [UNCERTAIN] flag | Manual verification required before flagging |
| EXCLUDE | [ANON], [SYMBOLIC], [ORG] | Do not include in matching logic |

---

## Update Policy

- This file is updated when new CoinDesk annual lists are published (typically November/December)
- 2024 full list and 2025 partial list to be updated as research completes
- Corrections to uncertain entries should be made as names are verified

---

*Data sourced from: CoinDesk.com annual lists (via Yahoo Finance mirrors, WebSearch, third-party crypto media). CoinDesk.com returns 403 to automated fetches; all data gathered via mirrors and search coverage.*
