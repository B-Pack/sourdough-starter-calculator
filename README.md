# 🍞 Sourdough Starter Calculator

A simple, mobile-friendly calculator for planning sourdough starter feedings.

This calculator helps determine how much starter, flour, and water are needed to achieve a desired starter yield based on your feeding ratio.

Designed to be easy to use on phones, tablets, and computers, with no account, installation, or downloads required.

---

## Features

✅ Calculate feedings based on your existing starter amount

✅ Calculate feedings based on a desired feeding ratio

✅ Advanced custom calculations

✅ Automatic buffer calculation

✅ Mobile-friendly design

✅ Dark mode support

✅ 100% free and open source

---

## How the Calculator Works

The calculator assumes a starter feeding ratio of:

```text
Starter : Water : Flour
    1   :   A   :   A
```

Examples:

```text
1 : 1 : 1
1 : 2 : 2
1 : 3 : 3
1 : 5 : 5
```

A higher feeding ratio means more food is provided to a smaller amount of starter.

---

# Calculator Modes

## Initial Starter Mode

Use this mode when you know:

- How much starter you currently have
- How much starter you want to end up with

Enter:

```text
Initial Starter (X)
Required Starter Yield (RSY)
```

The calculator will determine:

- Feeding ratio required
- Water to add
- Flour to add
- Total starter yield

### Example

Input:

```text
Starter: 40g
Required Yield: 500g
```

Output:

```text
Ratio: 1 : 5.75 : 5.75

Starter: 40g
Water: 230g
Flour: 230g
```

---

## Feed Ratio Mode

Use this mode when you know:

- The feeding ratio you want
- The amount of starter you need

Enter:

```text
Feed Ratio
Required Starter Yield
```

The calculator will determine:

- Starting starter amount
- Water required
- Flour required

### Example

Input:

```text
Ratio: 1 : 3 : 3
Yield: 500g
```

Output:

```text
Starter: 71.4g
Water: 214.3g
Flour: 214.3g
```

---

## Custom Mode

Use this mode when you want full control.

Enter:

```text
Starter Amount
Feed Ratio
Required Yield
```

The calculator will calculate all remaining values.

This mode is useful for experimenting with different feeding schedules and starter sizes.

---

# Buffer Calculation

A buffer is automatically added to help ensure enough starter remains after handling losses, sticking to containers, or future feedings.

The calculator automatically uses:

```text
3.5% of required yield
OR
30g minimum
```

whichever is larger.

You may manually enter your own buffer value if desired.

---

# Formula Used

For a ratio of:

```text
1 : A : A
```

The total starter yield is:

```text
Total Yield = Starter × (1 + 2A)
```

Where:

- Starter = existing starter
- A = feeding ratio
- Water = A × Starter
- Flour = A × Starter

---

# Privacy

This calculator:

- Does not collect data
- Does not require login
- Does not use cookies
- Does not store personal information
- Runs entirely in your web browser

---

# License

This project is provided free to use, modify, and share for personal and educational purposes.

Happy baking! 🍞
