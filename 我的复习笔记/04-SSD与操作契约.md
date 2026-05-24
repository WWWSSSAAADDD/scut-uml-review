# 04 - SSD 与操作契约

> **建造时间**：Week 2  
> **重要程度**：⭐⭐⭐ 介于分析和设计之间的桥梁  
> **依赖**：02 / 03  
> **被依赖**：05（顺序图）

---

## 学习目标

- [ ] System Sequence Diagram 与普通顺序图的区别（系统当黑盒）
- [ ] 从用例 Main Success Scenario 推导 SSD 的系统事件
- [ ] 知道操作契约（Operation Contract）的四个 section: Operation / Cross-References / Preconditions / Postconditions
- [ ] 后置条件三类：instance creation/deletion / attribute modification / association formed/broken

---

## 内容（待 Week 2 填充）

### 1. SSD 是什么、为什么有用

### 2. SSD vs 普通 Sequence Diagram

### 3. 操作契约的格式

### 4. 后置条件的三类变化

---

## 答题英文模板

```
Operation: makePayment(amount: Money)
Cross-References: Use Cases: Process Sale
Preconditions: a Sale is currently being processed.
Postconditions:
  - A Payment p was created (instance creation).
  - p.amount = amount (attribute modification).
  - p was associated with the current Sale (association formed).
  - the current Sale was marked as complete (attribute modification).
```

---

## 举一反三

> 银行 ATM 取款的 SSD 长什么样？操作契约 `withdraw(amt)` 怎么写？

---

## 状态

- 完成度：⬜ 未开始
- 关联错题：—
- 下次回顾日期：—
