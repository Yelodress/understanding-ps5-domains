| Studied firmware | PSN Access               |
| ---------------- | ------------------------ |
| 14.00            | None (outdated firmware) |

A few days ago, I asked for help to find a way to still download games on a PS5 while blocking updates through DNS. This post can be found [right here](https://www.reddit.com/r/PS5_Jailbreak/comments/1x2c70q/blocking_fw_update_while_still_download_games/), and it turns out this might be impossible.

During my research, I realized that the Sony domains the console connects to are poorly documented. So I decided to start documenting them, in my own small way.

### Firmware updates
In the following FQDNs, replace "XX" with your region code (au, br, cn, eu, hk, jp, kr, mx, ru, sa, tw, uk, us):

| FQDN                             | Note                                                                                                        |
| -------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| fXX01.ps5.update.playstation.net | XML file that specifies the latest firmware version, URL of the PUP and minimum firmware required per game. |
| dXX01.ps5.update.playstation.net | Serves the firmware itself (the PUP file)                                                                   |
| hXX01.ps5.update.playstation.net | Hosts the "About this update" page (details on the update's contents)                                       |
> Please note that blocking PS5 updates means you won't be able to install new games, access PSN or appear online. Games that are already installed will still receive updates (if you still have access to PSN).
### Feature updates (RNPS)
These domains have nothing to do with the firmware: they update console features (home screen, UI, etc.). Since these apps seem to be React Native apps, RNPS likely stands for "React Native PlayStation".
If you block a single feature’s domain (trophies, for instance), the console keeps working, but the feature update seems to be all-or-nothing: other modules, like the home screen, may stop receiving updates too _(unverified)_.
All descriptions below are unverified. With no documentation available, they're deduced from the names.

| FQDN                                                    | Note                                                                                                                                  |
| ------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| ppr-crl.rnps.dl.playstation.net                         | Likely related to the certificate revocation list (CRL)                                                                               |
| action-cards-host-app.rnps.dl.playstation.net           |                                                                                                                                       |
| agent-popupgui.rnps.dl.playstation.net                  | System pop-ups                                                                                                                        |
| bgft.rnps.dl.playstation.net                            | Probably related to background file transfers (bgft ?)                                                                                |
| broadcast.rnps.dl.playstation.net                       | Probably related to [PS5 broadcast](https://www.playstation.com/en-us/support/games/ps5-stream-gameplay-broadcast/) to Youtube/Twitch |
| capture-menu.rnps.dl.playstation.net                    | Likely related to the [game captures](https://www.playstation.com/en-us/support/games/ps5-game-captures-ps-app/) menu                 |
| codex.rnps.dl.playstation.net                           |                                                                                                                                       |
| compilation-disc-hub.rnps.dl.playstation.net            |                                                                                                                                       |
| control-center.rnps.dl.playstation.net                  | [Control center](https://www.playstation.com/en-us/support/games/customize-ps5-control-center/) updates                               |
| cosmiccube.rnps.dl.playstation.net                      |                                                                                                                                       |
| elysion.rnps.dl.playstation.net                         |                                                                                                                                       |
| explore-hub.rnps.dl.playstation.net                     | Likely related to the explore tab                                                                                                     |
| feature-discovery-device-dialog.rnps.dl.playstation.net |                                                                                                                                       |
| game-hub-preview-launcher.rnps.dl.playstation.net       |                                                                                                                                       |
| game-hub.rnps.dl.playstation.net                        |                                                                                                                                       |
| game-streaming-preview.rnps.dl.playstation.net          |                                                                                                                                       |
| gaming-lounge.rnps.dl.playstation.net                   |                                                                                                                                       |
| home.rnps.dl.playstation.net                            | Home menu updates                                                                                                                     |
| igc-browse.rnps.dl.playstation.net                      | Probably in-game content browsing                                                                                                     |
| invitation-dialog.rnps.dl.playstation.net               | Probably related to invitation dialog when you join a party with friends                                                              |
| legal-docs.rnps.dl.playstation.net                      | Legal docs                                                                                                                            |
| lfps-bc.rnps.dl.playstation.net                         |                                                                                                                                       |
| library.rnps.dl.playstation.net                         | Likely related to game library                                                                                                        |
| loyalty-hub.rnps.dl.playstation.net                     | Likely related to "[PlayStation Stars](https://www.playstation.com/en-hu/playstation-stars/)" program                                 |
| media-gallery.rnps.dl.playstation.net                   | Media gallery                                                                                                                         |
| millenniumfalcon-dialog.rnps.dl.playstation.net         |                                                                                                                                       |
| millenniumfalcon.rnps.dl.playstation.net                |                                                                                                                                       |
| monte-carlo.rnps.dl.playstation.net                     |                                                                                                                                       |
| notification-overlay.rnps.dl.playstation.net            | Notification overlay                                                                                                                  |
| onboard-download.rnps.dl.playstation.net                |                                                                                                                                       |
| player-selection-dialog.rnps.dl.playstation.net         |                                                                                                                                       |
| ppr-bgs.rnps.dl.playstation.net                         |                                                                                                                                       |
| profile-dialog.rnps.dl.playstation.net                  |                                                                                                                                       |
| profile.rnps.dl.playstation.net                         |                                                                                                                                       |
| ps5-multi-bundle-ota.rnps.dl.playstation.net            |                                                                                                                                       |
| psnow-player.rnps.dl.playstation.net                    | Likely related to the PSNow player (cloud gaming)                                                                                     |
| psw-firmware.rnps.dl.playstation.net                    | Likely related to wireless devices firmware (controller, headphones, etc.)                                                            |
| rnps-bgs-ml-app.rnps.dl.playstation.net                 |                                                                                                                                       |
| rnps-feature-discovery-archive.rnps.dl.playstation.net  |                                                                                                                                       |
| rnps-loginmgr-dialog.rnps.dl.playstation.net            | Login manager                                                                                                                         |
| rnps-media-settings.rnps.dl.playstation.net             | Media settings                                                                                                                        |
| rnps-ml-models.rnps.dl.playstation.net                  |                                                                                                                                       |
| rnps-peripherals-onboarding.rnps.dl.playstation.net     | Peripherals setup                                                                                                                     |
| screen-share.rnps.dl.playstation.net                    | Screen sharing feature                                                                                                                |
| search.rnps.dl.playstation.net                          | Search feature                                                                                                                        |
| service-hub-psplus.rnps.dl.playstation.net              | PS Plus hub                                                                                                                           |
| settings.rnps.dl.playstation.net                        | Settings                                                                                                                              |
| social-interaction.rnps.dl.playstation.net              | Social interactions                                                                                                                   |
| system-message-client.rnps.dl.playstation.net           | System messages                                                                                                                       |
| telemetry-schema-app.rnps.dl.playstation.net            | Related to telemetry schema                                                                                                           |
| titlestore-preview.rnps.dl.playstation.net              | PS Store preview                                                                                                                      |
| trophy.rnps.dl.playstation.net                          | Trophies related                                                                                                                      |
| tts-dictionary.rnps.dl.playstation.net                  | Text to speech dictionary                                                                                                             |
| uam-fs.rnps.dl.playstation.net                          | Likely related to User Account Management (UAM ?)                                                                                     |
| universal-checkout.rnps.dl.playstation.net              | Store payments                                                                                                                        |
| unsupported-title-hub.rnps.dl.playstation.net           | Related to the "Disc not supported" text                                                                                              |
| ut-service.rnps.dl.playstation.net                      |                                                                                                                                       |
| wishlist.rnps.dl.playstation.net                        | Wishlist system                                                                                                                       |
| x-wing.rnps.dl.playstation.net                          |                                                                                                                                       |
| service-hub-psnow.rnps.dl.playstation.net               |                                                                                                                                       |
| app-cloud-config-lambda.rnps.dl.playstation.net         |                                                                                                                                       |
| cart-lambda.rnps.dl.playstation.net                     |                                                                                                                                       |
| chimera-lambda.rnps.dl.playstation.net                  |                                                                                                                                       |
| cloud-config-lambda.rnps.dl.playstation.net             |                                                                                                                                       |
| exchange-lambda.rnps.dl.playstation.net                 |                                                                                                                                       |
| experience-lambda.rnps.dl.playstation.net               |                                                                                                                                       |
| feature-discovery-lambda.rnps.dl.playstation.net        |                                                                                                                                       |
| feedback-lambda.rnps.dl.playstation.net                 |                                                                                                                                       |
| game-hub-post-lambda.rnps.dl.playstation.net            |                                                                                                                                       |
| game-hub-pre-lambda.rnps.dl.playstation.net             |                                                                                                                                       |
| home-lambda.rnps.dl.playstation.net                     |                                                                                                                                       |
| igc-catalog-lambda.rnps.dl.playstation.net              |                                                                                                                                       |
| library-lambda.rnps.dl.playstation.net                  |                                                                                                                                       |
| monte-carlo-lambda.rnps.dl.playstation.net              |                                                                                                                                       |
| music-lambda.rnps.dl.playstation.net                    |                                                                                                                                       |
| search-lambda.rnps.dl.playstation.net                   |                                                                                                                                       |
| stories-lambda.rnps.dl.playstation.net                  |                                                                                                                                       |
| subscriptions-manager-lambda.rnps.dl.playstation.net    |                                                                                                                                       |
| uam-lambda.rnps.dl.playstation.net                      |                                                                                                                                       |
| wishlist-lambda.rnps.dl.playstation.net                 |                                                                                                                                       |
| univex-v1-lambda.rnps.dl.playstation.net                |                                                                                                                                       |
| users-lambda.rnps.dl.playstation.net                    |                                                                                                                                       |
### Game content
The following FQDNs are used to download game-related content (base games, DLC, patches, metadata, etc.).

| FQDN                               | Note                                                                                                                                                                                                                                                                                                      |
| ---------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| sgst.prod.dl.playstation.net       | Contains PS5 game patch metadata (XML & JSON files). It may also serve the second chunk of "PlayGo" compatible games and related CRC files. Blocking it most likely prevents the console from detecting new patches. Note: in my tests, a patch that was already queued kept downloading with it blocked. |
| gst.prod.dl.playstation.net        | PS5 game patch packages (\*.pkg file). According to PS Dev Wiki, this domain may contain the first chunk of "PlayGo" compatible games. In my tests, the full Ghost of Yōtei update was downloaded from this domain                                                                                        |
| gs-sec.ww.np.dl.playstation.net    | Contains PS4 game link to the Delta Package if it exists, the PlayGo Manifest XML and the JSON                                                                                                                                                                                                            |
| gs2.ww.prod.dl.playstation.net     | Contains PS4 game update change information, PlayGo manifest, base game and game update PKG file                                                                                                                                                                                                          |
| gs2-sec.ww.prod.dl.playstation.net | Game base descriptive files (icon, pronunciation, background image and background music)                                                                                                                                                                                                                  |
| tmdb.np.dl.playstation.net         | Title metadata database JSON (confirmed for PS4 games only; possibly used for PS5 games too).                                                                                                                                                                                                             |
### Websites
Your PlayStation has a built-in web browser to display web content.

| FQDN                   | Note                       |
| ---------------------- | -------------------------- |
| www.playstation.com    | Official website           |
| static.playstation.com | Website assets             |
| gmedia.playstation.com | Likely the website's media |

### Telemetry
These domains are used to send telemetry to PlayStation servers. 
Even on outdated firmware with no PSN access, your console still sends telemetry.
Please note that `telemetry-schema-app.rnps.dl.playstation.net` might be related to telemetry too. Based on its name, it likely serves the telemetry schema, which the console requests at boot.

| FQDN                                  | Note                                                                     |
| ------------------------------------- | ------------------------------------------------------------------------ |
| smetrics.aem.playstation.com          | According to some users, this domain could be used by the trophy system. |
| telemetry-console.api.playstation.com | Probably syncs information about playtime and games played               |
| telemetry-web.api.playstation.com     | Might be used to track how you use the web browser                       |
### NP domains

| FQDN                                         | Note               |
| -------------------------------------------- | ------------------ |
| bclog.np.rds.s0.playstation.net              |                    |
| ecode.np.cs.playstation.net                  |                    |
| web.np.playstation.com                       |                    |
| envelope2.np.dl.playstation.net              |                    |
| ps5.np.playstation.net                       |                    |
| ps5cel.np.dl.playstation.net                 |                    |
| uef.np.dl.playstation.net                    |                    |
| gs-sec.ww.np.dl.playstation.net              | See "Game content" |
| ps4-system.sec.np.dl.playstation.net         |                    |
| static-resource.np.community.playstation.net |                    |
| us.np.stun.playstation.net                   |                    |
| asm.np.community.playstation.net             |                    |
### Uncategorized domains

| FQDN                                            | Note                                                                     |
| ----------------------------------------------- | ------------------------------------------------------------------------ |
| ena.net.playstation.net                         | Internet connection status test (guessed from the User-Agent: "SceIcst") |
| cfss.crs.playstation.net                        |                                                                          |
| feature-discovery-assets-amd.dl.playstation.net |                                                                          |
| feature.api.playstation.com                     |                                                                          |
| image.api.playstation.com                       |                                                                          |
| psn-rsc.prod.dl.playstation.net                 |                                                                          |
| psnobj.prod.dl.playstation.net                  |                                                                          |
| qgve.dl.playstation.net                         |                                                                          |
| urlconfig.api.playstation.com                   |                                                                          |
| vulcan.dl.playstation.net                       |                                                                          |
