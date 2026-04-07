---
tags:
  - gamedev
  - gambling
---

![[Maya's golden riches await.png]]
Here’s a **condensed, step-by-step Markdown guide** tailored for **Godot**, with minimal fluff and more actionable structure.

---

# 🎰 Slot Machine (3x5) – Step-by-Step Guide (Godot)  
  
---  
  
## 1. Scene Setup  
  
Create main scene:  

SlotMachine (Node2D)  
├── Reels (Node2D)  
│   ├── Reel1  
│   ├── Reel2  
│   ├── Reel3  
│   ├── Reel4  
│   ├── Reel5  
├── UI (CanvasLayer)  
│   ├── SpinButton  
│   ├── BetDisplay  
│   ├── BalanceDisplay  
│   ├── WinDisplay

---

## 2. Game State

var state = "idle" # idle, spinning, result, win, bonus

---

## 3. Reel + Symbol Data

var symbols = ["A","K","Q","scarab","wild","cat"]  
  
var weights = {  
  "cat": 1,  
  "wild": 2,  
  "scarab": 4,  
  "A": 10,  
  "K": 10,  
  "Q": 10  
}

---

## 4. Generate Spin Result

func spin():  
  result = generate_result()  
  state = "spinning"  
  start_spin_animation()

func generate_result():  
  var res = []  
  
  for i in range(5):  
    var reel = []  
    for j in range(3):  
      reel.append(get_weighted_symbol())  
    res.append(reel)  
  
  return res

func get_weighted_symbol():  
  var pool = []  
  
  for key in weights:  
    for i in range(weights[key]):  
      pool.append(key)  
  
  return pool[randi() % pool.size()]

---

## 5. Animate Reels

func start_spin_animation():  
  stop_reel(0, 0.5)  
  stop_reel(1, 0.7)  
  stop_reel(2, 0.9)  
  stop_reel(3, 1.1)  
  stop_reel(4, 1.3)

func stop_reel(index, delay):  
  await get_tree().create_timer(delay).timeout  
  reels[index].set_result(result[index])

---

## 6. Paylines

var paylines = [  
  [1,1,1,1,1],  
  [0,0,0,0,0],  
  [2,2,2,2,2],  
  [0,1,2,1,0],  
  [2,1,0,1,2]  
]

---

## 7. Calculate Win

var payout = {  
  "cat": 100,  
  "wild": 50,  
  "scarab": 20,  
  "A": 10,  
  "K": 10,  
  "Q": 10  
}

func calculate_win():  
  var total = 0  
  
  for line in paylines:  
    var first = result[0][line[0]]  
    var count = 1  
  
    for i in range(1,5):  
      if result[i][line[i]] == first:  
        count += 1  
      else:  
        break  
  
    if count >= 3:  
      total += payout[first] * bet  
  
  return total

---

## 8. Features

### Scatter → Bonus

func check_scatter():  
  var count = 0  
  
  for reel in result:  
    for symbol in reel:  
      if symbol == "scatter":  
        count += 1  
  
  if count >= 3:  
    start_bonus()

---

### Random Feature (Golden Touch)

func golden_touch():  
  if randf() < 0.1:  
    var i = randi() % 5  
    result[i] = ["wild","wild","wild"]

---

## 9. Game Flow

func _on_spin_pressed():  
  if state != "idle":  
    return  
  
  spin()

func on_spin_finished():  
  golden_touch()  
  check_scatter()  
  
  var win = calculate_win()  
  show_win(win)  
  
  state = "idle"

---

## 10. Required Graphic Elements

### 🎰 Core Slot

- Reel background (frame)
- 6–10 symbol icons:
    - Cat girl (premium)
    - Wild
    - Scatter
    - Scarab
    - Egyptian icons (Ankh, Eye, etc.)
    - Card symbols (A, K, Q)

---

### 🐱 Character

- Idle pose
- Spin reaction
- Win animation
- Bonus animation

---

### ✨ Effects

- Reel spin blur
- Win glow (symbols)
- Coin particles
- Golden glow effect
- Highlight paylines

---

### 🎮 UI

- Spin button (idle + pressed)
- Autoplay button
- Bet control (+ / -)
- Balance text
- Win text
- Bonus screen overlay

---

### 🏛️ Background

- Luxor/Egypt environment
- Pyramids / gold interior
- Light particles / atmosphere

---

## 11. Build Order

1. Scene + UI layout  
2. Spin button → triggers spin()  
3. Generate result  
4. Animate reels  
5. Display result  
6. Calculate win  
7. Add features  
8. Add juice (effects, animation)

---

## 12. Core Rule

# ALWAYS:  
result = generate_result()  
# THEN:  
animate()  
# THEN:  
calculate_win()

---

## 🚀 Done

You now have a complete functional slot structure.  
Next step: polish animation + add personality.

  
---  
  
If you want next, I can:  
- build a **Godot reel scene script (ready-to-drop)**  
- or design your **symbol art list + exact payouts tuned for feel**
# Images
![[Maya's golden riches await 1.png]]

![[Cat-girl Egyptian queen character sheet.png]]

![[Egyptian casino enchantress with floating treasures.png]]

![[Egyptian casino queen cat-girl.png]]

![[Egyptian-inspired cat-girl character reference.png]]

![[Egyptian-inspired cat-girl reference sheet.png]]

![[Maya's golden fate slot machine.png]]

![[Maya's golden invitation to win.png]]