# TACP Protocol Specification V1.0

1. 元数据头部注入规范 (Metadata Header Injection)
在任何兼容 TACP 的 AI 系统输出中，必须在正文最顶端强制包含以下 YAML 头部：  
In any TACP-compatible AI system output, the following YAML header must be mandatorily included at the very top of the body:

```yaml
---
TACP_Protocol_Version: 1.0.0
H_Axis: "HB-YYYYMMDD-HHMM"
C_Axis: "YYYY-MM-DD HH:MM:SS (UTC+8)"
Delta_Axis: 
  Parent_Node: "HB-XXXXXXXX-XXXX"
  Relation_Type: "Inherit" # Options: Inherit, Refute, Refine, Supplement
  Description: "Brief description of the causal relationship for this generation"
Jurisdiction: "Dunjun"
---
```


2. 校验与熔断机制 (Validation & Circuit Breaker)

TACP 引擎在接收或生成信息时，必须执行以下校验：
The TACP engine must execute the following validations when receiving or generating information:

a.C轴完整性校验 (C-Axis Integrity Check): 若缺失或格式错误，触发 ERROR_C_AXIS_MISSING，立即终止推理。
If missing or malformed, trigger ERROR_C_AXIS_MISSING and immediately terminate inference.

b.H轴单调性校验 (H-Axis Monotonicity Check): 当前 H轴 必须严格大于 Parent_Node 的 H轴，否则触发 ERROR_TEMPORAL_PARADOX（时间悖论）。
The current H-Axis must be strictly greater than the Parent_Node's H-Axis; otherwise, trigger ERROR_TEMPORAL_PARADOX.

c.Δ轴溯源校验 (Δ-Axis Traceability Check): 随机抽样检查 Parent_Node 是否存在于本地知识库中，若断裂则降级当前节点的可信度权重。
Randomly sample-check if the Parent_Node exists in the local knowledge base; if broken, downgrade the credibility weight of the current node.
