# Electricity-Bill-Payment-Using-Python

class Customer:
    def __init__(self, name, customer_id, balance):
        self.name = name
        self.customer_id = customer_id
        self.balance = balance

    def display_balance(self):
        print("Current balance: $", self.balance)

    def make_payment(self, amount):
        if amount <= self.balance:
            self.balance -= amount
            print("Payment of $", amount, " successfully made.")
            self.display_balance()
        else:
            print("Insufficient balance. Payment failed.")


class ElectricityBill:
    def __init__(self, customer):
        self.customer = customer

    def generate_bill(self, units):
        bill_amount = units * 0.1  # Assuming the rate is $0.1 per unit
        print("Electricity Bill Amount: $", bill_amount)
        return bill_amount


def main():
    customer_name = input("Enter customer name: ")
    customer_id = input("Enter customer ID: ")
    customer_balance = float(input("Enter customer balance: "))

    customer = Customer(customer_name, customer_id, customer_balance)
    electricity_bill = ElectricityBill(customer)

    units_consumed = float(input("Enter units consumed: "))
    bill_amount = electricity_bill.generate_bill(units_consumed)

    print("Making payment...")
    customer.make_payment(bill_amount)


if __name__ == '__main__':
    main()
