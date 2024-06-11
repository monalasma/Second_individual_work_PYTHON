# Second_individual_work_PYTHON
```python
import datetime

class Client:
  number_of_clients = 0
  
  def __init__(self, name):
    self.name = name
    self.transactions = []
    Client.number_of_clients += 1
  def add_transaction(self, transaction):
    self.transactions.append(transaction)

class Item:
  def __init__(self, name, price):
    self.name = name
    self.price = price

class Transaction:
  def __init__(self, client, items):
    self.client = client
    self.item = items
    self.time_stamp = datetime.datetime.now()
    self.total_amount = sum(item.price for item in items)
    client.add_transaction(self)

client1 = Client("Rudzupuķe")
client2 = Client("Margrieta")
client3 = Client("Āboliņš")

item1 = Item("Chair", 100)
item2 = Item("Table", 250)
item3 = Item("TV", 780)

transaction1 = Transaction(client1, [item2, item3])
transaction2 = Transaction(client2, [item2])
transaction3 = Transaction(client3, [item1, item2, item3])

clients = [client1, client2, client3]

print(f'Number of clients today: {Client.number_of_clients}')

for client in clients:
  print(f'Client: {client.name}')
  for transaction in client.transactions:
    print(f'Transactions made: {transaction.time_stamp}. Total price: {transaction.total_amount}')
    for item in transaction.item:
      print(f'Items bought: {item.name}. Item price is: {item.price}')
```
