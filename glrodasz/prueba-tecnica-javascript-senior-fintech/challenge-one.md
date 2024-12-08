# Filtrar transacciones

**Crear una funcionalidad que dado un lista de transacciones, una categoría, un rango de fechas, devuelva la suma de todas las transacciones de esa categoría.**

```js
const transactions = [
  {
    id: 123,
    sourceAccount: "my_account",
    targetAccount: "coffee_shop",
    amount: -30,
    category: "eating_out",
    time: "2018-03-12T12:34:00Z",
  },
  {
    id: 124,
    sourceAccount: "my_account",
    targetAccount: "coffee_shop",
    amount: -50,
    category: "eating_out",
    time: "2018-03-12T11:34:00Z",
  },
  {
    id: 127,
    sourceAccount: "my_account",
    targetAccount: "restaurant",
    amount: -100,
    category: "eating_out",
    time: "2019-03-23T11:51:00Z",
  },
  {
    id: 125,
    sourceAccount: "my_work",
    targetAccount: "my_account",
    amount: 1000,
    category: "salary",
    time: "2019-02-12T12:34:00Z",
  },
  {
    id: 126,
    sourceAccount: "my_work",
    targetAccount: "my_account",
    amount: 1100,
    category: "salary",
    time: "2019-05-12T12:34:00Z",
  },
  {
    id: 129,
    sourceAccount: "my_account",
    targetAccount: "my_work",
    amount: -100,
    category: "salary",
    time: "2019-05-12T12:35:00Z",
  },
  {
    id: 128,
    sourceAccount: "my_account",
    targetAccount: "supermarket",
    amount: -10,
    category: "groceries",
    time: "2019-01-23T12:51:00Z",
  },
];
```

### Datos de ejemplo de la prueba

**¿Cuál es el < total > de dinero gastado en la < category > desde < fechaComienzo > hasta < fechaFinal >?**

```
getBalance(transactions, 'eating_out', '2019-01-01', '2019-12-31') => -100
```

<hr>

<details>
  <summary>
    <h3>Solution - Guillermo</h3>
  </summary>

```js
const filterByCategory =
  ({ category }) =>
  (transaction) =>
    transaction?.category === category;

const TWENTY_THREE_HOURS_IN_MS = 23 * 60 * 60 * 1000;
const FIFTY_NINE_MINUTES_IN_MS = 59 * 60 * 1000;
const FIFTY_NINE_SECONDS_IN_MS = 59 * 1000;

const filterByDate = ({ startDate, endDate }) => {
  const startTime = new Date(startDate).getTime();
  const endTime =
    new Date(endDate).getTime() +
    TWENTY_THREE_HOURS_IN_MS +
    FIFTY_NINE_MINUTES_IN_MS +
    FIFTY_NINE_SECONDS_IN_MS;

  return (transaction) => {
    const transactionTime = new Date(transaction?.time).getTime();

    return transactionTime >= startTime && transactionTime <= endTime;
  };
};

const sumAmount = (totalBalance, transaction) =>
  totalBalance + transaction?.amount ?? 0;

const getBalanceByCategoryAndRangeDate = (
  transactions,
  category,
  startDate,
  endDate
) =>
  Array.isArray(transactions)
    ? transactions
        .filter(filterByCategory({ category }))
        .filter(filterByDate({ startDate, endDate }))
        .reduce(sumAmount, 0)
    : 0;

console.log(
  getBalanceByCategoryAndRangeDate(
    transactions,
    "salary",
    "2019-01-01",
    "2023-12-31"
  )
);
```

</details>

<hr>

<details>
  <summary>
    <h3>Solution - MrRedu</h3>
  </summary>

```ts
interface Transaction {
  id: number;
  sourceAccount: string;
  targetAccount: string;
  amount: number;
  category: string;
  time: string;
}

const filterByCategory = (
  transactions: Transaction[],
  category: string
): Transaction[] =>
  transactions?.filter(
    (transaction) => transaction.category === category && transaction
  );
const filterByTime = (
  transactions: Transaction[],
  startDate: string,
  endDate: string
): Transaction[] => {
  // if (!Array.isArray(transactions)) throw new Error('El primer parámetro debe ser un Array');

  const startTime = new Date(startDate);
  const endTime = new Date(endDate);

  if (isNaN(startTime.getTime()))
    throw new Error("Formato de startDate incorrecto");
  if (isNaN(endTime.getTime()))
    throw new Error("Formato de endDate incorrecto");

  return transactions.filter(
    (transaction) =>
      new Date(transaction.time) < endTime &&
      new Date(transaction.time) > startTime
  );
};
const sumAmount = (transactions: Transaction[]): number => {
  let totalBalance = 0;
  for (let transaction of transactions) {
    totalBalance += transaction.amount ?? 0;
  }
  return totalBalance;
};

const getBalance = (
  transactions: Transaction[],
  category: string,
  startDate: string,
  endDate: string
): number => {
  const transactionsByCategory = filterByCategory(transactions, category);
  const transactionsByTime = filterByTime(
    transactionsByCategory,
    startDate,
    endDate
  );
  return sumAmount(transactionsByTime);
};

console.log(getBalance(transactions, 'salary', '2019-01-01', '2019-12-31'))             // 2000
console.log(getBalance(transactions, 'eating_out', '2018-01-01', '2018-12-31'))         // -80
console.log(getBalance(transactions, 'groceries', '2018-01-01', '2018-12-31'))          // 0
console.log(getBalance(transactions, 'groceries', '2019-01-01', '2019-12-31'))          // -10
console.log(getBalance(transactions, 'salary', '2019-05-12 08:33', '2019-05-12 08:35')) // 1100
console.log(getBalance(transactions, 'salary', '2019-05-12 08:33', '2019-05-12 08:36')) // 1000
```

</details>
