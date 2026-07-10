#----------------------------------------#

#YouTube: filter out upcoming videos and streams
www.youtube.com##ytd-browse ytd-grid-video-renderer:has(ytd-thumbnail-overlay-time-status-renderer[overlay-style="UPCOMING"])
www.youtube.com##ytd-browse ytd-rich-item-renderer:has(ytd-thumbnail-overlay-time-status-renderer[overlay-style="UPCOMING"])
www.youtube.com##ytd-browse[page-subtype="subscriptions"] ytd-video-renderer ytd-thumbnail-overlay-time-status-renderer[overlay-style="UPCOMING"]:upward(ytd-item-section-renderer)
youtube.com##ytd-rich-grid-row, #contents.ytd-rich-grid-row:style(display:contents !important;)

! Netflix - Hide Games
www.netflix.com##.billboard-row-games

||ads.twitch.tv^
www.twitch.tv###directory-banner
www.twitch.tv###directory-rectangle
www.twitch.tv##.channel-info-content > div > div > .kbdfeJ.Layout-sc-1xcs6mc-0
www.twitch.tv##.tw-root--theme-light.hoAkTp.inWwYB.ScLayoutCssVars-sc-10awzi2-1.Layout-sc-1xcs6mc-0
twitch.tv##.gMJXeQ.Layout-sc-1xcs6mc-0 > .dZwwnJ.Layout-sc-1xcs6mc-0

!YouTube Annoyances (recommendations)
youtube.com##.section-list > li:has(.shelf-title-cell > a[href="/feed/recommended"])
www.youtube.com##.ytp-ce-element-show
youtube.com##.ytd-shelf-renderer
youtube.com##.ytd-watch-next-secondary-results-renderer

#----------------------------------------#

! Title: Hide YouTube Shorts
! Description: Hide all traces of YouTube shorts videos on YouTube
! Version: 2026.4.29
! Last modified: 2026-04-29 19:49
! Expires: 2 weeks (update frequency)
! Homepage: https://github.com/gijsdev/ublock-hide-yt-shorts
! License: https://github.com/gijsdev/ublock-hide-yt-shorts/blob/master/LICENSE.md

! Hide all videos with the shorts indicator
www.youtube.com##ytd-thumbnail-overlay-time-status-renderer[overlay-style="SHORTS"]:upward(ytd-video-renderer)

! Remove generic shorts shelf except on history page
www.youtube.com##:matches-path(/^(?!\/feed\/history).*$/)ytd-reel-shelf-renderer

! Remove rich shelf shorts section
www.youtube.com##ytd-rich-shelf-renderer[is-shorts],ytd-rich-shelf-renderer[is-shorts]:upward(ytd-rich-section-renderer)
www.youtube.com##ytd-rich-item-renderer[rendered-from-rich-grid] ytm-shorts-lockup-view-model:upward(ytd-rich-item-renderer[rendered-from-rich-grid])

! Hide shorts button in sidebar
www.youtube.com##ytd-guide-entry-renderer:has(.ytd-guide-entry-renderer[title="Shorts"])
! Tablet resolution
www.youtube.com##ytd-mini-guide-entry-renderer:has(.ytd-mini-guide-entry-renderer[title="Shorts"])

! Hide shorts tab on channel pages
www.youtube.com##yt-tab-shape[tab-title="Shorts"]

! Hide shorts filter/category on top of homepage and search pages
www.youtube.com##yt-chip-cloud-chip-renderer:has(.ytChipShapeInactive:has-text(/^Shorts$/i))

! Hide shorts sections on search page
www.youtube.com##ytm-shorts-lockup-view-model-v2:upward(grid-shelf-view-model)

!!! MOBILE !!!

! Hide all videos with the shorts indicator
!m.youtube.com##ytm-thumbnail-overlay-time-status-renderer[data-style="SHORTS"]:upward(ytm-video-with-context-renderer)

! Remove generic shorts shelf except on history page
!m.youtube.com##:matches-path(/^(?!\/feed\/history).*$/)ytm-reel-shelf-renderer

! Hide shorts button in the bottom navigation bar
!m.youtube.com##ytm-pivot-bar-item-renderer:has(.pivot-shorts)

! Hide shorts sections except on history page
!m.youtube.com##:matches-path(/^(?!\/feed\/history).*$/)ytm-shorts-lockup-view-model:upward(ytm-rich-section-renderer)

! Hide shorts tab on channel pages
!m.youtube.com##yt-tab-shape[tab-title="Shorts"]

! Hide shorts filter/category on top of homepage and search pages
!www.youtube.com##ytm-chip-cloud-chip-renderer:has([aria-label="Shorts"])

! Hide shorts sections on search page
!m.youtube.com##ytm-shorts-lockup-view-model:upward(grid-shelf-view-model)

#----------------------------------------#

! YT Home - Hide videos based on channel URLs
!youtube.com##ytd-browse[page-subtype="home"] ytd-rich-item-renderer:has([href="/channel/channel1-ID-here"],[href="@/Channel2NameHere"])
! YT Home - Hide videos based on their titles
!youtube.com##ytd-browse[page-subtype="home"] ytd-rich-item-renderer:has(:is(#video-title-link,h3):is([title*="Partial Match"], [title*="Case-Insensitive Partial Match"i], [title~="Space-separated-aka-Whole-word-match"]))
! YT Sidebar - Hide videos based on their titles
!youtube.com###related :is(ytd-compact-video-renderer,yt-lockup-view-model):has(:is(#video-title,h3):is([title*="Partial Match"], [title*="Case-Insensitive Partial Match"i], [title~="Space-separated-aka-Whole-word-match"]))
! YT - Sidebar - Hide videos based on channel names (procedural)
!www.youtube.com###related :is(ytd-compact-video-renderer,yt-lockup-view-model) .yt-content-metadata-view-model__metadata-row:first-child>span:has-text(/^(Channel Name 1|Channel Name 2)$/):upward(ytd-compact-video-renderer,yt-lockup-view-model)
! YT Home - No Videos
www.youtube.com##ytd-browse[page-subtype="home"]
! YT Videos - No Sidebar
www.youtube.com##ytd-watch-flexy #secondary
! YT Videos - Sidebar Without Recommendations
www.youtube.com##ytd-watch-flexy #secondary
! YT Homepage - Hide the Posts Section
www.youtube.com##ytd-browse[page-subtype="home"] ytd-rich-section-renderer:has(ytd-rich-item-renderer[is-post])
! YT Homepage - Hide Posts
www.youtube.com##ytd-browse[page-subtype="home"] ytd-rich-item-renderer[is-post]
! YT - Below the Player Buttons - Join
www.youtube.com###top-row.ytd-watch-metadata #sponsor-button
! YT - Below the Player Buttons - Ask
www.youtube.com###top-row.ytd-watch-metadata yt-button-view-model:has([aria-label="Ask"])
! YT - Below the Player Buttons - Thanks
www.youtube.com###top-row.ytd-watch-metadata yt-button-view-model:has([aria-label="Thanks"])
! YT - Below the Player Buttons - More
www.youtube.com###top-row.ytd-watch-metadata [aria-label="More actions"]
! YT - Below the Player Buttons - More: Ask
www.youtube.com##ytd-menu-service-item-renderer:has([d^="M480-80q0-83-31.5-156T363-363q-54-54-127-85.5T80-480q83"])
! YT - Below the Player Buttons - More: Thanks
www.youtube.com##ytd-menu-service-item-renderer:has([d^="M16.25 2A6.7 6.7 0 0012 3.509 6.75 6.75"])
! Hide 1080p Premium
youtube.com##.ytp-quality-menu .ytp-menuitem:has(.ytp-premium-label)
! Hide 'Join Now'
youtube.com##ytd-popup-container > tp-yt-paper-dialog > ytd-mealbar-promo-renderer, ytd-popup-container > tp-yt-paper-dialog > yt-mealbar-promo-renderer:has-text(/Claim Offer|Join now|Not Now|No thanks|YouTube TV|live TV|Live TV|movies|sports|Try it free|unlimited DVR|watch NFL/)

#----------------------------------------#

! YT Search - keep only videos (no shorts), channels and playlists
youtube.com##ytd-search ytd-item-section-renderer>#contents>:is(:not(ytd-video-renderer,ytd-channel-renderer,ytd-playlist-renderer,yt-lockup-view-model,yt-showing-results-for-renderer,[icon-name="promo-full-height:EMPTY_SEARCH"]),ytd-video-renderer:has([aria-label="Shorts"])),ytd-secondary-search-container-renderer

! Move homepage placeholders to the end
www.youtube.com##ytd-browse[page-subtype="home"] :is(ytd-rich-grid-row, #contents.ytd-rich-grid-row):style(display: contents !important)

! Fixes grid alignment
www.youtube.com##ytd-rich-item-renderer[rendered-from-rich-grid][is-in-first-column]:style(margin-left: calc(var(--ytd-rich-grid-item-margin)/2) !important)
www.youtube.com##ytd-rich-grid-renderer>#contents:style(margin-left: calc(var(--ytd-rich-grid-gutter-margin)) !important)
www.youtube.com###content.ytd-rich-section-renderer:style(margin-left: calc(var(--ytd-rich-grid-item-margin)/2) !important; margin-right: calc(var(--ytd-rich-grid-item-margin)*2.5) !important;)

#----------------------------------------#

! Remove Auto-Dub
youtube.com##+js(json-edit, ..adaptiveFormats.*[?.audioTrack.isAutoDubbed])
youtube.com##+js(json-edit-xhr-response, ..adaptiveFormats.*[?.audioTrack.isAutoDubbed], propsToMatch, /youtubei)
youtube.com##+js(json-edit-fetch-response, ..adaptiveFormats.*[?.audioTrack.isAutoDubbed], propsToMatch, /youtubei)
youtube.com##+js(script, (function serverContract(), if("object"===typeof window.ytInitialPlayerResponse){window.ytInitialPlayerResponse=JSON.parse(JSON.stringify(window.ytInitialPlayerResponse));}(function serverContract(), sedCount, 1)

#----------------------------------------#

! WhatsApp
web.whatsapp.com###expressions-panel-container+span:not(:empty)>[role="application"]>ul>div>div>div:has([data-icon="thumbs-down-refreshed"],[data-icon="block-refreshed"],[data-icon="clear-refreshed"],[data-icon="delete"])
web.whatsapp.com##[aria-label="Report"], [aria-label="Block"], [aria-label="Clear chat"], [aria-label="Delete chat"]

#----------------------------------------#

#YouTube: filter out Shorts
www.youtube.com##ytd-guide-renderer a.yt-simple-endpoint path[d^="M10 14.65v-5.3L15 12l-5 2.65zm7.77-4.33"]:upward(ytd-guide-entry-renderer)
www.youtube.com##ytd-mini-guide-renderer a.yt-simple-endpoint path[d^="M10 14.65v-5.3L15 12l-5 2.65zm7.77-4.33"]:upward(ytd-mini-guide-entry-renderer)
www.youtube.com##ytd-browse[page-subtype="home"] .ytd-thumbnail[href^="/shorts/"]:upward(ytd-rich-item-renderer)
www.youtube.com##ytd-browse[page-subtype="subscriptions"] .ytd-thumbnail[href^="/shorts/"]:upward(ytd-grid-video-renderer,ytd-rich-item-renderer)
www.youtube.com##ytd-browse[page-subtype="subscriptions"] ytd-video-renderer .ytd-thumbnail[href^="/shorts/"]:upward(ytd-item-section-renderer)
www.youtube.com##ytd-watch-next-secondary-results-renderer .ytd-thumbnail[href^="/shorts/"]:upward(ytd-compact-video-renderer,ytd-shelf-renderer)
www.youtube.com##ytd-browse[page-subtype="trending"] .ytd-thumbnail[href^="/shorts/"]:upward(ytd-video-renderer)
www.youtube.com##ytd-search .ytd-thumbnail[href^="/shorts/"]:upward(ytd-video-renderer)
www.youtube.com##ytd-notification-renderer:has(> a[href^="/shorts/"])
www.youtube.com##ytd-rich-shelf-renderer[is-shorts]
www.youtube.com##ytd-rich-shelf-renderer[is-shorts].ytd-rich-section-renderer:upward(ytd-rich-section-renderer)
www.youtube.com##ytd-reel-shelf-renderer

#----------------------------------------#

! ============================
! YouTube Top Nav Bar
! ============================

! always show normal YouTube logo, never that distracting doodleyoodle
www.youtube.com##ytd-topbar-logo-renderer > a > ytd-yoodle-renderer
www.youtube.com##ytd-topbar-logo-renderer > a > div:remove-attr(hidden)

! hide "Search with your voice" button
www.youtube.com###masthead #center #voice-search-button

! hide "+Create" button
www.youtube.com###masthead #end #buttons > ytd-button-renderer

! fix height issue with top navigation bar + remove frosted glass background effect
www.youtube.com#$##frosted-glass.with-chipbar.ytd-app {background: var(--yt-spec-base-background)!important;height: var(--ytd-toolbar-height)!important;}
www.youtube.com#$#ytd-feed-filter-chip-bar-renderer[frosted-glass-mode=with-chipbar] #chips-wrapper.ytd-feed-filter-chip-bar-renderer, ytd-masthead[frosted-glass-mode=without-chipbar] #background.ytd-masthead {background: var(--yt-spec-base-background)!important;}

! ============================
! YouTube Left Main Menu
! ============================

! hide "Shorts" menu item
www.youtube.com##ytd-guide-renderer ytd-guide-entry-renderer:has(a[title="Shorts"]), ytd-mini-guide-entry-renderer[aria-label="Shorts"]

! hide "Explore" menu section
www.youtube.com##ytd-guide-section-renderer:has(#guide-section-title:has-text(/Explore/))

! hide "More from YouTube" menu section
www.youtube.com##ytd-guide-section-renderer:has(#guide-section-title:has-text(/More from YouTube/))

! ============================
! YouTube Home Page
! ============================

! hide disruptive sections like "Shorts" or "Top News" on Home Page
www.youtube.com##[page-subtype="home"] ytd-rich-section-renderer:has(#dismissible)

! hide "How is this recommendation?" tooltip below videos on Home Page
www.youtube.com##[page-subtype="home"] ytd-rich-item-renderer #attached-survey

! hide videos I already watched in full (>=70%) on Home Page
www.youtube.com##[page-subtype="home"] ytd-rich-item-renderer:has(:is(#progress, yt-lockup-view-model .ytThumbnailOverlayProgressBarHostWatchedProgressBarSegment):matches-attr(style="/width: ([789][0-9]|100)%/"))

! hide old videos (1 year and older) on Home Page
www.youtube.com##[page-subtype="home"] ytd-rich-item-renderer:has(:is(.inline-metadata-item.ytd-video-meta-block, yt-lockup-view-model yt-content-metadata-view-model span):has-text(/ years? ago$/))

! hide videos with less than 2000 views on Home Page
www.youtube.com##[page-subtype="home"] ytd-rich-item-renderer:has(:is(.inline-metadata-item.ytd-video-meta-block, yt-lockup-view-model yt-content-metadata-view-model span):has-text(/^(\d{1,3} |No |1(\.\d)?K )views?$/))

! hide mixes on Home Page
www.youtube.com##[page-subtype="home"] ytd-rich-item-renderer:has(yt-collections-stack:has-text(/[\w\W]{1}/))

! hide small live streams (under 100 watching) on Home Page
www.youtube.com##[page-subtype="home"] ytd-rich-item-renderer:has(:is(.inline-metadata-item.ytd-video-meta-block, yt-lockup-view-model yt-content-metadata-view-model span):has-text(/^\d{1,2} watching?$/))

! hide all recorded live streams turned into videos ("Streamed 8 hours ago" etc.) on Home Page
www.youtube.com##[page-subtype="home"] ytd-rich-item-renderer:has(:is(.inline-metadata-item.ytd-video-meta-block, yt-lockup-view-model yt-content-metadata-view-model span):has-text(/^Streamed/))

! hide garbage videos (less than 80% like ratio) on Home Page
www.youtube.com##[page-subtype="home"] ytd-rich-item-renderer:has(.ytrb-percentage:has-text(/^(?:[0-9]|[1-7][0-9])(\.[0-9]{1,2})?%$/))

! hide "Members only" videos on Home Page
www.youtube.com##[page-subtype="home"] ytd-rich-item-renderer:has(.badge-style-type-members-only)

! hide "Premium" videos on Home Page
www.youtube.com##[page-subtype="home"] ytd-rich-item-renderer:has(.badge[aria-label="Premium"])

! hide "Pay to watch" videos on Home Page
www.youtube.com##[page-subtype="home"] ytd-rich-item-renderer:has(.badge[aria-label="Pay to watch"])

! hide "Upcoming" videos on Home Page
www.youtube.com##[page-subtype="home"] ytd-rich-item-renderer:has(ytd-thumbnail-overlay-time-status-renderer[overlay-style="UPCOMING"])

! hide big yoodle banner on Home Page
www.youtube.com##[page-subtype="home"] #big-yoodle

! hide "how did you like this video" survey crap on Home Page
www.youtube.com##[page-subtype="home"] ytd-rich-section-renderer:has(ytd-inline-survey-renderer)

! remove badges like "Fundraiser" from videos on Home Page
www.youtube.com##[page-subtype="home"] yt-lockup-view-model yt-content-metadata-view-model > div:nth-child(3):remove()

! set responsive grid layout on Home Page and fix item margins
www.youtube.com##[page-subtype="home"] ytd-rich-grid-renderer.ytd-two-column-browse-results-renderer:matches-media((max-width: 1500px)):style(--ytd-rich-grid-items-per-row: 3 !important;)
www.youtube.com##[page-subtype="home"] ytd-rich-grid-renderer.ytd-two-column-browse-results-renderer:matches-media((min-width: 1500px) and (max-width: 2000px)):style(--ytd-rich-grid-items-per-row: 4 !important;)
www.youtube.com##[page-subtype="home"] ytd-rich-grid-renderer.ytd-two-column-browse-results-renderer:matches-media((min-width: 2000px) and (max-width: 2500px)):style(--ytd-rich-grid-items-per-row: 5 !important;)
www.youtube.com##[page-subtype="home"] ytd-rich-grid-renderer.ytd-two-column-browse-results-renderer:matches-media((min-width: 2500px)):style(--ytd-rich-grid-items-per-row: 6 !important;)
www.youtube.com##[page-subtype="home"] ytd-rich-grid-renderer > #contents > ytd-rich-item-renderer[rendered-from-rich-grid]:remove-attr(is-in-first-column)

! ============================
! YouTube Subscriptions Page
! ============================

! hide disruptive sections like "Shorts" on Subscriptions Page
www.youtube.com##[page-subtype="subscriptions"] ytd-rich-section-renderer:has(#dismissible)

! hide upcoming videos on Subscriptions Page
www.youtube.com##[page-subtype="subscriptions"] ytd-rich-item-renderer:has(ytd-thumbnail-overlay-time-status-renderer[overlay-style="UPCOMING"])

! hide "Members only" videos on Subscriptions Page
www.youtube.com##[page-subtype="subscriptions"] ytd-rich-item-renderer:has(.badge-style-type-members-only)

! hide "Premium" videos on Subscriptions Page
www.youtube.com##[page-subtype="subscriptions"] ytd-rich-item-renderer:has(.badge[aria-label="Premium"])

! hide videos I already watched in full (>=70%) on Subscriptions Page
www.youtube.com##[page-subtype="subscriptions"] ytd-rich-item-renderer:has(:is(#progress, .ytThumbnailOverlayProgressBarHostWatchedProgressBarSegment):matches-attr(style="/width: ([789][0-9]|100)%/"))

! hide all recorded live streams turned into videos ("Streamed 8 hours ago" etc.) on Subscriptions Page
www.youtube.com##[page-subtype="subscriptions"] ytd-rich-item-renderer:has(:is(.inline-metadata-item.ytd-video-meta-block, yt-lockup-view-model yt-content-metadata-view-model span):has-text(/^Streamed/))

! remove badges like "Fundraiser" from videos on Subscriptions Page
www.youtube.com##[page-subtype="subscriptions"] yt-lockup-view-model yt-content-metadata-view-model > div:nth-child(3):remove()

! set responsive grid layout on Subscriptions Page and fix item margins
www.youtube.com##[page-subtype="subscriptions"] ytd-rich-grid-renderer.ytd-two-column-browse-results-renderer:matches-media((max-width: 1500px)):style(--ytd-rich-grid-items-per-row: 3 !important;)
www.youtube.com##[page-subtype="subscriptions"] ytd-rich-grid-renderer.ytd-two-column-browse-results-renderer:matches-media((min-width: 1500px) and (max-width: 2000px)):style(--ytd-rich-grid-items-per-row: 4 !important;)
www.youtube.com##[page-subtype="subscriptions"] ytd-rich-grid-renderer.ytd-two-column-browse-results-renderer:matches-media((min-width: 2000px) and (max-width: 2500px)):style(--ytd-rich-grid-items-per-row: 5 !important;)
www.youtube.com##[page-subtype="subscriptions"] ytd-rich-grid-renderer.ytd-two-column-browse-results-renderer:matches-media((min-width: 2500px)):style(--ytd-rich-grid-items-per-row: 6 !important;)
www.youtube.com##[page-subtype="subscriptions"] ytd-rich-grid-renderer > #contents > ytd-rich-item-renderer[rendered-from-rich-grid]:remove-attr(is-in-first-column)

! ============================
! YouTube Search Results
! ============================

! hide garbage videos (less than 80% like ratio) in Search Results
www.youtube.com##ytd-search ytd-video-renderer:has(.ytrb-percentage:has-text(/^(?:[0-9]|[1-7][0-9])(\.[0-9]{1,2})?%$/))

! hide shorts (disguised as regular videos) in Search Results
www.youtube.com##ytd-search ytd-video-renderer:has(badge-shape[aria-label="Shorts"])

! hide shorts shelf in Search Results
www.youtube.com##ytd-search ytd-reel-shelf-renderer
www.youtube.com##ytd-search grid-shelf-view-model:has(.shortsLockupViewModelHost)

! hide fluff ("People also watched", "For you", "Previously watched" etc.) in Search Results
www.youtube.com##ytd-search ytd-shelf-renderer[thumbnail-style]
www.youtube.com##ytd-search #contents > ytd-horizontal-card-list-renderer

! hide movies you can rent or "buy" in Search Results
www.youtube.com##ytd-search ytd-movie-renderer

! hide right sidebar with ads for streaming services in Search Results
www.youtube.com##ytd-search ytd-secondary-search-container-renderer:has(ytd-universal-watch-card-renderer)

! ============================
! YouTube Channel Page
! ============================

! Channel Page: Header & Tabs Menu

! hide big top banner on channel header
www.youtube.com##[page-subtype="channels"] #page-header-banner

! hide links ("example.com and 3 more links") on channel header
www.youtube.com##[page-subtype="channels"] yt-attribution-view-model

! hide "Join" button on channel header
www.youtube.com##[page-subtype="channels"] yt-flexible-actions-view-model .yt-flexible-actions-view-model-wiz__action:has(button-view-model:has-text(/^Join/))

! hide "Subscribe +" button on channel header
www.youtube.com##[page-subtype="channels"] yt-flexible-actions-view-model .yt-flexible-actions-view-model-wiz__action:has(yt-subscribe-plus-button-view-model)
www.youtube.com##[page-subtype="channels"] yt-flexible-actions-view-model .ytFlexibleActionsViewModelAction:has(>yt-subscribe-plus-button-view-model)

! fix existing "Subscribed" button (restore deleted button text)
www.youtube.com##[page-subtype="channels"] yt-flexible-actions-view-model yt-subscribe-button-view-model.yt-subscribe-button-view-model-wiz:style(width:auto !important;)
www.youtube.com##[page-subtype="channels"] yt-flexible-actions-view-model button.yt-spec-button-shape-next--icon-leading-trailing-no-text .yt-spec-button-shape-next__secondary-icon::before:style(display: block; content: "Subscribed"; margin-right: 6px;)
www.youtube.com##[page-subtype="channels"] yt-flexible-actions-view-model button.yt-spec-button-shape-next--icon-leading-trailing-no-text .yt-spec-button-shape-next__secondary-icon:style(display: flex; align-items: center; width: inherit;)

! Channel Page: Page Content

! hide "Shorts" section on channel home page
www.youtube.com##[page-subtype="channels"] ytd-section-list-renderer > #contents > ytd-item-section-renderer:has(ytd-reel-shelf-renderer)

! hide "Our Members" section on channel home page
www.youtube.com##[page-subtype="channels"] ytd-section-list-renderer > #contents > ytd-item-section-renderer:has(ytd-recognition-shelf-renderer)

! hide videos I already watched in full (>=70%) on channel home page
www.youtube.com##[page-subtype="channels"] ytd-grid-video-renderer:has(:is(#progress, .ytThumbnailOverlayProgressBarHostWatchedProgressBarSegment):matches-attr(style="/width: ([789][0-9]|100)%/"))

! hide videos I already watched in full (>=70%) on channel videos page
www.youtube.com##[page-subtype="channels"] ytd-rich-item-renderer:has(:is(#progress, .ytThumbnailOverlayProgressBarHostWatchedProgressBarSegment):matches-attr(style="/width: ([789][0-9]|100)%/"))

! hide "Premium" videos on channel videos page
www.youtube.com##[page-subtype="channels"] ytd-rich-item-renderer:has(.badge[aria-label="Premium"])

! hide "Members only" videos on channel videos page
www.youtube.com##[page-subtype="channels"] ytd-rich-item-renderer:has(.badge-style-type-members-only)

! ============================
! YouTube Video Page
! ============================

! Video Page: Video Player

! reenable the possibility to scroll down the page when the player is in fullscreen
www.youtube.com##[deprecate-fullerscreen-ui]:remove-attr(deprecate-fullerscreen-ui)

! hide "1080p Premium HD" in video quality settings menu
www.youtube.com##.ytp-quality-menu .ytp-menuitem:has(.ytp-premium-label)

! hide video overlay on endcards
www.youtube.com##ytd-player .ytp-ce-element.ytp-ce-element-show.ytp-ce-video

! hide playlist overlay on endcards
www.youtube.com##ytd-player .ytp-ce-element.ytp-ce-element-show.ytp-ce-playlist

! hide website overlay on endcards
www.youtube.com##ytd-player .ytp-ce-element.ytp-ce-element-show.ytp-ce-website

! hide channel overlay on endcards
www.youtube.com##ytd-player .ytp-ce-element.ytp-ce-element-show.ytp-ce-channel

! automatically click on "I understand and wish to proceed" button on age-restricted content warnings
www.youtube.com##+js(trusted-click-element, div[id^="player-container"] + #error-screen #info:has(#reason) button[aria-label*="proceed"])

! Video Page: Title and Description

! prevent stats (such as likes and views) from live-updating
||youtube.com/youtubei/v1/updated_metadata

! hide "smartimation" animations
www.youtube.com##yt-smartimation > :not(.smartimation__content)
www.youtube.com##yt-animated-action > :not(.animated-action__content-with-background, .ytAnimatedActionContentWithBackground)
www.youtube.com##:is(.smartimation__content, .animated-action__content-with-background, .ytAnimatedActionContentWithBackground) > :has(> lottie-component)

! disable live reaction overlays
www.youtube.com##yt-reaction-control-panel-view-model, yt-reaction-control-panel-overlay-view-model

! hide "Purchase" button below video
www.youtube.com##ytd-video-owner-renderer > #purchase-button

! hide "Join" button below video
www.youtube.com##ytd-video-owner-renderer > #sponsor-button

! fix existing "Subscribed" button (restore deleted button text)
www.youtube.com#$#ytd-subscribe-button-renderer[subscribe-button-invisible][style^="width"],ytd-subscribe-button-renderer[subscribe-button-invisible] yt-subscribe-button-view-model[style^="width"] { width: auto!important; }
www.youtube.com#$#ytd-subscribe-button-renderer[subscribe-button-invisible] button.yt-spec-button-shape-next--icon-leading-trailing-no-text .yt-spec-button-shape-next__secondary-icon::before {display: block; content: "Subscribed"; margin-right: 6px;}
www.youtube.com#$#ytd-subscribe-button-renderer[subscribe-button-invisible] button.yt-spec-button-shape-next--icon-leading-trailing-no-text .yt-spec-button-shape-next__secondary-icon {display: flex; align-items: center; width: inherit;}

! hide "Download" button below video
www.youtube.com###below ytd-download-button-renderer
www.youtube.com##ytd-menu-popup-renderer ytd-menu-service-item-download-renderer

! hide "Thanks" button below video
www.youtube.com###below yt-button-view-model:has(button[aria-label="Thanks"])
www.youtube.com##ytd-menu-popup-renderer ytd-menu-service-item-renderer:has(yt-formatted-string:has-text(/^Thanks/))

! hide "Clip" button below video
www.youtube.com###below yt-button-view-model:has(button[aria-label="Clip"])
www.youtube.com##ytd-menu-popup-renderer ytd-menu-service-item-renderer:has(yt-formatted-string:has-text(/^Clip/))

! hide fundraiser badge below video title
www.youtube.com###below ytd-badge-supported-renderer

! hide that light blue "Clarify box" below video player, above video title
www.youtube.com###below > #clarify-box

! hide that "... is a public broadcast service" box between video and description
www.youtube.com###below #middle-row:has(ytd-info-panel-content-renderer)

! hide merch shelf in description
www.youtube.com###below ytd-structured-description-content-renderer #merch-shelf

! hide "Chapters" in description
www.youtube.com###below ytd-structured-description-content-renderer #items ytd-horizontal-card-list-renderer[modern-chapters]

! hide "Shorts remixing this video" in description
www.youtube.com###below ytd-structured-description-content-renderer #items ytd-reel-shelf-renderer

! hide "Music" in description
www.youtube.com###below ytd-structured-description-content-renderer #items ytd-horizontal-card-list-renderer[has-video-attribute-view-models]

! hide "Transcription" in description
www.youtube.com###below ytd-structured-description-content-renderer #items ytd-video-description-transcript-section-renderer

! hide that creator infobox with links at the end of the description box
www.youtube.com###below ytd-structured-description-content-renderer #items ytd-video-description-infocards-section-renderer

! hide "Live Chat Replay" box which sometimes appears next to the description
www.youtube.com###below #teaser-carousel

! hide merch shelf below description
www.youtube.com###below ytd-merch-shelf-renderer

! hide shitty AI summary nobody ever asked for below description
www.youtube.com###below [has-video-summary]

! hide all "Age-restricted video" notices below description, above comment section
www.youtube.com##ytd-metadata-row-container-renderer > #always-shown > ytd-metadata-row-renderer:has(a[href*="community_guidelines"],a[href*="age_restrictions"])

! hide all "Rating" notices below video description, above comment section
www.youtube.com##ytd-metadata-row-container-renderer > #always-shown > ytd-metadata-row-renderer:has(a[href*="answer/146397"])

! hide that fucking "Experiencing interruptions?" toast message because of AdBlock
www.youtube.com##tp-yt-paper-toast#toast:has(yt-button-renderer#action-button a[href*=blocker])

! Video Page: Sidebar / Related videos

! hide donation box for fundraiser videos
www.youtube.com###secondary #donation-shelf

! hide Shorts in video sidebar
www.youtube.com###columns #secondary ytd-compact-video-renderer:has(a[href^="/shorts/"])

! hide that weird channel card which sometimes appears somewhere in video sidebar
www.youtube.com###columns #secondary ytd-channel-renderer

! hide garbage videos (less than 80% like ratio) in video sidebar
www.youtube.com##ytd-watch-flexy yt-lockup-view-model:has(.ytrb-percentage:has-text(/^(?:[0-9]|[1-7][0-9])(\.[0-9]{1,2})?%$/))

! hide "Members first" videos in video sidebar
www.youtube.com##ytd-watch-flexy yt-lockup-view-model:has(.badge-shape-wiz--commerce)

! hide old videos (1 year and older) in video sidebar
www.youtube.com##ytd-watch-flexy yt-lockup-view-model:has(yt-content-metadata-view-model span:has-text(/^\d+ years? ago$/))

! hide super short videos (shorter than 1 minute) in video sidebar
www.youtube.com##ytd-watch-flexy yt-lockup-view-model:has(yt-thumbnail-overlay-badge-view-model:has-text(/^0:/))

! hide super long videos (1 hour and longer) in video sidebar
www.youtube.com##ytd-watch-flexy yt-lockup-view-model:has(yt-thumbnail-overlay-badge-view-model:has-text(/^\d+:\d\d:/))

! hide live streams in video sidebar
www.youtube.com##ytd-watch-flexy yt-lockup-view-model:has(.badge-shape-wiz--thumbnail-live)

! hide videos I already watched in full (>=70%) in video sidebar
www.youtube.com##ytd-watch-flexy yt-lockup-view-model:has(.ytThumbnailOverlayProgressBarHostWatchedProgressBarSegment:matches-attr(style="/width: ([789][0-9]|100)%/"))

! hide playlists in video sidebar
www.youtube.com##ytd-watch-flexy yt-lockup-view-model:has(yt-content-metadata-view-model:has-text(/^Playlist/))

! hide videos with less than 2000 views in video sidebar
www.youtube.com##ytd-watch-flexy yt-lockup-view-model:has(yt-content-metadata-view-model span:has-text(/^(\d{1,3} |No |1(\.\d)?K )views?$/))

! remove badges like "Fundraiser" from videos in video sidebar
www.youtube.com##ytd-watch-flexy yt-lockup-view-model yt-content-metadata-view-model > div:nth-child(3):remove()

! remove video recommendations at the end of videos
youtube.com##.html5-video-player.ended-mode .ytp-fullscreen-grid

! hide videos when scrolling
www.youtube.com##.ytp-fullscreen-grid

! Live chat
youtube.com##ytd-watch-flexy[live-chat-present-and-expanded] #columns:style(padding-right: 0 !important;)
youtube.com###chat-container, ytd-watch-flexy[live-chat-present-and-expanded] #panels-full-bleed-container

! ============================
! Title: YouTube Fullscreen Theater Mode
! Expires: 1 days
! Description: Forces YouTube's native theater mode to behave as windowed fullscreen.
! ============================

www.youtube.com##html:has(ytd-watch-flexy[theater]):style(overflow: hidden !important;)
www.youtube.com##html:has(ytd-watch-grid[theater]):style(overflow: hidden !important;)
www.youtube.com##body:style(overflow-anchor: none !important;)

www.youtube.com##ytd-masthead[theater]:upward(#masthead-container):style(display: none !important;)

www.youtube.com##ytd-watch-flexy[theater] #player-full-bleed-container.ytd-watch-flexy:style(height: 100vh !important; min-height: 100vh !important; max-height: 100vh !important; margin-top: 0px !important; background: #000000 !important;)
www.youtube.com##ytd-watch-grid[theater] #player-full-bleed-container.ytd-watch-grid:style(height: 100vh !important; min-height: 100vh !important; max-height: 100vh !important; margin-top: 0px !important; background: #000000 !important;)

www.youtube.com##ytd-watch-flexy[theater] #full-bleed-container.ytd-watch-flexy:style(block-size: fit-content !important; max-height: fit-content !important; background: #000000 !important;)
www.youtube.com##ytd-watch-grid[theater] #full-bleed-container.ytd-watch-grid:style(block-size: fit-content !important; max-height: fit-content !important; background: #000000 !important;)

www.youtube.com##ytd-watch-flexy[theater] #player-container:style(height: 100vh !important; top: 0 !important; background: #000000 !important;)
www.youtube.com##ytd-watch-flexy[theater] #ytd-player:style(height: 100vh !important; top: 0 !important; background: #000000 !important;)
www.youtube.com##ytd-watch-flexy[theater] .html5-video-player:style(height: 100vh !important; min-height: 100vh !important; top: 0 !important; background: #000000 !important;)

www.youtube.com##ytd-watch-flexy[theater] #columns:style(padding-top: 0px !important;)
www.youtube.com##ytd-watch-grid[theater] #columns:style(padding-top: 0px !important;)

www.youtube.com##ytd-live-chat-frame[theater-watch-while]:style(top: 0 !important; border-top-left-radius: 0 !important; border-top-right-radius: 0 !important;)
