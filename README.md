# City Tycoon — Complete Gameplay Update

A browser-based 2D property-trading game: one human player against three computer opponents.

## Run the game

1. Extract the ZIP archive.
2. Open `index.html` in a modern browser.
3. Keep all three files (`index.html`, `style.css`, and `game.js`) in the same folder.

No installation or internet connection is required to play the browser version.

## Implemented gameplay

- **Board and players:** 28 spaces, 16 properties, four players, $1,500 starting cash, clear player cards, live cash/net-worth/position tracker, and a recent-events log.
- **Dice and movement:** colorful animated dice; player tokens travel space-by-space with a highlighted route and landing effect. Direct moves to Start or Jail highlight the destination without incorrectly walking along the previous route. Reduced-motion preferences are respected.
- **Start payments:** pass Start and land beyond it to collect $200; land directly on Start to collect $300 total. Backward movement does not award Start money.
- **Properties:** buying, regular auctions, rent, 50% complete-group rent bonus, and up to three upgrade levels. Upgrades must be distributed evenly.
- **Property management:** sell only upgrades that preserve even building, receiving 50% of their original cost; mortgage properties for 75% of listed price; upgrades stay attached to mortgaged properties; repay mortgages at the mortgage payout plus 10%. Mortgaged properties do not collect rent or qualify for group rent bonuses.
- **Negotiated trades:** offer to buy AI-owned properties or offer your properties to AI opponents for cash. AI acceptance depends on the offer, cash reserve, and group strategy. Properties cannot be sold directly back to the bank.
- **Chance and Community Chest:** 12 cards in each deck, with rewards, payments, movement, Jail, repairs, and a Get Out of Jail Free card. Decks use draw/discard piles; a held Jail card is not duplicated and returns to the discard pile when used or when its owner is eliminated. Card-based payments per upgrade are calculated before liquidation starts.
- **Jail:** pay $100 before rolling, use a Get Out of Jail Free card, or attempt doubles for up to three turns. Jail doubles do not grant another roll. On the third failed attempt, pay $100 and move using that roll. Three consecutive doubles during ordinary movement send a player directly to Jail without completing the third move.
- **Debt and bankruptcy:** payments use cash, then legal upgrade sales, then mortgages. If the debt still cannot be paid, the player is eliminated; properties are auctioned, a player creditor receives eligible auction proceeds up to the remaining debt, and unpaid debt is forgiven. The bank has unlimited funds; Free Parking has no cash pot.
- **Computer opponents:** strategic property purchases, more competitive auctions, and upgrades when they can retain a cash reserve. AI players take turns automatically.
- **Victory:** (1) immediate win at $10,000 net worth; (2) last player remaining after bankruptcies; or (3) highest net worth after 25 completed rounds. Tie-breakers are cash, then net worth excluding cash; any remaining tie is shared.

## Testing performed

- JavaScript syntax check passed (`node --check game.js`).
- Automated logic smoke tests passed for board size and startup, group rent, even upgrades and upgrade sales, mortgages, all three victory conditions, Start rewards, direct Start/Jail relocation state, Jail-card recycling, negotiated property trade, and bankruptcy/creditor payment.
- HTML validation passed: IDs are unique and referenced CSS/JavaScript files exist.
- A complete interactive browser playthrough has **not** been verified in this environment. Please check a normal turn, an unowned-property auction, a Chance/Community Chest card, a mortgage, a trade, and a victory before treating every interaction as fully confirmed.

## Not included in this build

Local multiplayer, online multiplayer, Android packaging, and 3D-style graphics remain future expansion stages. The browser game does not currently save a game after the page is refreshed.
