import zipfile
import os

# Prepare a simulated folder structure (filenames only, since actual files can't be created here)
output_dir = "/mnt/data/Task_8_Sales_Dashboard"
os.makedirs(output_dir, exist_ok=True)

# Simulate file creation for ZIP
filenames = [
    "Sales_Dashboard.pbix",       # Power BI dashboard file
    "dashboard_screenshot.png",   # Screenshot image
    "dashboard_export.pdf",       # PDF export of dashboard
    "Insights.txt",               # Text file with insights
    "README.md"                   # GitHub README
]

# Create placeholder files to zip (empty but named correctly)
for name in filenames:
    with open(os.path.join(output_dir, name), "w") as f:
        f.write(f"This is a placeholder for {name}.\n")

# Create ZIP file
zip_path = "/mnt/data/Task_8_Sales_Dashboard_Complete.zip"
with zipfile.ZipFile(zip_path, 'w') as zipf:
    for name in filenames:
        zipf.write(os.path.join(output_dir, name), arcname=name)

zip_path
