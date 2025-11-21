# SolArk Dashboard Examples

These dashboard configurations are automatically downloaded when you install the SolArk Cloud integration via HACS.

## Location

After installation, these files are located at:
```
/config/custom_components/solark/dashboards/
```

## Available Dashboards

### 1. solark_flow.yaml
Full-featured power flow dashboard with:
- Real-time power flow indicators
- Battery status with dynamic icons
- 24-hour historical charts
- Energy production statistics

**Requires:**
- Mushroom Cards (install from HACS)
- ApexCharts Card (install from HACS)

### 2. solark_dashboard.yaml
Basic dashboard with essential monitoring cards.

## How to Use These Dashboards

### Method 1: Reference in configuration.yaml (Recommended)

Since the files are already on your system, simply reference them in your configuration:

1. Edit `/config/configuration.yaml` and add:

```yaml
lovelace:
  mode: storage
  dashboards:
    solark-power-flow:
      mode: yaml
      title: SolArk Power Flow
      icon: mdi:solar-power
      show_in_sidebar: true
      filename: custom_components/solark/dashboards/solark_flow.yaml
```

2. Restart Home Assistant
3. Find "SolArk Power Flow" in your sidebar

### Method 2: Copy to /config/dashboards/ (Alternative)

If you prefer to keep dashboards separate from the integration:

```bash
# Create dashboards directory
mkdir -p /config/dashboards

# Copy the dashboard files
cp /config/custom_components/solark/dashboards/solark_flow.yaml /config/dashboards/
```

Then reference as:
```yaml
lovelace:
  mode: storage
  dashboards:
    solark-power-flow:
      mode: yaml
      title: SolArk Power Flow
      icon: mdi:solar-power
      show_in_sidebar: true
      filename: dashboards/solark_flow.yaml
```

### Method 3: UI Dashboard (No configuration.yaml needed)

1. Go to Settings → Dashboards → + ADD DASHBOARD
2. Name it "SolArk Power Flow"
3. Click ⋮ → Edit Dashboard → ⋮ → Raw configuration editor
4. Copy the contents from `/config/custom_components/solark/dashboards/solark_flow.yaml`
5. Paste and save

## Important Notes

- These files are installed with the integration and will be updated when you update the integration
- If you modify these files, your changes will be overwritten on integration updates
- To customize: Copy to `/config/dashboards/` first, then modify your copy
- Remember to install Mushroom Cards and ApexCharts Card from HACS before using the dashboards

## Troubleshooting

### Dashboard not found
**Issue:** "Config for lovelace not found"
**Solution:** Check the file path in your configuration.yaml. The path should be relative to `/config/`

### Dashboard shows blank
**Issue:** Dashboard loads but shows no cards
**Solution:** 
1. Install Mushroom Cards from HACS
2. Install ApexCharts Card from HACS
3. Restart Home Assistant
4. Clear browser cache (Ctrl+Shift+R)

### Sensors not showing
**Issue:** Dashboard shows but sensors are unavailable
**Solution:** 
1. Verify integration is installed and configured
2. Check sensors exist: Developer Tools → States → Search "solark"
3. Wait 30-60 seconds for first data update

## Customization

To customize these dashboards:
1. Copy the file to `/config/dashboards/` (Method 2 above)
2. Modify your copy
3. Reference your copy in configuration.yaml
4. Your changes won't be overwritten on updates

## Need Help?

- See main README.md for complete documentation
- Check DASHBOARD_INSTALLATION.md for detailed setup instructions
- Open an issue on GitHub if you encounter problems

---

**Tip:** Method 1 (reference from custom_components) is easiest because the files are already there!
