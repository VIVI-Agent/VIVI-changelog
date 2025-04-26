# Changelog

## [0.4.2] - 04/25/2025

### Group Commands - Base Names (BNS) Integration

- **Send/Transfer to BNS Names**: Users can now send tokens and ETH directly to Base Names (.base.eth) in group chats

  ```
  @VIVIBaseBot send 0.1 ETH vivi.base.eth
  @VIVIBaseBot transfer 50 USDC satoshi.base.eth
  ```

This brings Web3 identity support to our group transfer system, making it easier for users to send assets using memorable names instead of complex addresses.

## [0.4.1] - 04/23/2025

### UI/UX Improvements

- **Radar Display Enhancement**: Improved text alignment for notification messages to ensure cleaner, more readable alerts.
- **Input Format Flexibility**: Added support for both decimal points (.) and commas (,) in numerical inputs for token amounts, ETH values, and percentages to accommodate users with different locale preferences.
- **Group Buy Competition Commands**: Fixed a critical issue where administrators creating a buy event couldn't execute other commands like buy, sell, or balance during event creation.
  - Added `/cancelcreation` command to quickly abort event creation
  - Implemented friendly reminders when users attempt to run commands during event creation
  - Added better error handling and message cleanup

### Command Enhancements

- **Percentage Symbol Support**: The sell command now properly handles percentage symbols (%) when specifying sell amounts (e.g., `sell 25%` now works alongside `sell 25`).
- **Transfer Command Alias**: Added `transfer` as an alias for the `send` command with identical functionality to match user expectations.
- **Non-Whitelisted Token Message**: Improved error messages for non-whitelisted tokens with a link to contact the VIVI team for whitelisting requests.

### Transaction Optimization

- **Gas Estimation Improvements**: Completely revamped transaction fee estimation system:
  - Implemented operation-specific gas limits based on transaction type (BUY, SELL, APPROVE, TRANSFER)
  - Added dynamic gas adjustment for larger transactions
  - Configured speed-based priority fee settings with separate profiles for buy/sell operations
  - Optimized fee multipliers to prevent transaction failures while minimizing costs

### Bug Fixes

- Fixed an issue where group buy competition administrators couldn't use essential commands while creating an event
- Resolved error handling in notification system that caused misaligned text in alerts
- Fixed number parsing issues for users with non-US locale settings

## [0.4.0] - 04/22/2025

### WALLET MANAGEMENT - Export Private Key

- **Export Wallet Feature**: Users can now securely export their private keys through the Wallet Management interface.
  - Access via the new "Export Wallet" button in the Wallets menu
  - Private keys are automatically deleted after 30 seconds or upon user confirmation
  - Export multiple wallet keys in sequence as needed

## [0.3.9] - 04/21/2025

### Group Bot - Token transfers unlocked across all Telegram

Users can now send tokens to any Telegram user, even if they’re not in the same group chat.

### Group Bot - Expanded Balance Command

- **@username Balance**  
  Any user can now trigger `/balance` for any Telegram user, in any group chat.

```
@VIVIBaseBot balance @username
```

## [0.3.8] - 04/17/2025

### BUY COMPETITION FEATURE (Telegram Group Chats) — Open to all groups

- **Group Buy Event System**  
  Admins (**on any group**) can now launch _Buy Events_ on a _specific ERC-20 Token_.
  These events allow users to compete by buying tokens and climbing the leaderboard.

## [0.3.7] - 04/15/2025

### VIVI's Radar Expansion

- **Add CLIZA**  
  Now listens for Cliza `Deploy Token`, retrieves new tokens, tracks volume, and notifies on threshold (0.05 ETH Volume).

## [0.3.6] - 04/14/2025

### WALLET MANAGEMENT - Import Wallet

- **Import Wallet Feature** Users can now import existing wallets via private key through the Wallet Management interface.
  - Secure encryption of imported private keys using the same protection as generated wallets.
  - Duplicate wallet detection to prevent importing the same wallet multiple times.
  - Newly imported wallets are automatically set as the default wallet.
  - After import, users can go to `/holdings` to import tokens associated with the wallet.

## [0.3.5] - 04/03/2025

### BUY COMPETITION FEATURE (Telegram Group Chats) — _MVP_

- **Group Buy Event System**  
  Admins can now launch _Buy Events_ on a _specific ERC-20 Token_.
  These events allow users to compete by buying tokens and climbing the leaderboard.

- **Buy Event Wizard** (`/createbuyevent`)  
  Admins can start an interactive scene:

  - Name the event, upload a banner, and set the token address.
  - Includes validation for image dimensions (1280x360 recommended).
  - Previews the summary before launch with inline confirmation.

- **Leaderboard System** (`/leaderboard` - `/myeventstat` )

  - Shows top 10 buyers with total ETH spent and buy count.
  - Highlights the _biggest buy_ and the user with the _most purchases_.
  - Leaderboard banners are supported for better visual context.

- **User Commands Summary**

  - `/createbuyevent`: _(Group Admin)_ Starts the wizard to launch a new buy event.
  - `/closebuyevent`: _(Group Admin)_ Allows admins to manually close an ongoing event.
  - `/leaderboard`: Shows the current or most recent leaderboard.
  - `/myeventstat`: Displays a user’s personal rank and ETH spent.

- **Preview Mode Notice**  
  This feature is currently restricted to a set of authorized groups as part of a closed testing phase.

## [0.3.4] - 04/01/2025

### DexScreener & Internal Improvements

- **New DexScreener Message Format**  
  When a DexScreener profile is detected for a token already flagged by volume, the bot now sends an update with the new style.

- **Twitter links improved**
  Includes a refined Twitter search link.

- **Internal Logging Improvements**  
  Additional log statements have been added for error handling and block-based searches, making it easier to debug connectivity or timing issues.

- **Minor Fixes**
  - Adjusted the DexScreener polling interval to reduce timeouts.
  - Minor formatting updates in the volume detection messages.
  - Various code cleanups in watchers to improve clarity and maintainability.

## [0.3.3] - 03/28/2025

### VIVI's Radar Expansion

Now Clanker, Rainbow, and KOA deployers, plus DexScreener profiles updates from tokens from Safe Deployers, with a modular design for adding future deployers integrations.

- **Add Rainbow**  
  Now listens for Rainbow `Deploy Token`, retrieves new tokens, tracks volume, and notifies on threshold (0.05 ETH Volume).

- **Add KOA**  
  Now listens for KOA `Deploy Token`, retrieves new tokens, tracks volume, and notifies on threshold (0.05 ETH Volume).

- **Update for BANKR's new thread Fee policy**  
  When a token is deployed from a reply, `Creator Address` now reflects the wallet of the person who deployed — not the thread author.

- **Safe DexScreener Alerts**  
  Now alerting on DexScreener profile updates only from safe deployers: Clanker, Rainbow, and KOA.

## [0.3.2] - 03/27/2025

### Bot Command Registration

- **Private Bot Menu**  
   Now refreshed with a cleaner UI.
  Help and feedback buttons are accessible via slash commands in the Telegram menu for easier access.

- **Private Bot Commands**  
  Users can now see a full list of commands – `/buy`, `/sell`, `/wallets`, `/settings`, etc. – directly in their Telegram menu without needing to type them out.

- **Group Bot `/help` Command**  
  New `/help@VIVIBaseBot` command is available in group chats, directing users to comprehensive documentation that explains how to use group handlers and commands.

## [0.3.1] - 03/26/2025

### Group Bot Updates

- **Multiple Recipients in `/send`**  
  The `/send` command now supports sending tokens or ETH to multiple Telegram users (registered or not) or Ethereum addresses in a single command.
- **Send to Any Telegram User**  
  When sending to unregistered Telegram users, the bot automatically creates a wallet for them. They can later access their new funds privately via **@VIVIBaseBot**.
- **Improved Command/Message Handling**  
  The group command system has been streamlined for reliability and clearer bot responses.

```
@BotUsername buy <amountInETH> <token|address> [slippage]
» Buys the specified token from within the group chat.

@BotUsername sell <percent|half|all> <token|address> [slippage]
» Sells the specified percentage (or half/all) of your token holdings.

@BotUsername send <amount|half|all> <token|eth> <@username|0xAddress> [...multiple recipients]
» Transfers tokens or ETH (when token=eth) to one or more recipients.

@BotUsername burn <amount|half|all> <token|address>
» Burns (destroys) the specified amount of tokens.

@BotUsername balance
» Displays your current wallet balance (ETH and tokens) for the active wallet.

@BotUsername invite
» Generates a registration link with a referral code for new users.
```

### Private Bot Updates

- **Enhanced Feedback Scene**  
  The feedback feature now supports multiple images and extended user messages for more detailed submissions.
- **Register Presale Wallet**  
  A new scene allows registering an external wallet for whitelisting in the VIVI Token presale via DAOS.WORLD.
- **Add Me to Group Button**  
  The bot now provides a button to be added to groups. It requires minimal admin permissions for reading and responding to user messages.
- **Buy Token on the Fly**  
  You can jump to the Buy scene by pasting a valid contract address anywhere in the bot (except when the bot is specifically waiting for a different input).
- **Holdings Scene & Token Import**  
  Users can manually add tokens they’ve received externally to their VIVI wallet.
- **Buy & Sell Scene Improvements**  
  Redesigned menus, enhanced messaging, and clearer handling of amounts, slippage, and transaction confirmations.

### VIVI-Radar

- **Bot Migration**  
  Tactical VIVI has moved to a new bot: [VIVIRadar](https://t.me/VIVIRadar).
- **Removed DexScreener Profile Alerts**  
  To avoid notifying about potential rugs or scams, DexScreener profile alerts have been dropped.
- **New “Clanker” Deploy Notifications**  
  The bot now detects tokens deployed via _Clanker_, distinguishing them from _Bankr_ deploys.
- **Minimum Volume Filtering**  
  A minimum volume filter is applied two minutes after detecting a new token deploy, ensuring higher-quality alerts.

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
