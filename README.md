# 📊 EMEA India Team Performance Dashboard - FY2027

Interactive ranking dashboard for India EMEA Tableau Technical Support engineers with **real-time data** from Salesforce OrgCS.

## 🌐 Live Dashboards

| Dashboard | URL | Description |
|-----------|-----|-------------|
| **EMEA Live Dashboard** | [View Live](https://dgunani-sudo.github.io/team-performance-dashboard-fy2027/emea_live.html) | Real-time rankings from OrgCS |
| **India EMEA (Historical)** | [View Historical](https://dgunani-sudo.github.io/team-performance-dashboard-fy2027/) | Static snapshot from June 15, 2026 |

## ✨ Features

### 📈 Interactive Rankings
- **28 Engineers** across 3 manager teams
- **Real-time sorting** by any metric
- **Live search** and filtering
- **Manager filters**: Kiran Vijay, Akanksha Saxena, Prakash Venugopal
- **Title/Level filters**: TSE, Senior TSE, Principal SE

### 📊 Metrics Tracked

| Metric | Description | Formula |
|--------|-------------|---------|
| **Closed Cases** | Total cases closed in FY2027 | COUNT(Closed) |
| **Throughput/week** | Cases closed per week | **Closed ÷ 7** |
| **CSAT** | Customer Satisfaction (case surveys only) | AVG(Rating 1-5) |
| **TTR** | Time to Resolution | AVG(Days to close) |
| **SLA%** | Initial response SLA compliance | % Met |
| **Reopen%** | Case reopen rate | % Reopened |
| **Surveys** | Survey count (case only, chat excluded) | COUNT |

### 🎯 Key Features

- ✅ **Throughput Formula**: Closures ÷ 7 (cases per week)
- ✅ **CSAT Source**: Case surveys only (chat surveys excluded)
- ✅ **Multi-level filtering**: By manager and title
- ✅ **Data Source**: Salesforce OrgCS Dashboard `01ZHx000000kpvZMAQ`
- ✅ **Period**: FY2027 YTD (Feb 1, 2026 onwards)

## 🔄 Auto-Update (Real-time Sync)

The dashboard automatically updates from Salesforce every 6 hours via GitHub Actions.

### Setup Instructions

To enable real-time updates, add these repository secrets:

1. Go to **Settings** → **Secrets and variables** → **Actions**
2. Add the following secrets:
   - `SF_USERNAME`: Your Salesforce username (e.g., user@orgcs.com)
   - `SF_PASSWORD`: Your Salesforce password + security token
   - `SF_INSTANCE_URL`: https://orgcs.lightning.force.com

### Manual Update

Trigger a manual update:
```bash
# Via GitHub UI
Actions → Update EMEA Dashboard Data → Run workflow

# Or via gh CLI
gh workflow run update-dashboard.yml
```

### Local Update

```bash
# Install dependencies (first time only)
npm install jsforce

# Set environment variables
export SF_USERNAME="your-username@orgcs.com"
export SF_PASSWORD="your-password-and-token"
export SF_INSTANCE_URL="https://orgcs.lightning.force.com"

# Run update script
node scripts/update_data.js
```

## 📅 Data Coverage

- **Fiscal Year**: FY2027 (Feb 2026 - Jan 2027)
- **YTD Period**: Feb 1, 2026 - Present
- **Update Frequency**: Every 6 hours (automated)
- **Last Updated**: Check badge in dashboard header

## 📂 Repository Structure

```
team-performance-dashboard-fy2027/
├── index.html                # Historical dashboard (June 15, 2026)
├── emea_live.html            # Live dashboard (auto-updated)
├── data/
│   └── emea_data_*.json      # Daily data snapshots
├── scripts/
│   └── update_data.js        # Auto-update script
├── .github/workflows/
│   └── update-dashboard.yml  # GitHub Actions workflow
└── README.md                 # This file
```

## 🚀 Usage

### View the Dashboard
Simply open any modern web browser and navigate to the live URL:
```
https://dgunani-sudo.github.io/team-performance-dashboard-fy2027/emea_live.html
```

### Filter by Manager
- 🌏 All Teams
- 🔵 Kiran Vijay (12 engineers)
- 🟠 Akanksha Saxena (13 engineers)
- 🟣 Prakash Venugopal (3 Principal SEs)

### Filter by Title
- 👥 All Levels (28 engineers)
- TSE - Technical Support Engineer
- Senior TSE - Senior Technical Support Engineer
- Principal SE - Principal Technical Support Engineer

### Search
Use the search box to quickly find any engineer by name.

## 📊 Data Source

**Salesforce OrgCS Dashboard**
- Dashboard ID: `01ZHx000000kpvZMAQ`
- Name: EMEA Dashboard
- Folder: EMEA Team Dashboards
- Type: SpecifiedUser

## 🛠️ Technical Details

### Stack
- **Frontend**: Vanilla JavaScript + Chart.js
- **Data**: JSON (extracted from Salesforce via OrgCS MCP)
- **Hosting**: GitHub Pages
- **Auto-update**: GitHub Actions + Salesforce API

### Performance
- ⚡ Fully client-side (no backend required)
- 📦 Self-contained (22KB HTML file)
- 🚀 Works offline after initial load
- 🔄 Auto-refreshes data every 6 hours

## 🤝 Contributing

To update the dashboard logic or styling:

1. Edit `emea_live.html`
2. Test locally by opening in a browser
3. Commit and push to `main` branch
4. GitHub Pages will auto-deploy in ~1-2 minutes

## 📝 License

Internal tool for Salesforce Tableau Support team use.

---

**🤖 Generated with [Claude Code](https://claude.com/claude-code)**
Last updated: 2026-07-10
