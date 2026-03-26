# intermediates_search_for_polmers

这是一个以 **Matlantis / ASE 相关测试脚本** 为主的实验仓库，主要用于分子动力学（MD）、NEB、表面吸附、结构优化以及参数搜索等方向的快速验证。

仓库中的内容以 **Python 脚本** 为主，同时包含一些 **Jupyter Notebook**。其中一部分脚本是手工编写和迭代的实验代码，另一部分则是在实际研究和测试过程中结合 **AI 辅助生成、改写或补充** 得到的原型脚本。

## 项目特点

- 以 Matlantis / ASE 生态为核心的测试与验证脚本集合
- 包含 MD、NEB、Optuna 搜索、表面-分子分析等不同主题
- 既有命令行脚本，也有 Notebook 形式的交互式实验记录
- 更偏向研究过程中的原型开发与思路验证，而不是严格产品化的工程项目

## 目录概览

### 根目录脚本

- `md.py` / `MD1.py` / `MD2.py` / `MD_loop_full.py`
  - 与分子动力学模拟相关的测试脚本
- `NEB.py`
  - 与 NEB / 反应路径搜索相关的实验脚本
- `optuna+md.py` / `optuna2.py`
  - 与参数搜索、结构筛选或优化实验相关
- `run_md_best_trials.py`
  - 对已筛选结构批量执行 MD 的脚本
- `care_test.py` / `after_train.py` / `2.py`
  - 一些独立测试或辅助实验脚本

### Notebook

- `ketone.ipynb`
- `Neb_test.ipynb`
- `Neb_test (1).ipynb`
- `Neb_test_results_2025-06-26_143727.ipynb`
- `test_ads.ipynb`
- `test_ads (1).ipynb`
- `test_MD.ipynb`
- `test_optuna_first.ipynb`

这些 Notebook 主要用于：

- 快速验证思路
- 可视化结构与结果
- 记录某次实验流程或中间结果

### 子目录

- `optuna+MD/`
  - 包含 MD、Optuna、氧化分析、碳原子优化等相关脚本与说明文档
- `surface_test_ai/`
  - 面向表面+分子体系分析的一组模块化脚本，带有较明显的 AI 辅助开发痕迹
- `Straightchain_VOC/`
  - 针对直链 VOC 或类似分子体系的搜索与优化实验脚本

## 主要技术栈

本仓库中的脚本主要围绕以下工具或库展开：

- Python
- Jupyter Notebook
- ASE
- Matlantis 相关计算接口
- Optuna
- NumPy / Pandas / Matplotlib

部分脚本中还出现了这些依赖：

- `pfp-api-client`
- `fairchem`
- `torch`
- `torch_dftd`
- `sella`
- `nglview`

由于不同脚本来自不同阶段的实验，依赖并不完全统一，实际使用前建议先查看目标脚本顶部的 `import`。

## 使用说明

### 1. 环境准备

建议使用独立 Python 环境，例如 Conda 或 venv。

常见基础依赖示例：

```bash
pip install ase numpy pandas matplotlib jupyter optuna
```

如果要运行依赖 Matlantis / PFP / FairChem 的脚本，还需要根据对应脚本补充安装相关包，并完成必要的账号、API 或模型环境配置。

### 2. 运行 Python 脚本

例如：

```bash
python md.py --help
python NEB.py
python run_md_best_trials.py
```

注意：

- 并不是所有脚本都做了完整的命令行封装
- 有些脚本需要提前准备结构文件、模型或输出目录
- 有些脚本是研究阶段原型，运行前建议先阅读源码

### 3. 运行 Notebook

```bash
jupyter notebook
```

然后打开对应的 `.ipynb` 文件逐步执行。

## 适用场景

这个仓库适合用于：

- 快速测试 Matlantis/ASE 在特定体系上的可行性
- 验证 MD、NEB、结构优化和反应路径分析思路
- 保存研究过程中的脚本原型和 Notebook 记录
- 作为后续整理正式项目时的实验素材库

## 说明

- 这是一个实验性质较强的仓库，脚本风格和完成度可能不完全一致
- 部分代码是为了快速验证想法而编写，可能需要根据具体课题进一步整理
- 部分脚本包含 AI 辅助生成或修改的内容，使用前建议结合实际计算需求进行检查

## 后续可整理方向

如果后续要把这个仓库进一步规范化，可以优先考虑：

- 统一依赖管理（如 `requirements.txt` 或 `environment.yml`）
- 补充每类脚本的输入输出说明
- 将重复逻辑抽离为公共模块
- 对 Notebook 和正式脚本做分层整理
- 增加示例数据与最小可运行案例

## License

当前仓库未单独声明许可证。如需公开发布或对外共享，建议补充明确的 License 文件。
