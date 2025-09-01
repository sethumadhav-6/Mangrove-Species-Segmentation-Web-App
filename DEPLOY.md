# 🚀 Deployment Guide

Quick setup instructions for hosting your Mangrove Species Segmentation App.

## 📋 Repository Structure
```
mangrove-segmentation/
├── index.html              # Main application file
├── README.md               # Project documentation
├── _config.yml             # GitHub Pages configuration
├── package.json            # Project metadata
├── DEPLOY.md              # This deployment guide
└── LICENSE                # MIT license file
```

## 🏗️ Deployment Options

### 1. GitHub Pages (Recommended)
**⏱️ Setup Time: 2 minutes**

```bash
# Step 1: Create repository
git clone https://github.com/your-username/mangrove-segmentation.git
cd mangrove-segmentation

# Step 2: Push to GitHub
git remote add origin https://github.com/your-username/mangrove-segmentation.git
git push -u origin main

# Step 3: Enable GitHub Pages
# Go to: Settings → Pages → Deploy from branch → main → Save
```

**🔗 Your app will be live at:** `https://your-username.github.io/mangrove-segmentation/`

### 2. Netlify
**⏱️ Setup Time: 1 minute**

1. **Drag & Drop**: Go to [netlify.com](https://netlify.com) and drag your project folder
2. **GitHub Integration**: Connect your GitHub repository
3. **Custom Domain**: Optional - add your own domain

### 3. Vercel
**⏱️ Setup Time: 30 seconds**

```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel

# Follow prompts and get instant deployment URL
```

### 4. Local Development
**⏱️ Setup Time: 10 seconds**

```bash
# Option A: Python (if Python installed)
python -m http.server 8000

# Option B: Node.js
npx serve .

# Option C: PHP (if PHP installed)
php -S localhost:8000

# Open: http://localhost:8000
```

## ⚙️ Configuration Steps

### 1. Update Repository Links
Edit these files with your GitHub username:
- `README.md`: Update demo links
- `package.json`: Update repository URLs
- `_config.yml`: Update base URLs

### 2. Customize App Settings
In `index.html`, you can modify:
- **Species List** (line 85): Add/remove mangrove species
- **Colors** (CSS): Change theme colors
- **Confidence Threshold**: Default detection sensitivity
- **Analysis Intervals**: Real-time processing frequency

### 3. Add Google Analytics (Optional)
In `_config.yml`:
```yaml
google_analytics: UA-XXXXXXXX-X
```

## 🔧 Advanced Setup

### Custom Domain with GitHub Pages
1. **Add CNAME file**:
```bash
echo "your-domain.com" > CNAME
git add CNAME && git commit -m "Add custom domain" && git push
```

2. **Configure DNS**: Point your domain to GitHub Pages IPs:
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

### HTTPS Setup
GitHub Pages provides free SSL certificates. For custom domains:
1. Wait 24 hours after DNS configuration
2. Go to Settings → Pages
3. Check "Enforce HTTPS"

## 🚁 DJI Integration Setup

### Workflow Integration
1. **DJI Fly App**: Export videos to device
2. **File Transfer**: Use USB/AirDrop to computer
3. **Web Upload**: Use app's file upload feature

### Recommended Drone Settings
```
Video Resolution: 4K/30fps
Gimbal Mode: Lock
Color Mode: Normal (for accurate species detection)
Histogram: Enable (for optimal exposure)
```

## 📊 Performance Optimization

### Image Processing
- **Optimal Size**: 1920x1080 for balance of speed/accuracy
- **Format**: JPG for photos, MP4 for video
- **Compression**: Minimal to preserve species details

### Browser Optimization
```javascript
// In index.html, you can adjust these values:
const ANALYSIS_INTERVAL = 2000; // ms between live analyses
const MAX_IMAGE_SIZE = 1920; // Max width for processing
const CONFIDENCE_THRESHOLD = 0.5; // Default detection threshold
```

## 🔍 Testing Your Deployment

### Quick Test Checklist
- [ ] App loads without errors
- [ ] Camera access works (HTTPS required)
- [ ] File upload accepts images/videos
- [ ] Species detection shows results
- [ ] Segmentation overlay displays
- [ ] Export functionality works
- [ ] Mobile responsive design

### Test URLs
```bash
# Local testing
http://localhost:8000

# GitHub Pages
https://your-username.github.io/repository-name/

# Custom domain
https://your-domain.com
```

## 🐛 Troubleshooting

### Common Issues

**❌ App won't load**
- Check file paths in index.html
- Ensure HTTPS for camera access
- Verify TensorFlow.js CDN link

**❌ Camera not working**
- Must use HTTPS (not HTTP)
- Check browser permissions
- Try different browsers

**❌ Slow performance**
- Reduce image size
- Lower analysis frequency
- Use desktop browser

**❌ GitHub Pages not updating**
- Check GitHub Actions tab
- Verify main branch is selected
- Clear browser cache

### Debug Commands
```bash
# Check if files are accessible
curl -I https://your-username.github.io/repository-name/index.html

# Validate HTML
npx html-validate index.html

# Test locally with HTTPS
npx serve . --ssl-cert

# Check GitHub Pages status
gh api repos/:owner/:repo/pages
```

## 📈 Performance Monitoring

### Analytics Setup
Add to `index.html` before `</head>`:
```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_TRACKING_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_TRACKING_ID');
</script>
```

### User Experience Metrics
Monitor these in browser dev tools:
- **First Contentful Paint**: < 2 seconds
- **Time to Interactive**: < 3 seconds
- **Camera Access Time**: < 1 second
- **Analysis Processing**: < 2 seconds per frame

## 🔄 Updates & Maintenance

### Regular Updates
```bash
# Update dependencies
npm update

# Update TensorFlow.js version
# Check: https://github.com/tensorflow/tfjs/releases

# Test on different devices/browsers monthly
```

### Backup Strategy
- **Code**: GitHub repository (automatic)
- **Models**: Store in separate repository/CDN
- **Documentation**: Keep local copies

## 📞 Support Checklist

Before requesting help, verify:
- [ ] Using supported browser (Chrome 80+, Firefox 75+, Safari 13+)
- [ ] HTTPS enabled (required for camera)
- [ ] JavaScript enabled
- [ ] No browser console errors
- [ ] Tested with different image formats
- [ ] Checked GitHub repository settings

## 🎯 Next Steps

After successful deployment:
1. **Test thoroughly** with real drone footage
2. **Share with community** for feedback
3. **Document species accuracy** in your region
4. **Consider contributing** improvements back to project
5. **Train custom models** for local mangrove species

---

**🎉 Congratulations!** Your mangrove species segmentation app is now deployed and ready to help with conservation efforts.

*Happy drone flying and species identification!* 🌿🚁
