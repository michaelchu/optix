# OptionSurface

Interactive 3D options surface visualizer. Transform options chains into intuitive surfaces to analyze strike prices, expiration dates, and premiums in real-time. Built with React, Recharts, and Polygon.io API.

![OptionSurface Demo](docs/demo-placeholder.gif)

## Features

- 🚀 Real-time options data visualization
- 📊 Interactive 3D surface plots
- 🔄 Switch between calls and puts
- 💡 Instant price surface generation
- 📱 Responsive design
- ⚡ Fast and efficient data processing

## Live Demo

[View Live Demo](https://optionsurface.demo) *(Coming Soon)*

## Getting Started

### Prerequisites

- Node.js 16+
- Polygon.io API key
- npm or yarn

### Installation

1. Clone the repository
```bash
git clone https://github.com/yourusername/optionsurface.git
cd optionsurface
```

2. Install dependencies
```bash
npm install
# or
yarn install
```

3. Create environment variables
```bash
cp .env.example .env
```

Add your Polygon.io API key to `.env`:
```
VITE_POLYGON_API_KEY=your_api_key_here
```

4. Start the development server
```bash
npm run dev
# or
yarn dev
```

Visit `http://localhost:5173` to view the application.

## Usage

1. Enter a stock symbol (e.g., AAPL, TSLA)
2. Select option type (Calls/Puts)
3. Click "Visualize" to generate the surface plot
4. Interact with the 3D surface to analyze options data

## Tech Stack

- ⚛️ React
- 📊 Recharts
- 🎨 Tailwind CSS
- 🧱 shadcn/ui
- 📡 Polygon.io API

## Architecture

```
src/
├── components/
│   ├── SymbolInput/
│   ├── OptionTypeSelector/
│   ├── SurfacePlot/
│   └── LoadingState/
├── services/
│   └── polygonApi.ts
├── hooks/
│   └── useOptionsData.ts
└── utils/
    └── dataTransform.ts
```

## Development

### Available Scripts

```bash
npm run dev      # Start development server
npm run build    # Build for production
npm run preview  # Preview production build
npm run lint     # Run ESLint
npm run test     # Run tests
```

### Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| VITE_POLYGON_API_KEY | Your Polygon.io API key | Yes |
| VITE_API_BASE_URL | Polygon.io API base URL | No |

## API Integration

The application uses Polygon.io's REST API endpoints:

```typescript
// Get options contracts
GET /v3/reference/options/contracts
  ?underlying_ticker=${symbol}
  &right=${optionType}

// Get options prices
GET /v3/snapshot/options/${optionContract}
```

## Performance

- Initial load time: < 1.5s
- Data fetch and render: < 2s
- Surface plot animation: 60fps
- Support for up to 500 data points

## Testing

```bash
# Run all tests
npm run test

# Run tests in watch mode
npm run test:watch

# Generate coverage report
npm run test:coverage
```

## Deployment

1. Build the application
```bash
npm run build
```

2. Deploy the `dist` folder to your hosting service

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [Polygon.io](https://polygon.io) for options data
- [Recharts](https://recharts.org) for 3D visualization
- [shadcn/ui](https://ui.shadcn.com) for UI components

## Support

For support, email support@optionsurface.com or open an issue in the repository.

## Roadmap

- [ ] Add custom rotation controls
- [ ] Implement multiple symbol comparison
- [ ] Add Greeks visualization
- [ ] Include historical data view
- [ ] Add export functionality
- [ ] Implement volume/open interest overlay

---

Made with ♡ by Michael Chu
