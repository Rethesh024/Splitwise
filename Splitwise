def main():
    no_transaction = int(input("Enter Number of Transactions: "))
    no_friends = int(input("Enter Number of friends: "))
    
    net = {}
    for _ in range(no_transaction):
        x, y, amount = input().split()
        amount = int(amount)
        if x not in net:
            net[x] = 0
        if y not in net:
            net[y] = 0
        net[x] -= amount
        net[y] += amount
    
    transactions = sorted([(person, amount) for person, amount in net.items() if amount != 0], key=lambda x: x[1])
    count = 0
    
    while transactions:
        low = transactions[0]
        high = transactions[-1]
        
        debit = low[1]
        debit_person = low[0]
        credit = high[1]
        credit_person = high[0]
        
        settled_amount = min(abs(debit), credit)
        debit += settled_amount
        credit -= settled_amount
        
        print(f"{debit_person} will pay {settled_amount} to {credit_person}")
        
        transactions.pop(0)
        transactions.pop(-1)
        
        if debit != 0:
            transactions.append((debit_person, debit))
        if credit != 0:
            transactions.append((credit_person, credit))
        
        transactions = sorted(transactions, key=lambda x: x[1])
        count += 1

if __name__ == "__main__":
    main()
