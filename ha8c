#!/usr/local/bin/python3.7

import gspread
from datetime import datetime
from oauth2client.service_account import ServiceAccountCredentials
import sys

args = sys.argv[1:]

def add(row):
    rows = len(sheet.get_all_records()) + 2
    sheet.insert_row(row, rows)

scope = ['https://spreadsheets.google.com/feeds', 'https://www.googleapis.com/auth/drive']
creds = ServiceAccountCredentials.from_json_keyfile_name("secret.json", scope)
client = gspread.authorize(creds)
sheet = client.open("Ha8c").sheet1

today = datetime.strftime(datetime.now(), "%d.%m.%Y")

if len(args) == 3:
    row = [today, args[0], args[1], args[2], "", "NS"]
    add(row)

elif len(args) == 4:
    row = [today, args[0], args[1], args[2], args[3], "NS"]
    add(row)

elif len(args) < 3:
    print("Not enough arguments!")

else:
    print("Too many arguments!")


