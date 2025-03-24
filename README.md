# 🔍 Find Customer Referee

## 📌 Problem Description
We have a table called `Customer` that holds information about customers and who referred them. It looks like this:

| Column Name | Type    |
|-------------|---------|
| `id`        | `int`   |
| `name`      | `varchar` |
| `referee_id`| `int`   |

### 🧾 Explanation of columns:
- **`id`**: A unique number for each customer.
- **`name`**: The customer's name.
- **`referee_id`**: The ID of the customer who referred this person (can be `null` if no one referred them).

---

## 🎯 Goal
We want to **find the names of customers** who were **NOT** referred by the customer with `id = 2`.

---

## 🔍 Example
Imagine the table looks like this:

| `id` | `name` | `referee_id` |
|------|--------|--------------|
| 1    | Will   | null         |
| 2    | Jane   | null         |
| 3    | Alex   | 2            |
| 4    | Bill   | null         |
| 5    | Zack   | 1            |
| 6    | Mark   | 2            |

✅ Expected output:

| `name` |
|--------|
| Will   |
| Jane   |
| Bill   |
| Zack   |

---

## 🛠️ SQL Query Solution
Here’s a simple SQL query to solve this:

```sql
select name from customer where referee_id !=2

```

### 💡 Explanation of the query:
1. **`SELECT name`**: This picks the customer names from the table.
2. **`FROM Customer`**: This tells SQL we’re working with the `Customer` table.
3. **`WHERE referee_id IS NULL OR referee_id != 2`**:
   - **`IS NULL`** checks for customers with no referee.
   - **`referee_id != 2`** filters out any customer referred by `id = 2`.

✅ **Result:** We get the names of customers who weren’t referred by customer `2`.

---

✨ **Now you can handle customer referrals like a SQL champ!** 🌟

