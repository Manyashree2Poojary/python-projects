# Simple Stock Tracker

# Hardcoded stock prices
stock_prices = {
    "AAPL": 180,
    "TSLA": 250,
    "GOOGL": 150,
    "MSFT": 420,
    "AMZN": 190
}

total_investment = 0

print("===== Stock Tracker =====")
print("Available stocks:", ", ".join(stock_prices.keys()))

while True:
    stock = input("\nEnter stock name (or 'done' to finish): ").upper()

    if stock == "DONE":
        break

    if stock in stock_prices:
        quantity = int(input("Enter quantity: "))

        investment = stock_prices[stock] * quantity
        total_investment += investment

        print("Stock price:", stock_prices[stock])
        print("Investment:", investment)

    else:
        print("Sorry, stock not available.")

print("\n==========================")
print("Total Investment: $", total_investment)
print("==========================")

# Save result to a text file
with open("stock_investment.txt", "w") as file:
    file.write("Stock Investment Report\n")
    file.write("=======================\n")
    file.write(f"Total Investment: ${total_investment}\n")

print("Result saved to stock_investment.txt")
