# 郭跃 · Yue Guo

**具身世界模型 · World-Action Model · 机器人学习**

哈尔滨工业大学（深圳）硕士，CAIA 实验室，预计 2027 年 6 月毕业。当前在北京人形机器人创新中心大模型组实习。

我关注如何把视频预测与机器人动作连接起来：用统一的视觉动作表示连接不同本体，用多流建模整合多视角与多模态观测，再通过数据、评测和真机反馈迭代模型。

[项目与演示](https://github.com/guoyue0412/reading-journal-sites/blob/main/projects.md) · [论文阅读](https://github.com/guoyue0412/reading-journal-sites/tree/main/content/papers) · [具身研究笔记](https://guoyue0412.github.io/embodied-frontier/) · [邮件联系](mailto:1601954018@qq.com)

## 研究工作

### Dream4ACT · 跨本体视觉动作接口

*Dream4ACT: A Shared Visual Action Interface for Multi-Embodiment Video-Action Modeling*

**ICLR 2027 · 已投稿（Submitted）**

基于 URDF 将异构关节配置表示为四视角动作视频，复用视频骨干联合建模观测与动作；通过 **training-free 多视角几何匹配**恢复可执行关节轨迹，无需本体专属动作解码头或真实相机外参对齐。

- **仿真评测：**RoboTwin2.0 全部 50 项任务，Clean / Randomized 两种设置的平均成功率为 **88.98%**。
- **跨本体验证：**另一组联合训练实验以固定权重支持四种真机平台；放置与擦拭两项共同任务的平台平均成功率为 **85%–90%**。

### WEAVE-0.5 · 多流具身世界模型

*WEAVE-0.5: Weaving Multi-stream Observations into Embodied World Models*

**ICLR 2027 · 已投稿（Submitted）**

通过原生分辨率独立编码、共享虚拟画布与跨流注意力，统一可变视角、混合分辨率及多模态观测；单一模型支持未来预测、跨视角补全和模态互转。

- **我的工作：**参与模型训练与数据消融，搭建评测平台，开展 bad case 分析与数据回流；建设 YouTube 视频管线和 Sim–Real 成对数据生产链路。
- **论文结果：**MV-261 上联合生成深度流，使主视角 PSNR 从 **15.74 提升至 17.87 dB（+2.13 dB）**；论文报告 RBench 第一、TriWorldBench 第二。

<sub>以上研究指标来自论文报告；榜单名次对应论文中的评测快照。Dream4ACT 的全任务评测与跨本体实验使用不同 checkpoint。</sub>

### Colugo · 多尺度潜在世界模型引导 VLA

协作研究 · 2026.04.26–2026.06.04

参与以 learnable slow / fast queries 预测 latent futures，通过 dual cross-attention 与 MLP fusion 调制 flow-based Action DiT。在 **LIBERO-Long、CALVIN ABC→D 和 AgileX Nero + RealSense D455** 上完成消融与真机验证；推理时移除 reconstruction decoder。

## 从模型训练到真机执行

**北京人形机器人创新中心 · 大模型组｜2026.07.31–至今**

围绕 WEAVE-0.5、Dream4ACT 开展研究工作，搭建 Isaac Sim 轨迹回放、域随机化与 Sim2Real / Real2Sim 数据链路，结合模型评测推进数据增广与迭代。

**智源人工智能研究院（BAAI）· 认知大模型组｜2026.04–2026.07.28**

搭建 Cosmos-Predict2.5-2B → PolicyDiT → ActionExpert / ActionDecoderDiT 三阶段 WAM，统一多源异构动作表示，开展 EgoDex → Ego2Robot 转换与教师–学生蒸馏。负责 DiT4DiT 数据采集、训练和 OpenArm 真机部署，完成酒店场景证件交互与双臂叠衣复现。

**道通智能 · 前沿预研｜2025.11–2026.04**

负责 OpenPI π₀.₅ SFT 与 ROS2 真机部署；将真机纠偏与恢复数据回流用于 **纠偏 SFT**，使工厂抓取放置任务的真机成功率从 **40% 提升至 70%**。构建 JAX BPTT 可微仿真与残差动力学管线，训练吞吐达到原来的 **10 倍**，动力学预测误差降至原来的 **十分之一**。

## 代表性演示

下方为 BAAI 和道通期间的真机演示，点击预览可打开视频。

<table>
  <tr>
    <td width="50%">
      <a href="https://github.com/guoyue0412/reading-journal-sites/blob/main/assets/evidence/baai-dit4dit/openarm_demo.mp4">
        <img src="https://raw.githubusercontent.com/guoyue0412/reading-journal-sites/main/assets/thumbs/openarms.jpg" alt="BAAI OpenArms 双臂叠衣真机演示的视频预览" width="420">
      </a>
      <br><strong>OpenArms 双臂叠衣</strong><br>
      DiT4DiT 跨本体后训练与真机部署
    </td>
    <td width="50%">
      <a href="https://github.com/guoyue0412/reading-journal-sites/blob/main/assets/evidence/daotong-vla/vla_realrobot_test.mp4">
        <img src="https://raw.githubusercontent.com/guoyue0412/reading-journal-sites/main/assets/thumbs/vla.jpg" alt="道通 OpenPI π₀.₅ 真机操作演示的视频预览" width="420">
      </a>
      <br><strong>OpenPI π₀.₅ 真机操作</strong><br>
      机器人数据处理、SFT 与 ROS2 端云部署
    </td>
  </tr>
</table>

[查看完整演示画廊](https://github.com/guoyue0412/reading-journal-sites/blob/main/projects.md) · [WAM 多视角预测](https://github.com/guoyue0412/reading-journal-sites/blob/main/projects.md#baai--wam-多视角视频预测) · [Sim–Real 成对数据](https://github.com/guoyue0412/reading-journal-sites/blob/main/projects.md#北京人形--weave-05-预训练数据基建)

## 技术与其他实践

- **模型与训练：**PyTorch、JAX、DeepSpeed；DiT、Diffusion / Flow Matching、VLM / VLA、多机多卡训练。
- **数据、仿真与部署：**LeRobot / OXE、DROID、EgoDex、AgiBot、RoboTwin；Isaac Sim、MuJoCo、ROS2、TensorRT / ONNX。
- **评测与工程：**LIBERO、CALVIN、RoboTwin、RoboDojo；Python、ROS、MATLAB，C++ 入门；RLT 等在线强化学习方法复现实践。
- **机器人系统：**曾任复合机器人月球探索团队负责人，负责全向底盘、5-DOF 机械臂与多传感器融合，获中国机器人及人工智能大赛国家一等奖；工程实践与创新能力大赛「智能+」赛道全国总决赛金奖。

我持续整理 [论文阅读笔记](https://github.com/guoyue0412/reading-journal-sites/tree/main/content/papers) 与 [具身研究资料](https://guoyue0412.github.io/embodied-frontier/)，欢迎交流世界模型、机器人学习与评测。
