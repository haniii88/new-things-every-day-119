/* New Things Every Day — Da 119 */
/* Analyzes transaction records and creates a summary */

function dailyLog119() {
    const transactions = [
        { type: "income", amount: 1200 },
        { type: "expense", amount: 450 },
        { type: "income", amount: 800 },
        { type: "expense", amount: 320 },
        { type: "income", amount: 600 }
    ];

    const summary = transactions.reduce(
        (result, transaction) => {
            result[transaction.type] += transaction.amount;
            return result;
        },
        { income: 0, expense: 0 }
    );

    const balance = summary.income - summary.expense;

    console.log({
        day: 119,
        timestamp: new Date().toISOString(),
        income: summary.income,
        expense: summary.expense,
        balance
    });
}

dailyLog119();
