# Progressive Web Application
My first progressive web app

_For this proyect, trying to follow and orderly sequence, I ask Copilot, because i have anything else to ask, in order to complete the onboarding tutorial. Therefore, Next is an slightly adapted version from the one provided by Github Copilot._

Creating a Progressive Web App (PWA) from scratch involves several steps, and one have multiple options for hosting it—including using Azure.

## Guide to create a PWA on Azure:

### Creating a Progressive Web App (PWA) From Scratch

#### 1. Set Up The Project
- Create a new directory for the app.
- Initialize a package manager (npm, yarn) if using JS frameworks.
- Write the HTML, CSS, and JavaScript files.

#### 2. Key PWA Requirements
- **Manifest file (`manifest.json`)**: Describes your app (name, icons, theme color, etc.).
- **Service Worker**: JavaScript file that controls caching and offline functionality.
- **HTTPS**: PWAs require secure hosting (HTTPS).

#### 3. Example: Minimal Structure
```plaintext
/public
  index.html
  manifest.json
  sw.js (Service Worker)
/src
  app.js
```
#### 4. Add Manifest to HTML
```html
<link rel="manifest" href="/manifest.json">
```
#### 5. Register Service Worker
```javascript
// in app.js or index.js
if ('serviceWorker' in navigator) {
  navigator.serviceWorker.register('/sw.js')
    .then(reg => console.log('SW registered!', reg))
    .catch(err => console.error('SW registration failed:', err));
}
```
#### 6. Test PWA Features
- Use Chrome DevTools: "Lighthouse" audit for PWA.
- Add to Home Screen on mobile browser.
---
### **Options to Host The PWA**

#### **A. Azure Hosting Options**
Here are common Azure services for hosting web apps:

1. **Azure Static Web Apps**
   - Best for static sites (HTML, CSS, JS, frameworks like React, Vue, Angular).
   - Auto-deployment from GitHub.
   - Free SSL, global CDN, custom domains.

2. **Azure App Service**
   - Host dynamic web apps (Node.js, Python, .NET, etc.).
   - Supports custom domains, scaling, and SSL.

3. **Azure Blob Storage**
   - Host static websites directly from storage.
   - Simple, cost-effective for static files.

#### B. Other Hosting Options
- GitHub Pages (free, good for static sites)
- Vercel, Netlify (popular for JAMstack, static PWAs)
- AWS S3 + CloudFront
- Google Firebase Hosting

---

### Quick Example: Deploying a PWA to Azure Static Web Apps

1. Push the code to GitHub.
2. Go to Azure Portal > Create Resource > Static Web App.
3. Connect a GitHub repo.
4. Configure build settings (e.g., `/public` folder).
5. Deploy! Azure handles HTTPS, CDN, and updates automatically.

---

### Summary
- Build: Manifest + Service Worker + HTTPS.
- Host: Azure Static Web Apps (recommended for PWAs), Azure App Service, Azure Blob Storage, or other platforms.
- Azure is a great option—especially Static Web Apps for PWAs!
