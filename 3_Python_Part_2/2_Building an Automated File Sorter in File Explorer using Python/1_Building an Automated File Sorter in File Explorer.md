# Building an Automated File Sorter in File Explorer

```python
import os, shutil

path = r"C:/Users/aimegael.boudzoumou/Downloads/Bootcamp-Data-Analyst-Ressources/To_Dell/visuals/"

file_name = os.listdir(path)

folder_names = ['csv files', 'image files', 'text files']

for loop in range(0,3):
    if not os.path.exists(path + folder_names[loop]):
        #print(path + folder_names[loop])
        os.makedirs(path + folder_names[loop])

for file in file_name:
    if ".csv" in file and not os.path.exists(path + "csv files/" + file):
        shutil.move(path + file, path + "csv files/" + file)
    elif ".png" in file and not os.path.exists(path + "image files/" + file):
        shutil.move(path + file, path + "image files/" + file)
    elif ".txt" in file and not os.path.exists(path + "text files/" + file):
        shutil.move(path + file, path + "text files/" + file)

```
