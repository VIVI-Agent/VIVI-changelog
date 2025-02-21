## [0.2.3] - 02/18/2025

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
