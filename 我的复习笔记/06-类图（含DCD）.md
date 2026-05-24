# 06 - 类图（含 DCD）

> **建造时间**：Week 2  
> **重要程度**：⭐⭐⭐⭐ 必考  
> **依赖**：03（领域模型）、05（顺序图——消息揭示方法）  
> **被依赖**：07（GRASP 用类图表达职责）

---

## 学习目标

- [ ] 类图标注完整 5 部分：可见性 / 名称 / 属性 / 方法 / 多重性
- [ ] 关联（Association） / 聚合（Aggregation） / 组合（Composition）的语义和符号差别
- [ ] 依赖（Dependency）vs 关联：何时用虚线
- [ ] 泛化（Generalization）与实现（Realization）
- [ ] 接口与抽象类
- [ ] 从顺序图反推 DCD（哪些方法是必要的）
- [ ] **关键区分**：Domain Model（概念类图） vs DCD（设计类图）

---

## 内容（待 Week 2 填充）

### 1. 类图 5 大成分

### 2. 关系类型完整表

| 关系 | 符号 | 语义 | 例子 |
|------|------|------|------|
| Association | 实线 | 对象间结构联系 | Customer ↔ Order |
| Aggregation | 空心菱形 | 整体-部分（弱） | Department ◇ Professor |
| Composition | 实心菱形 | 整体-部分（强，同生命周期） | Order ◆ LineItem |
| Dependency | 虚线箭头 | 使用关系 | Class ⇢ Logger |
| Generalization | 空心三角实线 | is-a | Dog →▷ Animal |
| Realization | 空心三角虚线 | implements | List ⇢▷ Iterable |

### 3. 多重性

### 4. 可见性符号 + - # ~

### 5. Domain Model vs DCD 对比

---

## 答题英文模板

待 Week 2 填充。

---

## 举一反三

> 学校管理系统：Student, Course, Enrollment（关联类）, Professor, Department 的类图。

---

## 状态

- 完成度：⬜ 未开始
- 关联错题：—
- 下次回顾日期：—
