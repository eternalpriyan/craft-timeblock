# Craft Timeblock Viewer

A visual timeline view for your Craft daily notes. See your day at a glance, drag to reschedule, and stay focused.

![Timeblock Viewer](https://img.shields.io/badge/zero--build-vanilla%20JS-brightgreen) ![License](https://img.shields.io/badge/license-MIT-blue)

## The Story

I used to be a heavy [Noteplan](https://noteplan.co/) user before switching to [Craft Docs](https://www.craft.do/). The one thing I missed? **The timeblocking view.** Being able to see my entire day laid out visually was invaluable for focus and time awareness.

Now, thanks to the new [Craft Imagine API](https://developer.craft.do/) (and some Claude Code sorcery), I have it again.

## Features

- **Visual Timeline**: See your day from 6 AM to 10 PM (configurable)
- **Drag & Drop**: Reschedule timeblocks by dragging them around
- **Resize**: Adjust duration by dragging the top or bottom edge
- **Date Navigation**: Browse through days with arrow buttons or keyboard shortcuts
- **Fuzzy Time Parsing**: Flexible format support (see below)
- **Dark/Light Theme**: Styled with Claude Desktop's color palette
- **Touch Support**: Works great on iPad and iPhone
- **Zero Dependencies**: Single HTML file, no build step required

### Flexible Time Formats

The parser understands many natural time formats:

```
10:00 AM - 11:00 AM - Team standup     # Full format
10-11 AM - Team standup                 # Shared AM/PM, no minutes
10 AM to 11 AM - Deep work              # "to" separator
14:00 -> 15:00 - Code review            # 24-hour with arrow
2:30 PM - 3:00 PM: Client call          # Colon before task
9-10 AM Meeting with design             # Space before task
```

Supports `-`, `–`, `—`, `to`, `->`, and `→` as time separators.
Supports `-`, `:`, or just a space before the task name.

## Suggested Use

### Desktop: Split Screen
Run Craft Timeblock side-by-side with Craft Docs. Update your daily note in Craft, hit refresh in Timeblock to see changes.

### iPad/iPhone: Second Screen
Keep Timeblock open on a separate device next to your main screen. Add to Home Screen for an app-like experience:

1. Open in Safari
2. Tap Share button
3. Select "Add to Home Screen"

### Local File
Download `index.html` and open directly in your browser ([or visit the hosted version](https://eternalpriyan.github.io/craft-timeblock/)). No server required.

## Setup

### Prerequisites

You need the [Craft Imagine](https://developer.craft.do/) Daily Notes API running. This provides the API bridge between this viewer and your Craft documents.

### Quick Start

1. In the Imagine tab, go to **API for All Daily Notes**
2. Set **Access Mode** to **"Public"** (not "API Key")
3. Copy the URL
4. Open `index.html` in your browser ([or visit the hosted version](https://eternalpriyan.github.io/craft-timeblock/))
5. Paste your Craft Imagine API URL
6. Your daily note's timeblocks appear on the timeline

## Troubleshooting

If you encounter errors when entering your API URL, here's what they mean:

| Error | Cause | Solution |
|-------|-------|----------|
| **400** | You've pasted a Docs API key instead of the Daily Notes API | Go to the Imagine tab and copy the URL from **"API for All Daily Notes"**, not a single document's API |
| **401** | Access mode is set to "API Key" | Go to the Imagine tab → Daily Notes API → Set **Access Mode** to **"Public"** |
| **404** | Typo in the API URL | Double-check the URL for any missing or incorrect characters |

## Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `←` | Previous day |
| `→` | Next day |
| `Spacebar` | Refresh |
| `Backspace` | Delete Task/ Timeblock |
| `Click on Empty Space` | Create New Timeblock |
| `Drag Block` | Change Timings |

## Writing Timeblocks in Craft

**Pro tip:** Create an event note from your calendar in Craft. It automatically appears on your daily note and gets picked up as a timeblock!

Or write time ranges manually in any of these formats:

```markdown
## Schedule

10:00 AM - 11:30 AM - Deep work session
11:30 - 12 PM - Team standup
2 PM to 3:30 PM: Project planning
15:00 -> 16:00 - Code review

## Tasks (unscheduled)

- [ ] Review pull requests
- [ ] Update documentation
- [ ] Reply to emails
```

Timeblocks are automatically color-coded based on highlighting and coloring of your text in Craft Docs.
Any changes in the time blocking view get automatically updated in your Daily Notes. Click the refresh button to have daily note changes updated in the Time blocking view.

## Configuration

Open Settings (gear icon) to:
- Switch between dark and light themes
- Adjust timeline start and end hours
- Update your Craft Connect API URL

Settings are stored in localStorage.

## Technical Details

- **Single File**: Everything in one `index.html`
- **No Build Step**: Open directly in browser
- **No Dependencies**: Vanilla HTML, CSS, JavaScript
- **Responsive**: Works on desktop, tablet, and mobile
- **Theme**: Uses CSS custom properties with Claude Desktop's color palette

## Roadmap

Future enhancements being considered:

- More Fuzzy Timings
- **Move Timeblocks Between Days**: Drag a block to tomorrow or next week
- **Seven-Day View**: See your entire week at a glance
- **Time Tracking**: Log actual time spent vs planned
- **Pomodoro Integration**: Built-in focus timer

## Contributing

Issues and pull requests welcome! This is a personal project built for my own workflow, but happy to accept improvements that benefit others.

## License

MIT License - feel free to use, modify, and share.

---

Built with Craft Docs + Claude Code
