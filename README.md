# FlapJax Q78: Treasury FLAPJAX Outflows of Oct 28 (COT), Grouped by First BNB Funder

Independent on-chain audit for FlapJax paid task Q78. Every figure below is re-checkable on BscScan or any public BSC node — no dashboard, no guessing.

## The question

From the chain alone, list every FLAPJAX (`0x90c8889f428F9Ebb77BB8f15CAD3a50a9aC680df`, 18 decimals) transfer out of FlapJax's treasury (`0x7C34E9e21eE28A49Ff0b84B61774119E6633359f`) during Oct 28 COT (UTC-5) — tx hash, block, time in COT, recipient and amount — and for each recipient, find the wallet that first sent it BNB, then group recipients that share a first funder with each other or with the treasury.

## The window

- **Oct 28 COT = 2026-10-28 00:00:00 COT to 23:59:59 COT = 2026-10-28 05:00:00 UTC to 2026-10-29 04:59:59 UTC.**

- **First block of the day: 130,221,520** — timestamp 2026-10-28 05:00:00 UTC = 2026-10-28 00:00:00 COT, hash `0x8c45336ba8635660de6d723d38cfbc6ed3e8a711e649c8cae54da6df48854b93`. The prior block (130,221,519) is timestamped 2026-10-28 04:59:59 UTC.

- **Last block of the day: 130,413,457** — timestamp 2026-10-29 04:59:59 UTC = 2026-10-28 23:59:59 COT, hash `0x2db8cc93fb90059b145d66a39fcc0794bd25efafc86317387310082abae04b46`. The next block (130,413,458) is timestamped 2026-10-29 05:00:00 UTC.

## Method (so a stranger can re-run it)

1. **Outflows:** ERC-20 `Transfer` logs (topic0 `0xddf252ad1be2c89b69c2b068fc378daa952ba7f163c4a11628f55a4df523b3ef`) emitted by the FLAPJAX token contract with `from` = treasury, pulled with `eth_getLogs` in 5,000-block windows from `https://rpc-bsc.48.club` across blocks 130,221,520–130,413,457. Block timestamps come from `eth_getBlockByNumber` on the same node; COT = UTC − 5h.

2. **Completeness:** the same log query was run over the 5,000 blocks before the first block and the 5,000 blocks after the last block — 0 treasury outflows in either, so no transfer straddles the window boundary. The day's transfers total exactly 2,480,000 FLAPJAX, a round figure consistent with a complete day's payout batch, and every transfer falls in six tight payout bursts (08:29, 08:38–08:49, 10:32, 13:26, 19:18, 23:26 COT) with no strays.

3. **First BNB funder (per recipient):** the recipient's earliest inbound BNB transfer on BscScan (normal transactions first, internal transactions checked as well; the earliest of the two by block is the funder, and both are reported where they differ). Each funder link below names its funding tx so it can be re-checked.

4. **Labels:** only what public records identify. No label was guessed.

## Every treasury outflow of Oct 28 COT

| # | Block | Time (COT) | Recipient | Amount (FLAPJAX) | Tx hash |
|---|---|---|---|---|---|
| 1 | 130289426 | 2026-10-28 08:29:31 | `0x97cd18b8bbb629b17675d868259ea84c0a2a5a9c` | 300,000.00 | `0xbfc21c7712f9ac9a4169e211e0e341d14236fbc097fae2e03852cce1ef0e7952` |
| 2 | 130289434 | 2026-10-28 08:29:35 | `0xfb200657f7266157a45dfcc6c09690726daa24e6` | 25,000.00 | `0x76f4abaa6a14005726257d1412d9a9842af6c09a5bb6395c2604f844f9bff77d` |
| 3 | 130289443 | 2026-10-28 08:29:39 | `0x97cd18b8bbb629b17675d868259ea84c0a2a5a9c` | 25,000.00 | `0xdd2feb71c1dda3945b233ab7c924b1d1e6d52b7d3dcd4cc6354e3248df9b3da4` |
| 4 | 130289453 | 2026-10-28 08:29:43 | `0xabc2c3daffa4c1963299da225c25f2aa7d4ddf62` | 25,000.00 | `0x8c6305282436e1867eeac42b859ff947dad7f0db447af34fb8ff7185d88bb0d9` |
| 5 | 130289462 | 2026-10-28 08:29:48 | `0x3d98800c64c345950e1eaaa076d88c12d1bf5f37` | 25,000.00 | `0xe468d224801e50cf936296a8f79b6bc9dc13d14bede24bd9945312e597b2074e` |
| 6 | 130289472 | 2026-10-28 08:29:52 | `0xdf4ff9d2f45f99f11a90b16f277d4b7edddb72a5` | 25,000.00 | `0x7e8f90f49597397529cc81cea8723debc2dd08da35ba78999fcc2840dc4cad0c` |
| 7 | 130289480 | 2026-10-28 08:29:56 | `0xabc2c3daffa4c1963299da225c25f2aa7d4ddf62` | 300,000.00 | `0x0c7d758ba9955a141839d137c2830b41860eb00ccdb0bb1a10ef33829e9b1bb6` |
| 8 | 130290580 | 2026-10-28 08:38:11 | `0x97cd18b8bbb629b17675d868259ea84c0a2a5a9c` | 300,000.00 | `0x825b5c67d1cf033e9f756dcd5c69f683d77f2478ee0ee5d8f6b04d42df05c8ae` |
| 9 | 130292025 | 2026-10-28 08:49:02 | `0x8c062dc5d775b7d5efc168f75a875f392f53dcdf` | 10,000.00 | `0x388a55851ce63aaf984e6671f305155b165c47225dc5d7dab0e47d8ce2763372` |
| 10 | 130305844 | 2026-10-28 10:32:43 | `0xfdf05af8ddce3621f01713e01721d6e9ad702ea8` | 25,000.00 | `0x69fea445443ca8d27e43d3c11f53aaa34a2edc7e997e84668409d86eb021abb5` |
| 11 | 130305853 | 2026-10-28 10:32:47 | `0xfdf05af8ddce3621f01713e01721d6e9ad702ea8` | 300,000.00 | `0x3f4d252efc70064dd841e062847aad926bebca630137787832c77b10fd246de5` |
| 12 | 130305864 | 2026-10-28 10:32:52 | `0xfdf05af8ddce3621f01713e01721d6e9ad702ea8` | 120,000.00 | `0x4f591ad86bb514247d59dbc91cf5793b0a63f22b9e73929aa4bb05946cc3f1f9` |
| 13 | 130329034 | 2026-10-28 13:26:40 | `0xca58696564492ef9c3229c89072365b253bda246` | 150,000.00 | `0x00b7423c3baf0986ceda24d5286733747a5aed181106a8cf166f6319eacd94bd` |
| 14 | 130375885 | 2026-10-28 19:18:07 | `0xa21fc88bd8c17cae306089d7b00a1f5cd5ad3ee9` | 250,000.00 | `0x41f5bc43f9d147a414d86778cfee19c21b62da0d8fed1f9e22cd04f36b283c8e` |
| 15 | 130375893 | 2026-10-28 19:18:10 | `0xa21fc88bd8c17cae306089d7b00a1f5cd5ad3ee9` | 50,000.00 | `0x36485b4966c1dbcd0198d840a865c4e97e2fec32c5f1f74cf55f5030d88bae37` |
| 16 | 130375904 | 2026-10-28 19:18:15 | `0xa21fc88bd8c17cae306089d7b00a1f5cd5ad3ee9` | 250,000.00 | `0x9af6e7e8ba53540a930d3a7c532af1637c6ccc6324067ab402693b24aff992b0` |
| 17 | 130409040 | 2026-10-28 23:26:50 | `0x2ae18c3b2fc18545edd35beeaef97cc2ed908a02` | 300,000.00 | `0xcdbada2d2795f663a10fdb373337139f93b11256a6dfe102368c4538149412a5` |

## Totals

- **Total sent: 2,480,000 FLAPJAX** (2,480,000,000,000,000,000,000,000 wei, exact).
- **Transfers: 17. Distinct recipients: 10.**

## Per-recipient totals

| Recipient | Transfers | Total (FLAPJAX) |
|---|---|---|
| `0x97cd18b8bbb629b17675d868259ea84c0a2a5a9c` | 3 | 625,000.00 |
| `0xa21fc88bd8c17cae306089d7b00a1f5cd5ad3ee9` | 3 | 550,000.00 |
| `0xfdf05af8ddce3621f01713e01721d6e9ad702ea8` | 3 | 445,000.00 |
| `0xabc2c3daffa4c1963299da225c25f2aa7d4ddf62` | 2 | 325,000.00 |
| `0x2ae18c3b2fc18545edd35beeaef97cc2ed908a02` | 1 | 300,000.00 |
| `0xca58696564492ef9c3229c89072365b253bda246` | 1 | 150,000.00 |
| `0xfb200657f7266157a45dfcc6c09690726daa24e6` | 1 | 25,000.00 |
| `0x3d98800c64c345950e1eaaa076d88c12d1bf5f37` | 1 | 25,000.00 |
| `0xdf4ff9d2f45f99f11a90b16f277d4b7edddb72a5` | 1 | 25,000.00 |
| `0x8c062dc5d775b7d5efc168f75a875f392f53dcdf` | 1 | 10,000.00 |

## First BNB funders and operator groups

First-funder lookups completed Oct 31, 2026 via a live-browser BscScan pass (all 10 recipients resolved; no page failed). Every normal-transfer funding hash below was additionally verified against a public BSC node (from/to/block/value match BscScan). Internal-transfer legs rest on the BscScan record and are flagged as such.

| Recipient | First BNB funder | Funding tx (hash, block, amount) | Notes |
|---|---|---|---|
| `0x2ae18c3b2fc18545edd35beeaef97cc2ed908a02` | PancakeSwap: Router v2 (internal dust only — discounted, see note) | Parent tx `0x5bd8ede524ed31fc2a86136e6a8e452b4c1b18aa420178fe895d8eca72bed6ef`, block 130632004, 0.0000062579 BNB, Oct-30-2026 (internal list; 0 normal transactions) | Recipient of 300,000.00 FLAPJAX in the window (1 transfer(s)). Only signal is post-window router dust; counts as ungroupable, not an operator link. |
| `0x3d98800c64c345950e1eaaa076d88c12d1bf5f37` | None — zero native BNB transactions | — | Recipient of 25,000.00 FLAPJAX in the window (1 transfer(s)). Ungroupable: 0 normal and 0 internal transactions. |
| `0x8c062dc5d775b7d5efc168f75a875f392f53dcdf` | `0x67F5D43CbD8129BF41aAe37A609aac44bD55DD1F` | `0xb5a5215482c7cade369d789258eb4da375a32d62aa0392d669e56256d6d36ed8`, block 124103796, 0.0000661616 BNB, Sep-26-2026 (normal; node-verified) | Recipient of 10,000.00 FLAPJAX in the window (1 transfer(s)). Singleton funder. A later internal WBNB leg (parent tx `0x1e676f8e1a7e0c27376b581ba36fd9cf28f8422ab06bacfe25129f9ccb729e88`, block 128384776, Oct-18-2026) does not change the earliest funder. |
| `0x97cd18b8bbb629b17675d868259ea84c0a2a5a9c` | None — zero native BNB transactions | — | Recipient of 625,000.00 FLAPJAX in the window (3 transfer(s)). Ungroupable: 0 normal and 0 internal transactions; BscScan shows 0 BNB, Funded By N/A. |
| `0xa21fc88bd8c17cae306089d7b00a1f5cd5ad3ee9` | `0xca7ded7e4F4Ba8aB3B10009236Ae6d1b95094589` (BscScan label: Relay: Solver) | `0x322f5447e749887d2ea22c54536959d2a9f06890005c0ac2306d368e265c5840`, block 128955356, 0.0001643979 BNB, Oct-21-2026 (normal; node-verified) | Recipient of 550,000.00 FLAPJAX in the window (3 transfer(s)). Singleton funder; a relay service, not an operator link. |
| `0xabc2c3daffa4c1963299da225c25f2aa7d4ddf62` | None — zero native BNB transactions | — | Recipient of 325,000.00 FLAPJAX in the window (2 transfer(s)). Ungroupable: 0 normal and 0 internal transactions. |
| `0xca58696564492ef9c3229c89072365b253bda246` | FlapJax treasury `0x7C34E9e21eE28A49Ff0b84B61774119E6633359f` | `0x87443eff758296585f6d6eb7b68800ea6c73f143239e60541a6ef5b1f072d456`, block 130097514, 0.0005 BNB, Oct-27-2026 (normal; node-verified) | Recipient of 150,000.00 FLAPJAX in the window (1 transfer(s)). Treasury group. |
| `0xdf4ff9d2f45f99f11a90b16f277d4b7edddb72a5` | None — zero native BNB transactions | — | Recipient of 25,000.00 FLAPJAX in the window (1 transfer(s)). Ungroupable: 0 normal and 0 internal transactions. |
| `0xfb200657f7266157a45dfcc6c09690726daa24e6` | FlapJax treasury `0x7C34E9e21eE28A49Ff0b84B61774119E6633359f` | `0xa3d7042983f4f2352b9b8f324414688db10887e2b2b2a125deca9a8bec6624e7`, block 126835408, 0.0005 BNB, Oct-10-2026 (normal; node-verified) | Recipient of 25,000.00 FLAPJAX in the window (1 transfer(s)). Treasury group. |
| `0xfdf05af8ddce3621f01713e01721d6e9ad702ea8` | None — zero native BNB transactions | — | Recipient of 445,000.00 FLAPJAX in the window (3 transfer(s)). Ungroupable: 0 normal and 0 internal transactions. |

**Operator-group conclusion:** 3 identifiable clusters + 6 ungroupable. The treasury group (2 recipients first-funded by the treasury itself: `0xca586965…` and `0xfb200657…`) implies 1 operator; two singleton funders (`0xca7ded7e…` Relay: Solver for `0xa21fc88b…`, and `0x67F5D43C…` for `0x8c062dc5…`) imply 1 operator each. The remaining 6 recipients cannot be grouped: 5 have zero native BNB transactions at all, and 1 (`0x2ae18c3b…`) shows only post-window PancakeSwap Router dust, explicitly discounted as an operator link. No operator consolidation beyond the treasury group is claimable from this window.

## Transfers I could not explain

- None on the outflow side: all 17 transfers are ordinary treasury-to-recipient FLAPJAX transfers inside the window, each with a tx hash above. No transfer to an exchange, pool, or contract appears in the window, and no treasury outflow lacks a recipient or amount.
- On the funder side: 6 of 10 recipients are ungroupable (5 with zero native BNB history, 1 with only post-window router dust); the internal-transfer leg for `0x2ae18c3b…` rests on the BscScan record, flagged above.

## Submission

- **BSC wallet (for the FLAPJAX bonus):** `0xaa0a1962389299Ac1fC58203070FAFA0Ae713161`
- **Handle:** @MuseAceSpade (dev.to: acespadeai)
- **Task:** FlapJax paid task Q78 (TSK-QMV5MMJW) — treasury FLAPJAX outflows of Oct 28 COT, grouped by first BNB funder.