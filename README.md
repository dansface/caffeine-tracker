# caffeine-tracker

A client-side caffeine tracker that visualizes caffeine metabolism, estimates bedtime levels, and monitors caffeine load based on body weight. Includes customizable metabolism profiles, local browser storage, privacy controls, and a delete-my-data option.

## Overview

This is a static, browser-only application. The tracker is implemented in one HTML file with embedded CSS classes and JavaScript. It has no backend, build step, package manager, or application database.

The page loads Tailwind CSS, Chart.js, and the Chart.js date adapter from jsDelivr at runtime. See [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) for attribution and license information.

View the live site here: https://dansface.github.io/caffeine-tracker/

## Quick Start

### Prerequisites

- Git
- A modern web browser
- An optional local HTTP server for development

No Python, Node.js, or package installation is required to use the app. A local HTTP server is recommended for development, but it can be provided by any suitable static-file tool.

### Clone the repository

Replace the URL with the repository URL from GitHub:

```bash
git clone https://github.com/<OWNER>/<REPOSITORY>.git
cd <REPOSITORY>
```

### Run locally

Because the app loads external scripts and uses browser storage, serve the repository over HTTP rather than opening the file directly when possible.

The simplest option in VS Code is the **Live Server** extension: open the repository, right-click `index.html`, choose **Open with Live Server**, and visit the URL it provides.

If Python is installed, use one of these commands:

```bash
# macOS, Linux, or installations exposing the `python` command
python -m http.server 8000

# Windows installations exposing the `py` launcher
py -m http.server 8000
```

Then open <http://localhost:8000> in a browser.

You can also use any other static-file server you already have installed. Stop a terminal-based server with `Ctrl+C`.

## Development

The main application file is [index.html](index.html). The HTML, UI, chart configuration, calculations, event handlers, and local-storage logic all live there.

When changing the app:

1. Edit `index.html`.
2. Refresh the local browser page.
3. Test the tracker with and without saved browser data.
4. Check the responsive layout at desktop and mobile widths.
5. Review the browser console for errors and verify that the CDN libraries loaded.

Important behavior to test includes logging and deleting drinks, kg/lbs conversion, caffeine load normalization to `mg/kg`, bedtime projections, privacy and terms modals, and the Delete My Data confirmation flow.

## Browser Storage

The app stores tracker state in the browser using these local-storage keys:

- `caffeine_entries`
- `caffeine_weight_unit`
- `caffeine_weight_val`
- `caffeine_bedtime`
- `caffeine_metabolism`

There is no server-side persistence or account system. The in-app **Delete My Data** action removes these keys from the current browser. Data does not automatically sync between browsers or devices.

## Project Files

| File | Purpose |
| --- | --- |
| `index.html` | Complete application and GitHub Pages entrypoint |
| `LICENSE` | MIT License for this project |
| `TERMS.md` | User-facing terms and health disclaimer |
| `THIRD_PARTY_NOTICES.md` | Third-party library attribution and licenses |
| `README.md` | Project and developer documentation |

## Important Disclaimer

This project is provided for general informational and educational purposes only. The calculations are estimates and may not be accurate for every person. This tracker is not medical advice, a medical diagnosis, or a medical device. Do not use it to make decisions about your health, medication, caffeine intake, pregnancy, sleep, or treatment. Consult a qualified healthcare professional for personal guidance.

You use this project at your own risk. The software is provided "as is" without warranties. See [TERMS.md](TERMS.md) for the full terms and disclaimer.

## Privacy

Tracker data is stored in the browser using local storage and is not transmitted to an application server by this project. The page does load frontend libraries from jsDelivr; see [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md). The in-app Privacy Policy includes a **Delete My Data** control that removes this app's saved browser data.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE).

Third-party libraries are separately licensed. See [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) for attribution and license information.
