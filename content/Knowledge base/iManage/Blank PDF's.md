When saving PDF Documents into iManage ,the document contents are cleared and it becomes a blank document and is then saved into iManage as a blank documents: 

Steps to replicate issue

- Open PDF document  
- Click File - save to iManage  
- Save into iManage folder 
- Document is saved and is blank.

Fix: Issue resolved after amending the below registry key: 

HKEY_CURRENT_USER\SOFTWARE\Adobe\Acrobat Reader\DC\TrustManager 

DWORD: iProtectedView 

VALUE: 0