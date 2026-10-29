# Direct online play

Card Vault's online mode uses the browser's built-in WebRTC data channel. It does not use a hosted game server, Supabase, or external STUN/TURN services. Each player uses their local collection and their own 10–30-card deck.

## Connect two players

1. Both players open the same game file and build a deck containing 10–30 cards.
2. The first player opens **Online**, enters a display name, and selects **Create offer**.
3. They copy the offer code and send it privately to the second player.
4. The second player pastes the offer code into **Join a connection**, enters a name, and selects **Create answer**.
5. They copy the answer code and send it back.
6. The first player pastes that code into **Opponent's answer code** and selects **Connect to opponent**. The direct connection starts the match when both decks are synchronized.

Connection codes contain network connection details; share them only with the intended opponent. No signaling service is involved: players exchange these codes out of band (for example, by message).

## Network limitations

Because this is fully server-free and uses no external network helpers, direct connections work only when the peers can reach each other using their network addresses. It is most reliable on the same local network. NAT, router, carrier, or firewall restrictions may prevent players on different internet connections from connecting. A reliable connection across arbitrary networks requires a public signaling path and often STUN/TURN infrastructure; that cannot be supplied by a local HTML file alone.

Matches are peer-hosted and intended for casual play. Either player can inspect or modify local game state, so this mode is not cheat-resistant.
