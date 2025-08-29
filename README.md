# 🌐 Glance Dashboard

A **self-hosted personal dashboard** powered by [Glance](https://github.com/glanceapp/glance).  
This project lets you organize bookmarks, news feeds, weather, stocks, homelab status, and more—  
all on **three cleanly organized pages**:  

- 🏠 **Home:** Tech news, dev blogs, weather, Reddit, Twitch, YouTube  
- 📈 **Markets:** Stocks, crypto, financial news, and market widgets  
- 🚀 **Startpage:** Homelab overview, quick bookmarks, and tools

The dashboard is deployed using **Docker Compose** for easy setup, with **Cloudflare Tunnel** integration for secure remote access.

---

## 📂 Repository Structure

```plaintext
glance/
├── docker-compose.yml   # Docker Compose config for Glance + Cloudflare tunnel
├── config/
│   ├── glance.yml       # Startpage layout and widgets
│   ├── home.yml         # Home page layout and widgets
│   └── markets.yml      # Markets/finance dashboard config
├── assets/
│   └── user.css         # Custom styling and theme tweaks
└── .gitkeep             # Keeps empty dirs in version control
```

---

## ✨ Features

* 🔗 **Centralized Startpage** for bookmarks and homelab links
* 📰 **Dynamic News and RSS Feeds** for tech, Reddit, and YouTube
* 💹 **Markets Page** for stocks, crypto, and finance tracking
* 🌤️ **Weather Widgets** with location-based forecasts
* 🎨 **Custom Theming** via `assets/user.css`
* 🐳 **Containerized Setup** with Docker Compose
* ☁️ **Optional Cloudflare Tunnel** for remote, secure access
* ⚡ **Single-File Configs** for easy editing and backup

---

## 🚀 Getting Started

Follow these steps to set up and run the Glance dashboard:

### 1. Clone the Repository

```bash
git clone git@gitlab.com:patel5d2/glance.git
cd glance
```

---

### 2. Configure Dashboard Pages

All customization happens in the `config/` directory:

* **glance.yml** – Main Startpage with bookmarks and tools  
* **home.yml** – Home dashboard with news, Reddit, weather  
* **markets.yml** – Finance & markets-focused dashboard  

Each YAML file is organized into sections (columns, widgets, feeds) so you can easily edit bookmarks, RSS sources, or services.

---

### 3. (Optional) Set Environment Variables

If you want to use **Cloudflare Tunnel** for secure remote access, create a `.env` file:

```env
TUNNEL_TOKEN=<YOUR-CLOUDFLARE-TOKEN>
```

This will allow `cloudflared` to authenticate and expose your dashboard securely over HTTPS without opening ports.

---

### 4. Start with Docker Compose

Run the following command to spin up your dashboard:

```bash
docker-compose up -d
```

Once running, your dashboard will be accessible at:

```
http://localhost:8080
```

If Cloudflare is enabled, check logs for your public URL:

```bash
docker logs cloudflared
```

---

## 🛠 Customization

### 🔧 Themes and Styles

* Modify `assets/user.css` to fully customize the look and feel (colors, fonts, layout tweaks).
* YAML configuration lets you rearrange widgets, rename sections, and add new data sources easily.

---

### 🧩 Widgets You Can Add

Glance supports a wide range of widgets. Examples include:

* Weather, Clock, and Calendar
* Stocks, Crypto, and Finance charts
* RSS feeds for any blog or news source
* Reddit & YouTube integrations
* Twitch streams
* Homelab monitoring

---

### 📱 Mobile-Friendly

The dashboard is **responsive**, meaning it adapts well to desktop and mobile screens.

---

## ☁️ Remote Access with Cloudflare Tunnel

For secure remote access:

1. Sign up for a free [Cloudflare account](https://www.cloudflare.com/).  
2. Create a tunnel token in Cloudflare.  
3. Add the token to `.env`:

   ```env
   TUNNEL_TOKEN=<YOUR-TOKEN>
   ```
4. Start the services:

   ```bash
   docker-compose up -d
   ```

You’ll receive a unique Cloudflare URL to access your dashboard securely over HTTPS.

---

## 🖼️ Screenshots

Here’s a preview of the dashboard layout (replace with your actual screenshots):

| Startpage                                      | Markets                                    | Home                                 |
| ---------------------------------------------- | ------------------------------------------ | ------------------------------------ |
| ![Startpage](assets/screenshots/startpage.png) | ![Markets](assets/screenshots/markets.png) | ![Home](assets/screenshots/home.png) |

---

## 📦 Tech Stack

| Component                                         | Purpose                                         |
| ------------------------------------------------- | ----------------------------------------------- |
| **[Glance](https://github.com/glanceapp/glance)** | Dashboard engine and widget system              |
| **Docker Compose**                                | Simple container orchestration for services     |
| **Cloudflare Tunnel**                             | Secure, firewall-free remote access             |
| **YAML Configs**                                  | Easy configuration of bookmarks, feeds, widgets |
| **Custom CSS**                                    | Full visual customization                       |

---

## 🔐 Security Notes

* No API keys or sensitive data are committed to Git.  
* Use a `.env` file for all secrets and tokens.  
* Cloudflare Tunnel adds an extra layer of security.  

---

## 🧩 Roadmap

* [ ] Add Docker image build automation (GitLab CI/CD)  
* [ ] Dark/Light mode toggle in `user.css`  
* [ ] More finance & homelab widgets  
* [ ] Config template examples for easier setup  

---

## 🤝 Contributing

Contributions are welcome!

1. Fork this repository  
2. Create a feature branch (`git checkout -b feature/new-widget`)  
3. Commit changes (`git commit -m "Add new widget"`)  
4. Push and open a Merge Request  

---

## 📝 License

This project is licensed under the [MIT License](LICENSE).

---

### 💡 Inspiration

Glance is designed to be **simple, self-hosted, and highly customizable**—perfect for homelabbers, developers, and productivity enthusiasts who want **everything in one view** without clutter.

