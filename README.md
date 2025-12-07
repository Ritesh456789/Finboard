# Finance Dashboard

A customizable, real-time financial monitoring dashboard built with Next.js, TypeScript, and Tailwind CSS. It enables you to connect to financial APIs and build widgets that visualize market data in a personalized way.

---

## 🌟 Features

### 1. Flexible Widget System
- Add new widgets using any financial API  
- Remove widgets anytime  
- Rearrange layout using drag-and-drop  
- Configure each widget individually  

### 2. Multiple Widget Views
- **Card View:** Compact metric display  
- **Table View:** Sortable and searchable data tables  
- **Chart View:** Line charts for visual insights  

### 3. Smart API Integration
- Map fields from API responses  
- Built-in API test functionality  
- Adjustable refresh intervals  
- Automatic caching to reduce requests  

### 4. Modern User Interface
- Light and Dark theme support  
- Fully responsive layout  
- Clear loading states and error messages  
- Clean, modern design  

### 5. Persistent Dashboard State
- Saves data using localStorage  
- Automatically restores layout on refresh  
- Configuration persists across sessions  

---

## 🛠 Technologies Used

- **Next.js 14 (App Router)**  
- **TypeScript**  
- **Tailwind CSS**  
- **Zustand** (state management)  
- **Recharts** (charts)  
- **@dnd-kit** (drag & drop)  
- **Axios**  
- **Lucide React** (icons)  

---

## 🚀 Getting Started

### Prerequisites
- Node.js 18 or higher  
- Financial API key (optional for live data)  

### Installation

```bash
git clone <repository-url>
cd finboard
```

Install dependencies:

```bash
npm install
# or yarn install / pnpm install
```

Start the development server:

```bash
npm run dev
```

Open: http://localhost:3000

---

## 📌 How to Use

### Adding a Widget
1. Click the **“+ Add Widget”** button  
2. Provide a widget name  
3. Enter an API endpoint  
4. Test the API  
5. Select display type (Card/Table/Chart)  
6. Choose fields  
7. Set refresh interval  
8. Add the widget  

### Managing Widgets
- Refresh → Click refresh icon  
- Delete → Click trash icon  
- Rearrange → Drag widget handle  

---

## 🧩 Supported APIs

Works with **any JSON-based REST API**.

Examples:
- Coinbase  
- Alpha Vantage  
- Finnhub  
- Custom financial APIs  

### API Requirements
- Must return JSON  
- Must support GET requests  
- Use proxy/API routes to avoid CORS issues  

---

## 📁 Project Structure

```
finboard/
├── app/
│   ├── layout.tsx
│   ├── page.tsx
│   └── globals.css
├── components/
│   ├── Dashboard.tsx
│   ├── AddWidgetModal.tsx
│   ├── ThemeToggle.tsx
│   └── widgets/
│       ├── WidgetCard.tsx
│       ├── WidgetTable.tsx
│       └── WidgetChart.tsx
├── store/
│   └── dashboardStore.ts
├── types/
│   └── widget.ts
├── utils/
│   ├── api.ts
│   └── storage.ts
└── package.json
```

---

## 🔐 API Key Management

Create `.env.local`:

```
NEXT_PUBLIC_API_KEY=your_key_here
```

For production, use Next.js API routes to securely handle sensitive keys.

---

## 🛠 Handling CORS

If the API blocks browser requests, create a proxy:

```ts
// app/api/proxy/route.ts
export async function GET(request: Request) {
  const { searchParams } = new URL(request.url);
  const apiUrl = searchParams.get('url');

  const response = await fetch(apiUrl!);
  const data = await response.json();

  return Response.json(data);
}
```

---

## 📅 Roadmap
- Real-time updates via WebSockets  
- Dashboard templates  
- Import/export configurations  
- More chart types (bar, candlestick, etc.)  
- Widget sharing and collaboration  

---

## 🤝 Contributing

Contributions are welcome! Submit a pull request or open an issue.

---

## 📄 License

MIT License

