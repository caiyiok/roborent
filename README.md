[README.md](https://github.com/user-attachments/files/27469209/README.md)
# RoboRent — Humanoid Robot Rental Website

A single-file, zero-dependency website for humanoid robot rentals.

## 📁 File Structure
```
roborent/
└── index.html        ← The entire website (frontend + admin)
```

## 🚀 Deployment Options

### Option 1: Vercel (Recommended — Free, 5 minutes)
1. Go to https://vercel.com and sign up with GitHub
2. Click "Add New Project" → "Deploy without Git" → drag & drop this folder
3. Click Deploy → your site is live at `yourproject.vercel.app`
4. For a custom domain: Project Settings → Domains → Add your domain

### Option 2: Netlify (Free)
1. Go to https://netlify.com
2. Drag & drop the `roborent` folder onto the dashboard
3. Live in seconds at `random-name.netlify.app`
4. Custom domain: Site Settings → Domain Management → Add custom domain

### Option 3: Alibaba Cloud / Tencent Cloud OSS (China)
1. Create an OSS/COS bucket, enable "Static Website Hosting"
2. Upload `index.html`
3. Set index document to `index.html`
4. Bind your domain via CDN

### Option 4: Traditional VPS (Nginx)
```bash
# Install Nginx
sudo apt update && sudo apt install nginx -y

# Upload index.html
scp index.html user@your-server-ip:/var/www/html/

# Nginx config (/etc/nginx/sites-available/roborent)
server {
    listen 80;
    server_name yourdomain.com www.yourdomain.com;
    root /var/www/html;
    index index.html;
}

# Enable SSL with Let's Encrypt
sudo apt install certbot python3-certbot-nginx
sudo certbot --nginx -d yourdomain.com
```

## 🌐 Domain Registration

### Recommended Registrars
| Registrar | Best For | URL |
|-----------|----------|-----|
| Namecheap | International, cheapest .com | namecheap.com |
| Cloudflare Registrar | At-cost pricing + free CDN | cloudflare.com |
| 阿里云 (Aliyun) | China ICP filing | aliyun.com |
| 腾讯云 (Tencent Cloud) | China ICP filing | cloud.tencent.com |

### Suggested Domain Names
- `roborent.com` / `roborent.io`
- `robot-rental.com`
- `humanoidrent.com`
- `rentarobot.io`

> **China ICP Filing Note**: If you plan to serve users in mainland China from a China-hosted server, you must obtain an ICP license (备案). This takes 7–20 business days. International hosting (HK, Singapore, US) does not require ICP filing.

## ⚙️ Admin Panel
Access via the "Admin Panel" button in the top navigation.

Features:
- Dashboard with key metrics
- Add / edit / deactivate products (prices, specs, descriptions, badges)
- Manage brand descriptions
- View and manage customer inquiries

> **Note**: Data is stored in-memory (resets on page reload). To persist data, integrate a backend (Firebase, Supabase, or a REST API).

## 🔧 Customization
All product data is in the `appData` object in the `<script>` section of `index.html`.
Edit directly or use the Admin Panel in the browser.
