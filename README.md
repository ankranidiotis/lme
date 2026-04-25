# LME Lead Price Tracker

A lightweight, interactive dashboard for tracking London Metal Exchange (LME) lead prices over time. Displays historical daily and monthly average prices with an intuitive, theme-aware interface.

## Features

- **Interactive Time-Series Chart**: Visualize lead price trends with daily prices and monthly averages
- **Zoom & Pan Controls**: Scroll to zoom, drag to pan, double-click to reset the view
- **Monthly Summary Cards**: Quick reference for average prices by month
- **Dark/Light Mode**: Toggle between dark and light themes with persistent UI state
- **Responsive Design**: Works seamlessly on desktop and mobile devices
- **Real-Time Updates**: Data is automatically updated via n8n workflow

## Demo

The application displays:
- Daily lead prices as a blue line chart with area fill
- Monthly average prices as an orange dashed overlay
- Summary statistics cards for each month
- Last data update timestamp

## Tech Stack

- **Frontend**: Vanilla HTML, CSS, and JavaScript
- **Charts**: [Chart.js](https://www.chartjs.org/) with time-series adapter and zoom plugin
- **Data Format**: JSON with timestamp and price data
- **Styling**: CSS variables for theming, responsive grid layout

## Project Structure

```
.
├── index.html          # Single-page application
├── data.json          # Lead price data (updated via n8n)
├── fav.ico           # Favicon
└── README.md         # This file
```

## Data Format

The `data.json` file contains:

```json
{
  "updated": "2026-04-24T05:01:09.263Z",
  "data": [
    {
      "timestamp": "2026-01-02T00:00:00.000Z",
      "lmelead": 1676.86
    }
  ]
}
```

- `updated`: ISO timestamp of when the data was last refreshed
- `data`: Array of price entries
  - `timestamp`: ISO date when the price was recorded
  - `lmelead`: Lead price in EUR/tonne (cash contract, offer price)

## Data Source

Price data is sourced from [lme.com](https://www.lme.com) and automatically updated via n8n workflow.

## Getting Started

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd lme
   ```

2. **Open in browser**
   - Simply open `index.html` in your web browser
   - No build process or dependencies required

3. **Local development**
   - Serve with any HTTP server (Python, Node.js, etc.)
   - Example: `python -m http.server 8000`

## Usage

- **Zoom**: Scroll your mouse wheel on the chart
- **Pan**: Click and drag the chart horizontally
- **Reset**: Double-click the chart to reset zoom and pan
- **Toggle Theme**: Click the "Light mode" / "Dark mode" button in the header

## Browser Support

Works on modern browsers that support:
- ES6 JavaScript
- CSS custom properties (variables)
- Chart.js and related libraries

## Customization

The application uses CSS variables for theming. To customize colors, edit the CSS variables in the `<style>` section of `index.html`:

```css
:root {
  --bg: #f5f5f5;
  --card-bg: #fff;
  --text: #222;
  --text-muted: #666;
  --grid: #f0f0f0;
  --shadow: rgba(0,0,0,0.08);
}

[data-theme="dark"] {
  --bg: #0f172a;
  --card-bg: #1e293b;
  --text: #f1f5f9;
  /* ... etc ... */
}
```

## Updates

Data is automatically refreshed via n8n workflow. The last update timestamp is displayed at the bottom of the chart.

## License

© 2026 Nassos Kranidiotis. Data sourced from [lme.com](https://www.lme.com).

## Author

Designed by [Nassos Kranidiotis](https://nassoskranidiotis.com)
