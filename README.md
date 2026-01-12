# Spedify V2 🛒✨

AI-powered price comparison platform that intelligently scrapes and compares product prices across multiple e-commerce platforms.

## 🌟 Features

- 🤖 **AI-Powered Search**: Leverages Groq AI for intelligent product matching
- 💰 **Real-time Price Comparison**: Instant price checks across Amazon, Flipkart, and more
- 📊 **Price History Tracking**: Visual charts showing price trends over time  
- ❤️ **Favorites & Alerts**: Save products and get notified of price drops
- 🔍 **Smart Search**: Natural language search with AI understanding
- 📱 **Responsive Design**: Works seamlessly across all devices

## 🛠️ Tech Stack

### Backend
- **FastAPI** - High-performance Python web framework
- **MongoDB** - NoSQL database for storing product data
- **Groq AI API** - Advanced AI for product analysis
- **BeautifulSoup4** - Web scraping and parsing
- **Pydantic** - Data validation and settings management

### Frontend
- **React 18** - Modern UI library with hooks
- **TypeScript** - Type-safe JavaScript development
- **Tailwind CSS** - Utility-first CSS framework
- **Vite** - Lightning-fast build tool
- **Chart.js** - Interactive price history charts

## 🚀 Getting Started

### Prerequisites
- Python 3.8+
- Node.js 16+
- MongoDB (local or Atlas)
- Groq API Key ([Get one here](https://console.groq.com))

### Backend Setup

```bash
cd spedify-v2/backend

# Create virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Set up environment variables
cp .env.example .env
# Edit .env with your API keys and database URL

# Start the server
uvicorn main:app --reload
```

### Frontend Setup

```bash
cd spedify-v2/frontend

# Install dependencies
npm install

# Set up environment variables
cp .env.example .env.local
# Edit .env.local with your API URLs

# Start development server
npm run dev
```

## 📁 Project Structure

```
spedify-v2/
├── backend/
│   ├── main.py              # FastAPI application entry point
│   ├── models.py            # Database models
│   ├── auth_*.py            # Authentication modules  
│   ├── favorites_routes.py  # User favorites API
│   ├── scraper.py           # Price scraping logic
│   └── requirements.txt     # Python dependencies
├── frontend/
│   ├── src/
│   │   ├── components/      # React components
│   │   ├── services/        # API services
│   │   ├── types/          # TypeScript types
│   │   └── utils/          # Helper functions
│   └── package.json        # Node.js dependencies
└── scraper/
    ├── ollama_scraper.py   # AI-powered scraping
    └── price_history_extractor.py
```

## 🔧 Environment Variables

### Backend (.env)
```env
GROQ_API_KEY=your_groq_api_key_here
MONGODB_URL=mongodb://localhost:27017/spedify
SECRET_KEY=your_secret_key_here
```

### Frontend (.env.local)  
```env
VITE_API_URL=http://localhost:8000/api
VITE_WS_URL=ws://localhost:8000/ws
```

## 📡 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/api/search/{query}` | Search products across platforms |
| `GET` | `/api/product/analyze?url=...` | Analyze specific product URL |
| `POST` | `/api/favorites` | Add product to favorites |
| `GET` | `/api/favorites` | Get user's favorite products |
| `GET` | `/api/stats` | Platform statistics and metrics |
| `GET` | `/api/price-history/{product_id}` | Get price history for product |

## 🧪 Usage Examples

### Search Products
```python
import requests

response = requests.get("http://localhost:8000/api/search/iphone 15")
products = response.json()
```

### Analyze Product URL
```python
url = "https://amazon.com/product/123"
response = requests.get(f"http://localhost:8000/api/product/analyze?url={url}")
analysis = response.json()
```

## 🎯 Supported Platforms

- ✅ **Amazon India** - Full product details and pricing
- ✅ **Flipkart** - Complete catalog with offers
- ✅ **Snapdeal** - Wide product range
- 🔄 **More platforms coming soon...**

## 📊 Screenshots

_Add screenshots of your application here_

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Groq](https://groq.com) for AI capabilities
- [FastAPI](https://fastapi.tiangolo.com) for the amazing web framework
- [React](https://reactjs.org) for the frontend library
- [Tailwind CSS](https://tailwindcss.com) for styling

---

Made with ❤️ by [Your Name]

⭐ Star this repo if you find it helpful!