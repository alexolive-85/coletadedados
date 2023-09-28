import pandas as pd

df = pd.read_csv('bancomundial.csv')
user_ids = df['UserID'].tolist()
print(user_ids)
3788 3789 3790

import requests
import json

def get_user(id):
response = requests.get(f'{sdw2023_api_url}/users/{id}')
return response.json() if response.status_code == 200 else None

users = [user for id in user_ids if (user := get_user(id)) is not None]
print(json.dumps(users, indent=2))

{
"id": 3788,
"name": "Edward",
"account": {
"id": 4031,
"number": "3331-1",
"agency": "0001",
"balance": 0,
"limit": 1000
},
"card": {
"id": 3680,
"number": "**** **** **** 2211",
"limit": 2000
},
"features": [],
"news": []
}

{
"id": 3789,
"name": "Bradock",
"account": {
"id": 4032,
"number": "6677-5",
"agency": "0001",
"balance": 0,
"limit": 1000
},
"card": {
"id": 3681,
"number": "**** **** **** 4466",
"limit": 2000
},
"features": [],
"news": []
}

{
"id": 3790,
"name": "Max",
"account": {
"id": 4033,
"number": "8899-7",
"agency": "0001",
"balance": 0,
"limit": 1000
},
"card": {
"id": 3682,
"number": "**** **** **** 1155",
"limit": 2000
},
"features": [],
"news": []
}
