# Changelog

## [0.5.4] - 05/31/2025

### Virtual Protocol Token Support

- **Virtual Token Integration**: Buy and sell scenes now support tokens launched via Virtual Protocol's launchpad platform.

  - Automatic detection of Virtual Protocol-deployed tokens with native liquidity pools
  - Seamless trading using multi-hop routing: ETH → VIRTUAL → TOKEN for purchases
  - Reverse path TOKEN → VIRTUAL → ETH for sales
  - Optimized quote comparison across all available DEXs including Virtual Protocol pools
  - Fallback to standard DEX routing if Virtual pools unavailable or non-optimal

- **Group/Private Commands**: All existing trading commands now work with Virtual Protocol tokens.

  ```
  @VIVIBaseBot buy 0.1 <virtual_token_address>
  @VIVIBaseBot sell 50% <virtual_token_address>
  ```

## [0.5.3] - 05/30/2025

### MultiSend Feature

- **Multi-Recipient Token Transfers**: Enhanced the existing send functionality to support sending tokens or ETH to multiple recipients simultaneously.

  - Batch Processing: Execute up to 30 transfers in a single command for improved efficiency
  - Smart Validation: Pre-flight checks ensure sufficient balance for all transfers before processing
  - Enhanced Command Syntax: Improved parsing for multi-recipient commands across all interfaces.

  ```
  # Send to multiple recipients at once
  send 0.01 ETH @alice @bob 0x742d35Cc6634C0532925a3b8D214C3D2F9D1f8 vivi.base.eth

  # Group chat multi-send
  @VIVIBaseBot send 50 USDC @user1 @user2 satoshi.base.eth
  ```

- **Optimized Batch Transactions**: Improved gas estimation and transaction queuing for multi-recipient operations
- **Enhanced Error Recovery**: Better handling of partial failures in batch operations with detailed error reporting

## [0.5.2] - 05/29/2025

### ApeStore Integration

- **ApeStore Token Support**: Buy and sell scenes now support tokens launched via ApeStore platform.

  - Automatic detection of ApeStore prebo
  - Seamless trading integration with ApeStore's pre graduated token ecosystem
  - Optimized routing for ApeStore tokens across all supported DEXs
  - Enhanced token metadata retrieval from ApeStore API

- **Group/Private Commands**: All existing trading commands now work with ApeStore tokens.
  Once ApeStore Token is graduated the bot will use uniswap v2 or v3 pools.

  ```
  @VIVIBaseBot buy 0.1 <apestore_token_address>
  @VIVIBaseBot sell 50% <apestore_token_address>
  ```

- **Enhanced Pool Discovery**: Improved pool discovery system across all supported DEXs for faster and more stable trading.
  - Optimized pool detection algorithms for better performance
  - Enhanced stability in multi-DEX routing and quote comparison
  - Faster response times when discovering liquidity across different platforms

## [0.5.1] - 05/27/2025

### Zora Token Swap Support

- **Zora Token Integration**: Buy and sell scenes now support tokens launched via Zora's social network platform.

  - Automatic detection of Zora-deployed tokens with native liquidity pools
  - Seamless trading using multi-hop routing: ETH → USDC → ZORA → TOKEN for purchases
  - Reverse path TOKEN → ZORA → USDC → ETH for sales
  - Optimized quote comparison across all available dexes.
  - Fallback to standard DEX routing if Zora pools unavailable or a better non-ZORA/TOKEN pool is available

- **Group/Private Commands**: All existing group trading commands now work with Zora tokens.

  ```
  @VIVIBaseBot buy 0.1 <zora_token_address>
  @VIVIBaseBot sell 50% <zora_token_address>
  ```

## [0.5.0] - 05/22/2025

### UI/UX & Market Cap Improvements

- **Enhanced Market Cap Calculations**: Improved accuracy and reliability of market cap calculations in both buy and sell scenes.

  - Real-time data refresh for more accurate market information
  - Better handling of low-liquidity tokens with small market caps

- **PNL Display Enhancements**: Refined token and ETH displays in the PNL tracking system.

  - Clearer formatting for large numbers with appropriate separators
  - Consistent decimal precision across all token displays

- **Multi-Wallet Balance Fix**: Resolved an issue where only the public wallet balance was displayed in the main menu after completing a buy or sell operation.
  - Main menu now correctly shows aggregated balances from all wallets after any transaction
  - Fixed refresh mechanism to properly update all connected wallet balances

### Command System Restructuring

- **Separated Inline Commands**: Completely restructured the inline command handling system for both group chats and direct messages.
  - Distinct command paths for `buy`, `sell`, and `send` operations
  - Improved parsing for complex command structures
  - Better error handling with specific error messages for each command type
  - Reduced command conflicts and interference between similar operations
  - Enhanced support for command chaining in complex scenarios

## [0.4.9] - 05/21/2025

### Update Token Transfers

- **Multi-Recipient Transfers**: Send tokens or ETH to multiple recipients in a single command:
  ```
  send 0.01 ETH/TOKEN @user1 @user2 0xAddress vivi.base.eth
  ```
- **Improved Transfer Experience**:

  - Confirmation step before processing multiple transfers
  - Real-time progress tracking during multi-recipient transactions
  - Automatic validation of all recipients before starting transfers
  - Transfer summary showing successful and failed transactions

- **Improved Balance Verification**:

  - Balance Validation for full TX
  - Error messages when insufficient balance with exact shortage

- **Enhanced Recipient Handling**:

  - Support for Telegram usernames, Ethereum addresses, and BNS names in one command
  - Invalid recipients with detailed error
  - Maximum 15 recipients per transfer command to ensure reliability

- **Streamlined User Interface**:
  - Clear confirmation screens showing all recipients before proceeding
  - Progress indicators for tracking multi-recipient transfers in real-time
  - End-of-transfer summary with success/failure counts
  - "Let 'Em Know" button to notify recipients of successful TX via Telegram

## [0.4.8] - 05/18/2025

### PNL Tracking System (MVP)

- **Detailed PNL Calculations**: New PNL (Profit and Loss) tracking system provides detailed calculations across all your holdings.

  - Track unrealized profits, realized profits, and total returns for each token
  - View performance metrics with intuitive visual indicators (🚀, 🔥, 📈, ⚖️, 📉, 💩)
  - Results automatically include all transactions from all your wallets

- **Multi-Wallet PNL Integration**: PNL calculations now aggregate data from all your wallets for complete portfolio insights.

  - See total cost basis and current value across all wallets
  - Track percentage returns for each token regardless of which wallet made the trades
  - Instantly view which wallets contain specific tokens with per-wallet balance breakdown

- **PNL Command**: New `pnl` command shows detailed profit/loss information.
  - Use `pnl` to see overall performance summary for all tokens
  - Use `pnl <symbol>` to deep-dive into specific token performance
  - Command shows balance, current worth, cost basis, unrealized/realized profits, and return percentage

### Enhanced Trading Scenes

- **Buy Scene with PNL Data**: Buy scene now shows real-time PNL information about tokens you already hold.

  - Make informed decisions with current profit/loss data while purchasing
  - See wallet-by-wallet breakdown of holdings and ETH balances
  - Instantly understand how your new purchase will affect your average cost

- **Sell Scene with PNL Data**: Sell scene now includes detailed PNL metrics.
  - View current profit/loss before selling
  - See how different sell percentages affect your potential realized profits
  - Get wallet-specific balance information to optimize selling strategy

### Holdings/Positions Scene Improvements

- **Enhanced Token Detail View**: Get comprehensive PNL breakdown for any token in your portfolio.

  - One-tap access to token performance metrics from the portfolio view
  - See full performance history including cost basis, current value, and percentage returns
  - View wallet distribution with precise balance information for each wallet

- **Wallet-Specific Views**: Enhanced wallet detail pages show PNL performance for each wallet.

  - Filter and view PNL by individual wallet
  - Compare performance across different wallets
  - See which wallets are providing the best returns for specific tokens

- **Import Token Enhancements**: Choose which wallet to import tokens to with a simple selection interface.
  - User-friendly wallet selection screen during token import
  - Clear confirmation of which wallet received the imported token
  - Automatic PNL tracking begins immediately after import

The new PNL system is designed to give traders complete transparency into their portfolio performance, helping make more informed trading decisions with comprehensive, cross-wallet profitability insights.

## [0.4.7] - 05/08/2025

### WALLET MANAGEMENT - Remove Wallet

- **Remove Wallet Feature**: Users can now remove unused wallets from their account through the Wallet Management interface.
  - Access via the new "🗑️ Remove Wallet" button in the Wallets menu
  - Clear warnings about permanent loss of access to funds if private key not backed up
  - Safety protections prevent removing the currently selected wallet
  - At least one wallet must remain in the account at all times

## [0.4.6] - 05/08/2025

### Enhanced RPC Infrastructure

- **Transaction/Call Separation**: Split architecture to process transactions and read-only calls separately, improving overall performance.
- **Load Balancing**: Added multi-node support to handle increased traffic during peak periods.
- **Connection Optimization**: Implemented connection pooling for faster response times.

## [0.4.5] - 05/05/2025

### Multi-Wallet Trading: Buy Scene

- **Multi-Wallet Swaps**: Perform buy operations using multiple wallets directly within the scene.
- **Gas Priority Selection**: Adjust gas priority (0.1 / 1 / 5 gwei) seamlessly during the buy process.
- **Real-time Wallet Balances**: Updated ETH balances instantly reflect purchases across all active wallets.

### Multi-Wallet Trading: Sell Scene

- **Multi-Wallet Swaps**: Execute sell operations from multiple wallets within a single scene interaction.
- **Gas Priority Selection**: Specify desired gas priority (0.1 / 1 / 5 gwei) directly in the sell scene.
- **Instant Wallet Updates**: ETH and token balances automatically refresh upon transaction completion, accurately reflecting updated holdings.

### Multi-Wallet Trading: Main Menu

- **Aggregated Wallet Balances**: View combined ETH and token balances from all your wallets directly in the Main Menu.
- **Enhanced Refresh Button**: The refresh button now updates ETH and token balances simultaneously across all wallets, ensuring consistent and accurate balance information.

## [0.4.4] - 05/02/2025

### Send tokens to any @tguser via VIVI's DM + notify recipient

We've introduced intuitive text-based commands that work without the need for command prefixes:

- **`buy <amount> <token>`** - Quickly buy tokens with a specified amount of ETH
- **`sell <percent|half|all> <token>`** - Easily sell tokens with specific percentage
- **`send <amount> <token> <recipient1> [<recipient2> ...]`** - Send tokens to one or multiple recipients at once
- **`transfer <amount> <token> <recipient1> [<recipient2> ...]`** - Alternative to the send command
- **`balance [@tgUsername]`** - Check your balance or another user's balance
- **`burn <amount|all|half> <token>`** - Burn tokens permanently

### Send Tx Sharing

- Improved confirmation flow with inline buttons
- Added "Let 'Em Know" button after successful transfers to easily notify recipients
- Share transaction details with recipients via Telegram's native sharing

## [0.4.3] - 04/28/2025

### Gas Estimation Improvements

- Smarter gas calculation for taxed tokens and internal transactions
- Dynamic adjustment based on swap type for better cost efficiency
- Automatic transaction size detection to fine-tune gas limits

## [0.4.2] - 04/25/2025

### Group Commands - Base Names (BNS) Integration

- **Send/Transfer to BNS Names**: Users can now send tokens and ETH directly to Base Names (.base.eth) in group chats

  ```
  @VIVIBaseBot send 0.1 ETH vivi.base.eth
  @VIVIBaseBot transfer 50 USDC satoshi.base.eth
  ```

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
