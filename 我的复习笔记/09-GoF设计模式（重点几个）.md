# 09 - GoF 设计模式（重点几个）

> **建造时间**：Week 3（与 GRASP 同周）  
> **重要程度**：⭐⭐⭐ 简答题高频，不会全考但必考几个  
> **依赖**：06 / 07  
> **被依赖**：13（POS 用 Adapter 隔离外部支付）

---

## 学习目标

考试常考的几个：

- [ ] **Adapter**（适配器）—— 仿真卷简答题原题
- [ ] **Strategy**（策略）—— 仿真卷简答题原题
- [ ] **Observer**（观察者 / Subscribe-Notify）—— 仿真卷选择题原题（MVC 通知机制）
- [ ] **Factory** / **Singleton**（创建型基础）
- [ ] **Facade**（外观）—— POS 案例的 PersistenceFacade
- [ ] **Composite**、**Decorator**（备选，时间够再学）

---

## 内容（待 Week 3 填充）

每个模式的标准格式：

```
Pattern Name: 
Intent (one English sentence): 
Problem it solves: 
Solution structure (Mermaid class diagram): 
Consequences (advantages / liabilities): 
Code skeleton: 
Real-world example: 
```

### 1. Adapter
### 2. Strategy
### 3. Observer
### 4. Factory / Abstract Factory
### 5. Singleton
### 6. Facade

---

## 答题英文模板（Adapter）

```
Adapter Pattern.
Intent: Convert the interface of a class into another interface clients expect.
       Adapter lets classes work together that couldn't otherwise because of incompatible interfaces.
Example: A payment service requires the interface IPaymentGateway,
        but the third-party library exposes StripeAPI. A StripeAdapter
        implements IPaymentGateway by delegating to StripeAPI.
```

---

## 举一反三

> Strategy 模式：POS 系统的不同税收计算（中国 / 美国 / 欧盟）；Observer 模式：股票价格变动通知多个订阅者。

---

## 状态

- 完成度：⬜ 未开始
- 关联错题：—
- 下次回顾日期：—
