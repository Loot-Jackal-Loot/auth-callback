# auth-callback

Login page of **LOOT JACKAL LOOT!**, published with GitHub Pages at <https://loot-jackal-loot.github.io/auth-callback/>.

When a player signs in with Google or Discord from the game, Supabase redirects the browser here at the end of the login. The page sends the tokens to the `store-auth-tokens` Edge Function, which keeps them for a few minutes under the game's polling code, and the game picks them up from there. The page then tells the player whether the login worked and that they can go back to the game.

## Files

- `index.html`: the page. It reads `access_token` and `refresh_token` from the URL fragment and `polling_state` from the query string, and shows a failure if any of them is missing or if the Edge Function rejects them. The shared style (fonts, colors, background, panels) comes from `/assets/site.css` in the [loot-jackal-loot.github.io](https://github.com/Loot-Jackal-Loot/loot-jackal-loot.github.io) repository.
