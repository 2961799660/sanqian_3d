# 三千AI · 3D 快速上手(5 分钟从注册到导出第一个模型)

## 第 1 步 · 注册

访问 <https://3d.zijie.lol/>,手机号注册。

**新人福利**:**注册即送 300 积分**(价值 ¥45)· **14 天有效** · **任务失败 0 扣费**。

300 积分够走通本教程一遍(单 NPC 完整资产约 80-150 积分)。

## 第 2 步 · 描述你要的物体

进入"生成"页,在 prompt 框输入自然语言描述。

**好的 prompt 示例**:

```
战损头盔 · 科幻风格
古董相机 · 1930 年代金属机身
雕花灯笼 · 铁艺 + 透光玻璃
玩具跑车 · 压铸红色 · 1980 风格
```

**Prompt 写作技巧**:

1. **物件 + 风格**:`战损头盔 + 科幻` 比 `头盔` 信息密度高
2. **加材质 / 时代**:`黄铜工业风`、`1930 年代` 这种修饰词很关键
3. **避免模糊**:`一个东西` 这种没法用,模型猜不到

## 第 3 步 · 选引擎

| 你的情况 | 选哪个 |
|---|---|
| 第一次试 prompt,看大概方向 | **Turbo**(8-12s,~10 积分) |
| 想要质量 + 全控制,贴近 prompt | **v3.1**(~30s,~30 积分) |
| 最终交付件,质量优先 | **P1**(~30s,~30 积分) |
| 老接口复刻(不进下游管线) | **v1.4**(~10s,~10 积分) |

**推荐流程**:Turbo 先跑两轮锁定方向 → P1 出最终件。

## 第 4 步 · 加交付选项(按需)

模型基础生成后,你可以叠加:

- **+4K PBR 贴图**(+10 积分):进引擎必备
- **+四边面拓扑 Quad**(+5 积分):要在 Maya / Blender 二次编辑必加
- **+自动绑骨**(25 积分):角色 / 生物类必加
- **+预设动画**(每个 10 积分):16 种可选,常用 4 个动画 = 40 积分
- **+智能分块**(40 积分):做 3D 打印手办用
- **+智能补全**(50 积分):残缺扫描或单视角盲区补

## 第 5 步 · 导出

格式选择:

- **进游戏引擎(Unity / Unreal)** → FBX 或 GLB
- **进 Web / Three.js / Babylon** → GLB
- **进 Apple AR** → USDZ
- **3D 打印 / 通用交换** → OBJ

点"下载",国内 GLB 加速代理秒级到本地。

## 第 6 步 · 进引擎(Unity 为例)

```csharp
// 把下载的 GLB 拖进 Unity Assets
// 角色类资产挂载 Animator,选预设动画 Controller

using UnityEngine;

public class NpcController : MonoBehaviour
{
    private Animator animator;

    void Start() { animator = GetComponent<Animator>(); }

    public void PlayIdle() { animator.Play("Idle"); }
    public void PlayWalk() { animator.Play("Walk"); }
    public void PlayAttack() { animator.Play("Attack"); }
}
```

## 完整工作流示范 · 一个游戏 NPC

```
1. 描述:"科幻战士 · 重甲 · 科技纹路"
2. P1 引擎 → ~30 积分
3. +4K PBR → +10 积分
4. +四边面拓扑 → +5 积分
5. +自动绑骨 → +25 积分
6. +8 个双足动画(待机/走/跑/跳/攻击/受击/死亡/胜利) → +80 积分
7. 导出 GLB → 国内代理秒下
8. 拖进 Unity → 挂 Animator → 完工
```

**总消耗**:**150 积分**(按 ¥15=100 积分 算,具体单价以演示站当期为准)。**总耗时**:从输入 prompt 到 Unity 跑起来 < 5 分钟。

## 下一步

- 看完整产品文档:[`product.md`](./product.md)
- 看计费细则:[`pricing.md`](./pricing.md)
- 看 FAQ:[`faq.md`](./faq.md)
- 看示例 prompt 库:[`../examples/prompts.md`](../examples/prompts.md)
