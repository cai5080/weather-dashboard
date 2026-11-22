# Weather Comfort Atlas

This static dashboard uses `dashboard-data.json` beside `index.html`. Keep both files together when sharing or hosting the dashboard. Open it through an HTTP server rather than directly as a `file://` URL so the browser can load the data file.

## Refresh the dashboard data

From the workspace root, run:

```powershell
& 'C:/Users/120470/AppData/Local/miniconda3/python.exe' 'Project Files/calculate_hci_scores.py'
& 'C:/Users/120470/AppData/Local/miniconda3/python.exe' 'Project Files/build_hci_dashboard_data.py'
```

The first command rebuilds the scored CSV from `Source/weatherAUS.csv`. The second refreshes this folder's dashboard data file.

## Run locally

```powershell
& 'C:/Users/120470/AppData/Local/miniconda3/python.exe' -m http.server 8765 --bind 127.0.0.1 --directory 'Output/hci_dashboard'
```

Then open `http://127.0.0.1:8765/`. To share with others, publish the complete `hci_dashboard` folder on an approved internal static host or web server.