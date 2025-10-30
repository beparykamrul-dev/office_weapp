import zipfile
import os

# Define folder structure
structure = {
    'webapp/frontend': ['App.js', 'Dashboard.js', 'Admin.js', 'Employee.js', 'index.js'],
    'webapp/backend/routes': ['auth.js', 'tasks.js', 'accounts.js', 'employees.js'],
    'webapp/backend/models': ['User.js', 'Task.js', 'Account.js'],
    'config': ['.env.example', 'README_Deployment.md'],
    'sample_data': ['admin_user.json', 'sample_employees.json', 'sample_tasks.json', 'sample_accounts.json']
}

zip_name = "Family_Time_Network_Full_Deployment_Local.zip"

with zipfile.ZipFile(zip_name, 'w') as zipf:
    for folder, files in structure.items():
        for file in files:
            filepath = os.path.join(folder, file)
            zipf.writestr(filepath, f'// {file} placeholder content')

print(f"ZIP created: {zip_name}")
