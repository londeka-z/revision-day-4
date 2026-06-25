# Gaming Score Tracker

## **Problem Statement:**

Create a **score tracking app** where players:
- **Add their gaming scores** (just a number)
- **View all scores** in a list
- **Filter scores** (show high/low scores)
- **Sort scores** (highest to lowest)
- **Analyze performance** with stats

### **No Objects. Just Arrays & Numbers.**

---

## **User Flow:**

```
User enters score: 85
↓
Click "Add Score"
↓
85 appears in list
↓
Stats update: "Total: 1, Average: 85, Best: 85, Worst: 85"
↓
User adds more scores: 92, 78, 105
↓
Can filter/sort/see stats
```

---

## **Starter HTML:**

```html
<!DOCTYPE html>
<html>
<head>
  <title>Gaming Score Tracker</title>
  <style>
    body {
      font-family: Arial;
      max-width: 500px;
      margin: 40px auto;
      padding: 20px;
      background: linear-gradient(135deg, #667eea, #764ba2);
      min-height: 100vh;
    }

    .container {
      background: white;
      padding: 30px;
      border-radius: 15px;
      box-shadow: 0 10px 40px rgba(0,0,0,0.3);
    }

    h1 {
      text-align: center;
      color: #333;
      margin-bottom: 30px;
    }

    .input-section {
      display: flex;
      gap: 10px;
      margin-bottom: 20px;
    }

    input {
      flex: 1;
      padding: 12px;
      border: 2px solid #ddd;
      border-radius: 5px;
      font-size: 16px;
    }

    button {
      padding: 12px 20px;
      background: #667eea;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      font-weight: bold;
      transition: background 0.3s;
    }

    button:hover {
      background: #764ba2;
    }

    button.danger {
      background: #e74c3c;
    }

    button.danger:hover {
      background: #c0392b;
    }

    .filter-section {
      display: flex;
      gap: 10px;
      margin: 20px 0;
      flex-wrap: wrap;
    }

    #scoresList {
      background: #f9f9f9;
      padding: 20px;
      border-radius: 8px;
      margin: 20px 0;
      min-height: 120px;
      max-height: 250px;
      overflow-y: auto;
    }

    .score-item {
      background: white;
      padding: 12px;
      margin: 8px 0;
      border-left: 4px solid #667eea;
      border-radius: 5px;
      font-size: 16px;
      font-weight: bold;
      color: #333;
    }

    .score-item.high {
      border-left-color: #28a745;
    }

    .score-item.low {
      border-left-color: #e74c3c;
    }

    .stats-section {
      background: #f0f0f0;
      padding: 20px;
      border-radius: 8px;
      margin-top: 20px;
    }

    .stats-section h3 {
      margin-top: 0;
      color: #333;
    }

    .stat-row {
      display: flex;
      justify-content: space-between;
      padding: 10px 0;
      border-bottom: 1px solid #ddd;
    }

    .stat-row:last-child {
      border-bottom: none;
    }

    .stat-label {
      font-weight: bold;
      color: #333;
    }

    .stat-value {
      color: #667eea;
      font-weight: bold;
      font-size: 18px;
    }

    .empty-message {
      text-align: center;
      color: #999;
      padding: 30px;
      font-style: italic;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>🎮 Gaming Score Tracker</h1>

    <!-- INPUT SECTION -->
    <div class="input-section">
      <input 
        type="number" 
        id="scoreInput" 
        placeholder="Enter your score (0-999)"
        min="0"
        max="999"
      >
      <button id="addBtn">Add Score</button>
      <button id="clearBtn" class="danger">Clear All</button>
    </div>

    <!-- FILTER SECTION -->
    <div class="filter-section">
      <button id="showAllBtn">Show All</button>
      <button id="aboveAvgBtn">Above Average</button>
      <button id="belowAvgBtn">Below Average</button>
      <button id="sortBtn">Sort High to Low</button>
    </div>

    <!-- SCORES LIST -->
    <div id="scoresList">
      <div class="empty-message">No scores yet. Add your first score! 🎯</div>
    </div>

    <!-- STATS -->
    <div class="stats-section">
      <h3>📊 Stats</h3>
      <div class="stat-row">
        <span class="stat-label">Total Scores:</span>
        <span class="stat-value" id="totalCount">0</span>
      </div>
      <div class="stat-row">
        <span class="stat-label">Average:</span>
        <span class="stat-value" id="avgScore">0</span>
      </div>
      <div class="stat-row">
        <span class="stat-label">Best Score:</span>
        <span class="stat-value" id="bestScore">-</span>
      </div>
      <div class="stat-row">
        <span class="stat-label">Worst Score:</span>
        <span class="stat-value" id="worstScore">-</span>
      </div>
    </div>
  </div>

  <script>
    let scores = [];
    let displayedScores = [];

    // YOUR CODE HERE

  </script>
</body>
</html>
```

---
## **Test Your Work:**

Add these scores in order: **85, 92, 78, 105, 88**

Then check:

- [ ] Total Scores: **5**
- [ ] Average: **89** (or 89.6 rounded)
- [ ] Best Score: **105**
- [ ] Worst Score: **78**
- [ ] Above Average shows: **92, 105** (2 scores)
- [ ] Below Average shows: **85, 78, 88** (3 scores)
- [ ] Sort High to Low shows: **105, 92, 88, 85, 78**
- [ ] Clear All resets everything

---

## **Tips:**

- Validate input: check if empty and if it's a number
- Use `.reduce()` with a starting value (0 for sum, first score for min/max)
- Keep `scores` unchanged - only change `displayedScores`
- Use `.forEach()` to build HTML strings
- Math.round() rounds decimals

---
