## excel读写
```
from xlutils.copy import copy
import xlrd
import xlwt
# 写
rb = xlrd.open_workbook(excel_path)
wb = copy(rb)
ws = wb.get_sheet(sheet_name)
ws.write(row, col, text)
os.remove(excel_path)
wb.save(excel_path) # 只能保存为xls格式
# 读
rb = xlrd.open_workbook(excel_path)
for rs in rb.sheets():
    rows = rs.nrows
    cols = rs.ncols
    for i in range(rows):
        for j in range(cols):
            print rs.cell(i,j).value
```
