# pandas Read Excel Multiple Sheets
sheet_name param also takes a list of sheet names as values that can be used to read multiple sheets into pandas DataFrame. Not that while reading multiple sheets it returns a Dict of DataFrame. The key in Dict is a sheet name and the value would be DataFrame.
import pandas as pd

# Read excel file with sheet name
dict_df = pd.read_excel('c:/apps/courses_schedule.xlsx', 
                   sheet_name=['Technologies','Schedule'])
Since we are reading two sheets from excel, this function returns Dict of DataFrame. You can get the DataFrames from Dict as follows.


# Get DataFrame from Dict
technologies_df = dict_df .get('Technologies')
schedule_df = df.get('Schedule')

# Print DataFrame's
print(technologies_df)
print(schedule_df)
