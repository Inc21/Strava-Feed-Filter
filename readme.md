# Strava Feed Filter

A powerful Chrome Extension and Firefox Extension that provides advanced filtering
capabilities for your Strava activity feed. Built with a modular architecture
for maximum performance and maintainability.

> Note: As of v1.2.4, this project includes Firefox Extension (desktop and Android). As of v2.2.5, Chrome Extension with complete feature parity is also available. **As of v2.4.5, both Firefox and Chrome extensions feature enhanced mobile support with notification system and bidirectional panel resizing. As of v2.5.0, both extensions include a compact settings panel with info icons and device-based activity filtering.**
>
> ⚠️ **Userscripts are deprecated** and will no longer receive updates or new features. Please use the Chrome or Firefox extension instead. iPhone/iPad users can get the full extension experience via the [Orion Browser](https://orionbrowser.com/) — see [ios-safari-install.md](./ios-safari-install.md).

![Strava Feed Filter in action](./src/readme-images/filter-panel-overview.png)
*Filter panel*

## Description

This filter enhances your Strava experience by providing comprehensive
filtering capabilities directly on your feed. Hide activities based on
keywords, activity types, distance, duration, elevation, pace, and more.
The filter features a clean, draggable interface that works seamlessly
with Strava's design.

## 🆕 What's New

- **v2.8.3** — 🐛 **Fixed for Strava's new header!** Strava rebuilt the global header as a React component, which took the filter button's anchor, the header kudos button and the header row with it — the button ended up below the feed and the row stayed hidden. Both buttons now sit on the new header's notification item, and the row takes over as soon as Strava drops its own main links. The "Show more stats" button in the feed is back as well.
- **v2.8.2** — 🎛️ **Filter modes & a much wider mobile layout!** The on/off switch is now a five-button mode bar — **OFF / LIGHT / MEDIUM / STRICT / CUSTOM** — each preset describing exactly what it hides, with your own configuration untouched underneath. 📱 The opt-in mobile layout now covers **athlete profiles, settings pages (My Gear, My Account) and segment pages** as well as activity details. Filter and kudos buttons move as one set below the header once it runs out of room, instead of shrinking to an icon. New **KlimatApp** and **MyBikeTraffic** embed filters, embed filtering on activity detail pages, and a fix for the Wandrer snippet being left half visible.
- **v2.8.1** — 🐛 **Group filtering fix & new post controls!** Group activities now resolve their sport from the group header ("X rode / ran / walked / hiked / swam with Y") plus the recording platform, so **Virtual Ride / Virtual Run** and other sport filters now catch group entries too. New **Hide athlete posts** and **Hide Strava promotional posts** options in the Other section keep non-activity cards out of the feed.
- **v2.8.0** — ➕ Added **Physical Therapy** to the Activity Types filter (56 types) to match Strava's new dedicated sport type for recovery & rehabilitation sessions. Also added **Indoor Cycling**, **Long Run**, **Treadmill** and **Competition** to the Activity Tags filter (11 tags). New **Hide Untagged** option in the Activity Tags section hides all activities that have no tags. 📱 New opt-in **Mobile Responsive** layout adapts **activity detail pages** to phones and narrow windows (beta — more pages coming). 🐛 Fixed the notification bell's red count requiring two opens to clear on mobile.
- **v2.7.0** — ✨ **Custom embed & device filtering improvements!** New custom embed filters field in 3rd Party Embeds section with real-time matching. Custom recording device field now also applies in real-time. Fixed partial device name matching (e.g. "ELEMNT" now matches "Wahoo ELEMNT ROAM").
- **v2.6.2** — ✨ **Update notifications & UI improvements!** In-panel update notification banner with version checking. Keyword preset buttons for Warm Up and Cool Down. Compact header buttons option for a cleaner interface. Improved dark mode support and panel usability.
- **v2.5.0** — ✨ **Major UI & filtering improvements!** Compact settings panel with clickable info icons replacing verbose helper text. New device-based filtering with support for 21+ predefined devices (Zwift, Garmin, Wahoo, etc.) plus custom device field. Full support for group activities with improved device detection prioritizing metadata over user-editable names.
- **v2.4.7** — 🐛 **Bug fixes & enhancements!** Fixed extension message listener for proper popup communication. Added "See what's new" link to extension popups linking to GitHub changelog.
- **v2.4.6** — 🐛 **Bug fixes!** Fixed notification badge not clearing when viewing notifications - now properly marks all as read using Strava's API with CSRF authentication. Fixed badge color (now red instead of orange) and improved positioning in Chrome. Added missing "Hide Start Trial" functionality for Strava free users without premium subscriptions (bug reported by Reddit user: andreasbeer1981).
- **v2.4.5** — 📱 **Major mobile improvements!** Both Firefox and Chrome extensions now feature a notification bell for mobile screens (≤990px), bidirectional panel resizing (drag from left or right edge), and viewport-aware UI that automatically adapts to screen size. Complete feature parity achieved between both extensions.
- Read the full history in the Changelog: [CHANGELOG.md](./CHANGELOG.md)

## ✨ Key Features

### 🎯 Filtering Options

- **Keyword Filtering**: Hide activities containing specific keywords in titles
- **Activity Type Filtering**: Granular control over 40+ activity types
  (Run, Ride, Virtual activities, etc.)
- **Recording Device Filtering**: Hide activities by recording device (NEW in v2.5.0)
  - 21+ predefined devices: Apple, Bryton, COROS, Elite, Fitbit, Garmin, Hammerhead, MyWhoosh, Peloton, Polar, Rouvy, Samsung, Stages, Strava, Suunto, Tacx, TrainerRoad, Wahoo, Wahoo SYSTM, Whoop, Zwift
  - Custom device text field for user-defined devices
  - Select All / Clear All quick actions
  - Full support for group activities
- **Quick tip – isolate one type fast**: Click "Select All", then deselect the activity you'd like to show. For example, to see only hikes: open **Activity Types**, press **Select All**, then untick **Hike**. The feed will show only hikes while hiding every other category.

  > 💡 Want the opposite? Hit **Clear All** and tick just the one type you want to hide.

- **Distance Filtering**: Set minimum and maximum distance thresholds
- **Duration Filtering**: Specify minimum and maximum duration for activities
- **Elevation Filtering**: Control based on elevation gain
- **Pace Filtering**: Filter running activities by pace (min/km or min/mi)
- **Map Filtering**: Hide activities without GPS maps
- **Commute Tag Filtering**: Hide activities marked with the Commute tag
- **Club Posts**: Option to hide club-related posts
- **Athlete Posts**: Option to hide athlete text/photo posts
- **Strava Promotional Posts**: Option to hide trial offers and Strava promo cards in the feed
- **Challenge Filtering**: Hide your challenges section
- **Hide Joined Challenges**: Hide athletes' joined challenge cards from the feed
- **External Service Embeds Filtering**: Option to hide text embeds from third-party services in activity descriptions (e.g., myWindsock report, summitbag.com, Run Health, Wandrer, Bandok.com, COROS, Rouvy, eVISO, Cyql, Restortrain, KlimatApp, MyBikeTraffic), with a custom pattern field for anything else
- **Embed Filters on Detail Pages**: The preset embed filters also run on an activity detail page, where the description is rendered outside the feed
- **Athlete Management**: Ignore specific athletes to hide all their activities from your feed
- **UI Sections Hiding**: Hide "Suggested Friends" and "Your Clubs" sections site-wide

### 🎨 Interface & Notifications

- **Compact Settings Panel**: Info icons replace verbose helper text (NEW in v2.5.0)
  - Blue ℹ icons provide explanations on click
  - Tooltips with close button and click-outside dismiss
  - Saves significant UI space while maintaining accessibility
- **Mobile Notification System**: Bell icon on mobile screens (≤990px) for quick access to Strava notifications
- **Responsive Design**: Adapts to different screen sizes and Strava layouts
- **Bidirectional Panel Resizing**: Drag left or right edge to resize the filter panel (280px - 600px)
- **Draggable Panel**: Move the settings panel anywhere on screen
- **Collapsible Sections**: Organized dropdown sections for easy navigation
- **Real-time Updates**: See filtering results immediately as you adjust
  settings
- **Global Settings**: Hide elements like "Give a Gift" button across all
  Strava pages
- **Sidebar Dropdown**: New dropdown in the separate sidebar for quick access
- **Panel Tweaks**: Slightly wider settings panel and an always-visible panel scrollbar to avoid flicker

![Filter panel interface](./src/readme-images/filter-panel-sections.png)
*Organized sections with collapsible dropdowns*

### 🔧 Smart Features

- **Unit System Support**: Switch between Metric and Imperial units
- **Allowed Athletes**: Override filters for specific athletes you always
  want to see
- **Auto-filtering**: Automatically filters new activities as they load
- **Kudos Integration**: Optional "Give Kudos to Everyone" button
- **SPA Navigation**: Works seamlessly with Strava's single-page application

### 🏗️ Architecture & Performance

- **Modular Architecture**: Clean separation of concerns (CSS, UI, Logic, Utils)
- **Memory Optimization**: Efficient event handling and DOM manipulation
- **Error Handling**: Robust error handling with graceful fallbacks
- **Performance**: Debounced filtering and optimized DOM queries

## 📱 Responsive Design

The filter adapts seamlessly to different screen sizes with enhanced mobile support:

- **Desktop**: Full-featured panel with all options; the filter and kudos buttons sit in Strava's header row
- **Narrower windows**: Once the header runs out of room (or Strava collapses it behind the hamburger), both buttons move together into a row below the header at full size, aligned to the header's content column — the switch is measured from the header's own layout, not a fixed breakpoint
- **Mobile (≤1305px)**: Strava's own mobile layout takes over, with our row, compact header and hamburger handling
  - **Notification bell** for quick access to Strava notifications
  - Real-time unread notification badge
  - Tap bell to view notification dropdown
- **Responsive Panel**:
  - Drag left or right edge to resize (280px - 600px)
  - Automatically repositions to avoid UI conflicts
  - Position and size persist across sessions

![Responsive design](./src/readme-images/responsive-layout.png)
*Filter button adapts to different screen sizes*

### 📱 Mobile Responsive Layout (Beta)

> 🚧 **Work in progress.** Our opt-in **Mobile Responsive** mode reflows Strava's fixed-width pages for phones and narrow browser windows:
>
> - **Activity details** — Strava's native Name–Type header, a reorganised stats grid, swipe/drag panning for the elevation chart and segment tables, full-screen photo lightboxes and a back-to-top button.
> - **Athlete profiles** — the photo collage, Last 4 Weeks summary, tab strip and trophies stack into single columns; trophies are capped at three rows with a **Show all N trophies** button, and the activity-log graph becomes a pannable strip on phones.
> - **Settings pages** — My Gear, My Account and component pages: the settings menu scrolls sideways like a tab strip, the gear image and Edit button stop floating, and the component tables fit the screen instead of scrolling.
> - **Segment pages** — the leaderboard, filter dropdown, PR comparison and Local Legend button fit the column, and the elevation profile and map stack.
>
> The dashboard feed keeps Strava's native layout for now.

## 🎛️ Settings Panel

The main settings panel features organized sections:

1. **Master Toggle**: Enable/disable all filtering
2. **Keywords**: Text-based filtering
3. **Allowed Athletes**: Whitelist specific users
4. **Ignored Athletes**: Hide activities from specific users
5. **Activity Types**: Checkboxes for each activity type with live count
6. **Min/Max Filters**: Distance, duration, elevation, pace controls
7. **Other Options**: Map filtering, club posts, athlete posts, Strava promos, challenges, global settings
8. **Settings Management**: Import/export settings, reset to defaults

![Settings panel sections](./src/readme-images/filter-sections.png)
*Well-organized filtering options*

## 🚀 Installation

Choose the option that fits your browser/platform.

### Chrome Extension

- Install from [Chrome Web Store](https://chromewebstore.google.com/detail/geihkfcdimdmlckcgkebcdajdlmeppff?utm_source=item-share-cb)

### Firefox Extension

- Install from [Firefox Add-ons](https://addons.mozilla.org/en-US/firefox/addon/strava-feed-filter/)

### Userscript (Desktop Browsers) — ⚠️ DEPRECATED

> **Userscripts are no longer maintained.** They will not receive new features or bug fixes and will be removed in a future release. Please switch to the Chrome or Firefox extension above for the full experience.

- ~~Install from [Greasy Fork](https://greasyfork.org/en/scripts/550272-strava-feed-filter)~~
- ~~Manual installation: Download `userscript/strava-feed-filter-clean.js` and install via your userscript manager.~~

### Orion Browser (iOS & iPadOS)

- ▶️ Follow the dedicated Orion setup guide: [ios-safari-install.md](https://github.com/Inc21/Tempermonkey-Strava-Feed-Filter/blob/main/ios-safari-install.md)
- Install Orion from the [App Store](https://apps.apple.com/app/orion-browser-by-kagi/id1484498200) or TestFlight, enable extensions, then add SFF from the [Chrome Web Store](https://chromewebstore.google.com/detail/geihkfcdimdmlckcgkebcdajdlmeppff) or [Firefox Add-ons](https://addons.mozilla.org/en-US/firefox/addon/strava-feed-filter/).
- Full desktop extension feature set (dark mode, notification bell, update banner) now works on iPhone/iPad via Orion.

**Disclaimer:** This extension has been primarily tested on Chrome, Firefox, and Orion (iOS). Support for other browsers may vary.

## 📖 Usage Guide

### Getting Started

1. Navigate to your [Strava Dashboard](https://www.strava.com/dashboard)
2. Look for the **"Filter"** button (top-right on desktop, or secondary nav
   on mobile)
3. Click the button to open the settings panel
4. Configure your filtering preferences
5. Activities are filtered in real-time

![Filter button location](./src/readme-images/filter-button-location.png)
*Filter button in the Strava interface*

### Page Behavior

- **Dashboard Pages**: Full filtering functionality available
- **Other Strava Pages**: Global settings applied (e.g., "Give a Gift"
  button hiding)
- **Auto-detection**: Script automatically detects page type and applies
  appropriate features

### Filtering Tips

- Use **Keywords** to hide activities with specific terms (e.g., "warm up",
  "recovery")
- Set **Distance ranges** to focus on activities of interest
- Use **Allowed Athletes** to always see activities from favorite users
- **Activity Type** filtering helps reduce clutter from activity types you
  don't follow
- **Pace filtering** is perfect for runners wanting to see only quality workouts

## 🛠️ Configuration Options

### Unit Systems

- **Metric**: Kilometers, meters, min/km
- **Imperial**: Miles, feet, min/mi

### Filter Categories

| Category | Options | Description |
| --- | --- | --- |
| Keywords | Text input | Hide activities containing specified words |
| Activity Types | 20+ checkboxes | Show/hide specific activity types |
| Distance | Min/Max sliders | Filter by activity distance |
| Duration | Min/Max inputs | Filter by activity time |
| Elevation | Min/Max inputs | Filter by elevation gain |
| Pace | Min/Max inputs | Filter running pace (runs only) |
| Map | Checkbox | Hide activities without GPS data |
| Athletes | Text input | Whitelist specific users |

## 🎨 Customization

### Panel Positioning & Resizing

- **Drag** the panel by its header to reposition
- **Resize** the panel by dragging left or right edge (280px - 600px width)
- **Automatic positioning** under the filter button when opened
- **Viewport constraints**: Panel stays within browser window
- **Position memory**: Panel location and size persist across sessions

### Theme & Styling

- **Strava-native styling**: Matches Strava's design language
- **Dark/Light themes**: Adapts to Strava's theme
- **Smooth animations**: Fade in/out transitions
- **Responsive breakpoints**: Mobile-optimized layout

## 🏗️ Architecture

The script uses a clean modular architecture:

```javascript
// CSS Module - All styling centralized
injectStyles()

// Utilities Module - Core functionality
UtilsModule {
    loadSettings(), saveSettings(), debounce(),
    isOnDashboard(), parseDistanceKm(), parseDurationSeconds(),
    parseElevationM()
}

// UI Module - Interface management
UIModule {
    createElements(), updateActivityCount(), updateFilterLabels(),
    applySettings(), setupEvents(), makeDraggable(), keepInViewport()
}

// Logic Module - Business logic
LogicModule {
    filterActivities(), updateGiftVisibility(),
    manageHeaderKudosButton(), setupAutoFilter()
}
```

## 🔧 Developer Information

### Technical Implementation

- **Memory-efficient**: Uses debouncing and optimized DOM queries
- **SPA-compatible**: Handles Strava's single-page application navigation
- **Error resilient**: Comprehensive error handling with fallbacks
- **Browser compatible**: Works across all major browsers
- **Performance optimized**: Minimal impact on Strava's performance

### Contributing

Developed by [Inc21](https://github.com/Inc21). Contributions and suggestions
welcome!

### Support the Developer

If you find this script useful, consider:

- ⭐ Starring the repository
- ☕ [Buy me a coffee](https://www.buymeacoffee.com/inc21)
- 🐛 Reporting bugs or suggesting features: [GitHub Issues](https://github.com/Inc21/Tempermonkey-Strava-Feed-Filter/issues)

## 🔄 Filtering Results

See the difference filtering makes on your Strava feed:

**Before Filtering:**
![Before filtering](./src/readme-images/before-filtering.png)
*Strava feed showing all activities*

**After Filtering:**
![After filtering](./src/readme-images/after-filtering.png)
*Same feed with filters applied - notice the reduced activity count*

## 🎯 Activity Count Display

![Activity count feature](./src/readme-images/activity-count-display.png)
*Real-time count showing "(X hidden / Y total)" for activity types*

## Changelog

For the complete release notes, see [CHANGELOG.md](./CHANGELOG.md).
Latest release: v2.8.3 (28.10.2026) - Compatibility fix for Strava's new React header (header row, filter and kudos buttons, "Show more stats" in the feed).

## 📄 License

This project is licensed under the **MIT License**. See the [LICENSE](./LICENSE) file for details.

---

**Note**: This userscript is not affiliated with Strava. It's a community tool
designed to enhance the user experience.
