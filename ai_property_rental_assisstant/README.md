# 🏠 AI Property Rental Assistant

> Smart property recommendations powered by AI for UAE rentals

An intelligent Python tool that scrapes UAE property listings and leverages OpenAI's GPT-4o-mini to deliver personalized rental recommendations tailored to your specific needs.

## ✨ Features

- 🔍 **Smart Scraping** - Automatically extracts property listings from UAE rental websites
- 🤖 **AI-Powered Analysis** - Uses GPT-4o-mini to match properties with your requirements
- 💡 **Intelligent Recommendations** - Get ranked suggestions with detailed reasoning
- 🎯 **Customizable Search** - Filter by location, budget, bedrooms, and more
- 💰 **Cost-Effective** - Uses GPT-4o-mini (~$0.001 per request)

## 🚀 Quick Start

### Prerequisites

- Python 3.7 or higher
- OpenAI API key ([Get yours here](https://platform.openai.com/api-keys))

### Installation

1. **Clone or download this repository**

2. **Install dependencies:**
```bash
   pip install requests beautifulsoup4 openai python-dotenv
```

3. **Configure your API key:**
   
   Create a `.env` file in the project root:
```env
   OPENAI_API_KEY=sk-proj-your_api_key_here
```

4. **Run the script:**
```bash
   python rental_assistant.py
```

## 📖 Usage

### Basic Example

The script comes pre-configured for Dubai student housing. Simply run it:
```bash
python rental_assistant.py
```

### Customize Your Search

**Change location:**
```python
website_url = "https://www.bayut.com/to-rent/property/dubai/al-barsha"
```

**Update your requirements:**
```python
user_needs = """
I'm a young professional looking for:
- 1-bedroom apartment
- Budget: Under AED 50,000/year
- Location: Al Qusais or nearby
- Must have parking
"""
```

### Example Use Cases
```python
# For students
user_needs = "Student seeking shared accommodation under AED 25,000/year"

# For families
user_needs = "Family of 4 needing 3-bedroom villa with garden, budget AED 100,000/year"

# For professionals
user_needs = "Young professional wanting modern studio near Metro, max AED 45,000/year"
```

## 📊 Sample Output
```
==================================================
RENTAL RECOMMENDATIONS
==================================================

✅ Recommended Properties (3 matches found)

1. Modern 1BHK with Balcony
   💰 Rent: AED 48,000/year
   🛏️ Bedrooms: 1 | 🚿 Bathrooms: 1 | 📐 Area: 650 sqft
   📍 Location: Al Qusais 2, Dubai
   ⭐ Why this matches: Within budget, includes parking, close to Metro

2. Spacious Studio Apartment
   💰 Rent: AED 42,000/year
   ...
```

## 🛠️ How It Works
```
┌─────────────────┐
│  Web Scraping   │  Fetches property listings from Bayut
└────────┬────────┘
         │
┌────────▼────────┐
│ Text Extraction │  Cleans HTML and extracts key details
└────────┬────────┘
         │
┌────────▼────────┐
│  AI Analysis    │  GPT-4o-mini processes requirements
└────────┬────────┘
         │
┌────────▼────────┐
│ Recommendations │  Ranked results with explanations
└─────────────────┘
```

## ⚙️ Configuration

### Supported Websites
- ✅ Bayut.com
- ✅ Property Finder (modify URL)
- ✅ Dubizzle (modify URL)

### Customizing AI Behavior

Modify the `system_prompt` in the script to change AI behavior:
```python
system_prompt = """
You are a UAE property expert specializing in:
- Luxury properties
- Family-friendly neighborhoods
- Investment opportunities
[Add your custom instructions here]
"""
```

## 💡 Advanced Features

### Create `requirements.txt`
```txt
requests>=2.28.0
beautifulsoup4>=4.11.0
openai>=1.0.0
python-dotenv>=1.0.0
```

Install with:
```bash
pip install -r requirements.txt
```

### Rate Limiting (for multiple searches)
```python
import time

for search in searches:
    get_recommendations(search)
    time.sleep(2)  # Wait 2 seconds between requests
```

## 🚨 Troubleshooting

| Issue | Solution |
|-------|----------|
| `No API key found` | Ensure `.env` file exists with correct API key |
| `Error fetching website` | Check internet connection or try different URL |
| `No recommendations` | Adjust budget/requirements or try different location |
| `Rate limit exceeded` | Wait 60 seconds (free tier limit: 3 requests/min) |

## 💰 Cost Information

- **Model:** GPT-4o-mini
- **Cost:** ~$0.001 per request (extremely affordable)
- **Free tier:** 3 requests per minute
- **Monitor usage:** [OpenAI Usage Dashboard](https://platform.openai.com/usage)

## 🎯 Future Improvements

- [ ] Interactive CLI with user input
- [ ] Support multiple websites simultaneously
- [ ] Price history tracking
- [ ] Email alerts for new listings
- [ ] Web interface with Flask/Streamlit
- [ ] Image analysis for property photos
- [ ] Neighborhood insights (schools, transport, amenities)

## ⚠️ Important Notes

- **Educational Purpose:** This tool is for learning and personal use
- **Verify Information:** Always confirm property details with agents/landlords
- **Respect ToS:** Follow website terms of service and scraping policies
- **Rate Limiting:** Be respectful - don't overwhelm servers with requests

## 📝 License

This project is open source and available under the MIT License.

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Report bugs
- Suggest new features
- Submit pull requests

## 📧 Support

Having issues? 
1. Check the [Troubleshooting](#-troubleshooting) section
2. Ensure your `.env` file is properly configured
3. Verify your internet connection
4. Check your OpenAI API key is valid

---

**Made with ❤️ for UAE property hunters** | Powered by OpenAI GPT-4o-mini