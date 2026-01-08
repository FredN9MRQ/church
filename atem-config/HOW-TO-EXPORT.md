# How to Export ATEM Configuration Files

## From ATEM Software Control

Follow these steps to save your switcher configuration for backup and remote access:

### 1. Save Switcher Setup

1. Open **ATEM Software Control** on this Windows PC
2. Connect to your 1 M/E Production Switcher 4K (via Ethernet or USB)
3. Go to **File** → **Save Switcher Setup**
4. Navigate to: `C:\Users\tbc_s\AI\church\atem-config\`
5. Name the file with a descriptive name and date, e.g., `church-switcher-setup-2026-01-07.xml`
6. Click **Save**

This saves:
- Input configurations and labels
- Auxiliary output routing
- Downstream keyer (DSK) settings
- Transition settings
- Color generator values

### 2. Save Startup State (Optional)

If you've configured a specific startup state:

1. In ATEM Software Control, set up the switcher to your desired startup state
2. Go to **File** → **Save Startup State to Switcher**
3. This saves the state directly to the switcher's memory

You can also export this state:
1. **File** → **Export Startup State**
2. Save to `C:\Users\tbc_s\AI\church\atem-config\`
3. Name it, e.g., `church-startup-state-2026-01-07.xml`

### 3. Export Macros (If Configured)

If you've created macros (see MACRO-GUIDE.md):

1. Each macro can be saved individually from the Macros panel
2. Save to `C:\Users\tbc_s\AI\church\atem-config\macros\` folder
3. Name descriptively, e.g., `macro-pre-service-setup.xml`

### 4. Commit to GitHub

After saving configuration files:

```bash
cd /c/Users/tbc_s/AI/church
git add atem-config/
git commit -m "Update ATEM configuration files - [date/description]"
git push
```

## To Restore Configuration

1. Download the configuration file from GitHub
2. Open ATEM Software Control
3. Connect to the switcher
4. Go to **File** → **Restore Switcher Setup**
5. Select the downloaded XML file
6. Confirm the restore operation

## Recommended Backup Schedule

- **Weekly**: After any significant configuration changes
- **Before events**: Prior to special services or events
- **After updates**: After ATEM software or firmware updates
- **Monthly**: Regular backup on first Sunday of month

## Notes

- Configuration files are typically saved as `.xml` files
- Keep different versions with dates for change tracking
- Test restored configurations before live services
- Document any manual settings not captured in exports (physical connections, network settings, etc.)
