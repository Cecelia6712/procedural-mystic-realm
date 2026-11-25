<img width="3010" height="1756" alt="1" src="https://github.com/user-attachments/assets/1b6afe2e-db71-4cd1-93b6-a37e781b82e5" /><div align="center">

# 🏝️ 程序化秘境 (Procedural Mystic Realm)

**一个基于纯算法与底层数学推导生成的 3D 虚拟生态漫游系统**

[![Three.js](https://img.shields.io/badge/Three.js-r160-blue?style=flat-square&logo=three.js)](https://threejs.org/)
[![WebGL](https://img.shields.io/badge/WebGL-2.0-red?style=flat-square&logo=webgl)](https://www.khronos.org/webgl/)
[![GLSL](https://img.shields.io/badge/Shader-GLSL-orange?style=flat-square)](https://www.khronos.org/opengl/wiki/OpenGL_Shading_Language)
[![License](https://img.shields.io/badge/License-MIT-green.svg?style=flat-square)](https://opensource.org/licenses/MIT)

[👉 **点击这里进入在线演示 (Live Demo)**](https://cecelia6712.github.io/procedural-mystic-realm/) 👈

</div>

---

## 📸 视觉展示

<!-- 
  🚨 拖拽教学：
  1. 把鼠标光标放到下面这段文字的中间。
  2. 直接从你的电脑里，把截图拖进这个网页编辑框。
  3. GitHub 会自动生成一段 `![image](https://github.com/user-attachments/assets/...)` 的代码。
  4. 把生成的那段代码留在这里就行了。
-->

<div align="center">
  <!-- 在这里拖拽你的第一张图（白昼地貌） -->


<img width="3010" height="1756" alt="1" src="https://github.com/user-attachments/assets/a7fd368d-6e7a-4bb5-80fc-21bc2a7ef5dd" />

  <!-- 在这里拖拽你的第二张图（黄昏秘境） -->
![Uploading 2.png…]()
![Uploading 4.png…]()
![Uploading 3.png…]()


  <!-- 在这里拖拽你的第三张图（幽蓝星夜） -->
  
</div>
<p align="center"><i>基于手写 fBm 地形算法与点精灵粒子系统的实机渲染截图</i></p>

## 📖 项目简介

《程序化秘境》是一个完全由代码实时计算生成的交互式 3D 生态场景。与传统依赖 Blender 等外部建模工具的项目不同，本作**不加载任何外部模型（No GLTF/OBJ）**，场景中的每一座山脉、每一棵树木、每一颗粒子均由数学算法动态生成。

本项目作为《计算机图形学原理》课程设计的满分作品，同时也是本科毕业设计《虚拟生态模拟系统》的核心雏形。

## ✨ 核心技术特性 (Features)

*   🧮 **底层矩阵推导**：纯手写 MVP 矩阵（透视/正交），放弃引擎内置 Camera，深刻还原 \(w_c = -z\) 的齐次坐标透视除法原理。
*   ⛰️ **自然分形地形**：手写 2D Perlin 噪声与分形布朗运动 (fBm)，引入 Hurst 指数 (\(D = 3 - H\)) 动态控制地形粗糙度。
*   🌲 **L-System 生态**：基于字符串重写的林氏系统，结合四元数（Quaternion）进行 3D 空间变换，实时生成具有拓扑结构的树木。
*   🏗️ **实体几何造型**：利用扫描表示法（平行传输标架）沿贝塞尔曲线生成管道；使用基于 BVH 加速树的 CSG 布尔运算，从圆柱塔楼中“抠”出门窗。
*   ✨ **粒子与后处理**：手写 GLSL 着色器实现距离衰减与圆形点精灵，结合 Additive Blending（加性混合）与 UnrealBloom 泛光，打造发光孢子群。
*   🖱️ **实时射线交互**：基于 Raycaster 射线检测，鼠标左键点击地形即可实时生成树木，伴随生长动画特效。

## 🎮 操作指南

*   `W A S D`：第一人称移动
*   `鼠标`：旋转视角（Yaw/Pitch）
*   `Space / Shift`：升空 / 下降
*   `V`：切换 **透视投影 (Perspective)** / **正交投影 (Orthographic)**
*   `鼠标左键`：在准星处 **点击种树** (需在草地或森林海拔)
*   `右上角面板`：实时调整 Hurst 指数、雪线高度、粒子数量等参数

## 🛠️ 本地运行

由于浏览器安全限制（PointerLock 与跨域加载），请勿直接双击 `index.html`。请使用本地静态服务器：

```bash
# 如果你安装了 Python
python -m http.server 8080

# 或使用 Node.js
npx http-server -p 8080
