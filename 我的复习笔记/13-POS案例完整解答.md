# 13 - POS 案例完整解答

> **建造时间**：Week 5  
> **重要程度**：⭐⭐⭐⭐⭐ 仿真卷压轴题就是这个  
> **依赖**：01-10 全部  
> **被依赖**：考试

---

## 题目（取自 仿真卷.doc 第 5 题）

> Suppose you are asked for developing a point of sale (POS) system using OOA/D technologies. A POS system is a computerized application used to record sales and handle payments and it is typically used in a retail store. Processing sale would be one of the key functions that the system has to perform. Please model the key function via the methodology of object-oriented analyze and design.
>
> Suppose the simplified context of processing sale is under-consideration: a customer arrives at a checkout of a retail store with items to purchase. The cashier uses register of the POS system to record each purchased item. Each of the items is described a product specification, which belongs to a product catalogue. The system presents a running total and line-item details. The customer enters payment information, which the system validates and records. The system updates inventory. The customer receives a receipt from the system and then leaves with the items and the sale is logged on a ledger with which the manager can checked the information for a period of time.
>
> 1. Draw a UML use case diagram (Score 5).
> 2. Class diagram with analysis classes (names + descriptions only, with multiplicities) (Score 10).
> 3. Boundary / Control / Entity classes for J2EE (Score 5).
> 4. UML sequence diagram for "process sale" in J2EE (Score 10).

总分 30，是案例分析全部分值。

---

## 标准解答（待 Week 5 完整填充）

### Part 1 · Use Case Diagram（5 分）

```mermaid
%% Week 5 填充
```

### Part 2 · Analysis Class Diagram（10 分）

```mermaid
%% Week 5 填充
```

### Part 3 · Boundary / Control / Entity（J2EE / Robustness Analysis）（5 分）

| 类名 | Stereotype | 一句描述 |
|------|-----------|---------|
| ProcessSaleUI | `<<boundary>>` | Cashier-facing screen for recording items and payment |
| ProcessSaleController | `<<control>>` | Coordinates the sale workflow |
| Sale | `<<entity>>` | The transaction being processed |
| LineItem | `<<entity>>` | Individual purchased item line |
| ProductSpecification | `<<entity>>` | Catalogue description of a product |
| Payment | `<<entity>>` | Money tendered by customer |
| Inventory | `<<entity>>` | Stock quantities |
| Ledger | `<<entity>>` | Audit log queryable by manager |

### Part 4 · Sequence Diagram for Process Sale（10 分）

```mermaid
%% Week 5 填充
```

---

## 备选/常见变体题型（Week 5 也要练）

- 同样场景换问"画领域模型 + 操作契约"
- 同样场景换问"用 GRASP 解释每条消息为什么发给那个对象"
- 把 J2EE 换成普通分层架构

---

## 手画清单（考前 1 周每日 1 张）

- [ ] 6/22 (Mon)：Use Case Diagram
- [ ] 6/23 (Tue)：Domain Model
- [ ] 6/24 (Wed)：System Sequence Diagram (SSD)
- [ ] 6/25 (Thu)：Operation Contract
- [ ] 6/26 (Fri)：Sequence Diagram (J2EE)
- [ ] 6/27 (Sat)：Boundary/Control/Entity Class Diagram
- [ ] 6/28 (Sun)：完整解答连续画一遍（计时）
- [ ] 6/29 (Mon)：DCD（Design Class Diagram）
- [ ] 6/30 (Tue)：考前最后一遍

每张拍照存到 `images/手画/YYYY-MM-DD-<diagram>.jpg`。

---

## 状态

- 完成度：⬜ 未开始
- 关联错题：—
- 下次回顾日期：—
