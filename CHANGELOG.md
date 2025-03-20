## [0.3.0] - 03/15/2025

### Tactival VIVI - Group/Channels Notifications for DexScreener Profiles

- The bot can now be added to groups or channels to receive notifications about new token profiles from DexScreener.
- Group admins can enable notifications with `/notify_on`, and the bot will periodically post alerts in all enabled chats.
- Stay updated on token activity—and join our channel for more updates: [TacticalVIVI](https://t.me/TacticalVIVI).

## [0.2.9] - 03/13/2025

### Group-Level Token Transfers

- **Balance Command:**  
  The `@VIVIBaseBot balance` command shows the selected wallet’s ETH balance along with a list of token holdings.
- **Access Control:**  
  These group-level commands remain restricted to registered bot users only.

## [0.2.8] - 03/09/2025

### Group-Level Token Transfers

- **Send, Transfer and Burn Commands (Group):**  
  Users can now execute token transfers `@VIVIBaseBot send` (send), `@VIVIBaseBot burn` burn tokens, and transfer ETH directly from groups.
  - Supports both numerical amounts as well as the keywords “half” and “all” to indicate percentages of the wallet’s holdings.
  - Displays appropriate feedback and updates balances accordingly.
- **Access Control:**  
   These group-level commands remain restricted to registered bot users only.

## [0.2.7] - 03/07/2025

### Group-Level Trading Commands

- **Buy and Sell in Groups:**  
  The bot now supports executing the `@VIVIBaseBot buy` and `@VIVIBaseBot sell` commands directly in groups.
  - Users can swap tokens from within group chats without needing to switch to private chat.
  - Commands are available exclusively for users registered in the bot.
- **Access Control:**  
   These group-level commands remain restricted to registered bot users only.

## [0.2.6] - 03/06/2025

### Best Dex and Quotes

- Improved overall speed when fetching the most advantageous quote across supported DEXs.

### Uniswap V4 Indexer

- **Indexer for Uniswap V4**: Init new indexer to gather pool data from Uniswap V4, including PoolManager and StateView logic.

  - _Note_: Swap functionality coming soon.

### Points System

- Finished x2 rewards promotion (no more extra points). Back to regular points earnings.

## [0.2.5] - 02/28/2025

### Zero-Fee Buying for Coinbase BTC (cbBTC)

- **No-Fee Swaps:** Users can now buy cbBTC without any platform fees, reducing costs while incentivizing healthy portfolio management

## [0.2.4] - 02/27/2025

### Enhanced Buy and Sell Scenes

- **Detailed Token Statistics:** The scenes now display comprehensive token data including current holders, circulating supply, and basic market statistics to help users assess token health.
- **Optimized Swap Quotes:** Users receive improved swap quotes that show the buy amount alongside the expected output from the best available DEX (covering Uniswap V2, Uniswap V3, and Aerodrome). This allows for better comparison and decision-making.
- **Unified Interface:** The updated design integrates token stats, swap quotes, and key market indicators into a single, cohesive view for a more informed and seamless trading experience.

## [0.2.3] - 02/21/2025

### Points System

- Hot Weekend Special: Users Earn 2x Points from Friday 21/02 to Monday 24/02, 1PM UTC

## [0.2.2] - 02/18/2025

### Referral System

- **User Referrals**:

  - A new `Referral` button in the main menu shows your personal link and referral stats.
  - Each user can now generate a unique referral link (`https://t.me/<botName>?start=ref_<tgUsername>`).
  - When a new user registers via this referral link, the user who referred them immediately receives **690 points**.
  - The referrer earns a percentage of the points generated from each trade made by their referred user. This bonus is extra and does not reduce the referred user's points.

    - For every 0.0002 ETH in referral trading volume = 1 point is awarded

## [0.2.1] - 02/17/2025

### Trading Bot Integrations

- **YapTrade DAO**: New token in DAOS.WORLD, 50% discount on service fees, 20% bonus points

## [0.2.0] - 02/17/2025

### Trading Bot Integrations

- **Base Mainnet** support for on-chain operations
- **Dex** integrations on Base Mainnet:
  - Aerodrome Finance
  - Uniswap V2
  - Uniswap V3

### Trading Bot Scenes and Commands

- **Commands**:

  - `/start`: Initialize usage, create first wallet, and open main menu
  - `/settings`: Access or modify user settings (Buy, Sell, Speed)
  - `/buy`: Open the buy menu using preset user settings
  - `/sell`: Open the sell menu using preset user settings
  - `/qb`: Quick buy (contract address, amount in ETH, optional slippage)
  - `/qs`: Quick sell (contract address, % of tokens, optional slippage)
  - `/wallets`: List and create wallets (Max 7 wallets)
  - `/holdings`: Display tokens with current balances, manually add tokens from external wallets
  - `/withdraw`: Withdraw ETH or tokens
  - `/help`: How it works & FAQs
  - `/feedback`: Provide feedback to the dev team
  - `/login`: Generate a web login URL to access the VIVI dashboard

- **Buy Tokens**: Sending any valid contract address automatically triggers the buy scene with that token pre-selected.

- **Settings Scene**:
  - **Buy Settings**: 5 customizable default amounts, plus default slippage
  - **Sell Settings**: 3 customizable default % for selling, plus default slippage
  - **Speed Settings**: Normal, Fast, Turbo (default: Normal)

### Points System

- **Leaderboard**: Top [redacted] traders gain eligibility for VIVI DAO PRESALE, access from `/login` command.
- **Scoring**: 0.0001 ETH in volume = 1 point
- **DAOS.WORLD** tokens yield 20% bonus points
- **DAOS.WORLD** tokens enjoy a 50% discount on service fees (0.5% instead of 1%)
