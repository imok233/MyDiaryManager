# MyDiaryManager - 个人日记自动管理工具

## 功能简介
- 自动创建每日 Markdown 格式日记文件，支持自定义命名格式和模板。
- 按年份、月份自动分类存放日记文件。
- 支持通过配置文件自由设置路径、模板使用与文件命名。
- 支持 Windows 任务计划程序自动化每日运行。

## 文件说明

| 文件名                 | 作用说明                                       |
| ---------------------- | ---------------------------------------------- |
| `diary_manager.py`     | 核心业务代码                                   |
| `utils/file_utils.py`  | 文件处理工具函数                               |
| `templates/default.md` | 日记模板文件，包含默认标题和提示文本，可自定义 |
| `config.yaml`          | 配置文件示例，用户请复制并修改为 `config.yaml` |
| `auto_create_diary.py` | 自动创建日记的脚本，读取配置自动生成文件       |
| `start.bat`            | Windows 批处理文件，方便双击运行脚本           |
| `README.md`            | 本说明文档                                     |

## 使用步骤

1. **准备环境**  
   - 安装 Python 3.x  
   - 安装依赖库：  
     ```bash
     pip install pyyaml
     ```

2. **配置**     
   
   - 运行`diary_manager.py`，按照提示选择日记根目录、模板路径、文件命名格式等设置。        
   - 配置完成后，程序会自动保存配置文件 `config.yaml`。     
   - 无需手动编辑配置文件。
   
3. **手动测试**  
   - 在命令行或终端运行：  
     ```bash
     python auto_create_diary.py
     ```
   - 检查对应目录是否生成了当天日记文件。

4. **自动化运行（可选）**  
   
   - 使用 Windows 任务计划程序安排每日定时执行 `auto_create_diary.bat`，实现自动日记创建。  
   - 具体设置方法请参考 Windows 任务计划程序官方文档。

## 注意事项

- 配置文件中的路径请使用绝对路径，注意反斜杠 `\` 转义或使用双反斜杠 `\\`。  
- 模板文件中支持 `{{date}}` 占位符，会自动替换为当前日期（格式 `YYYYMMDD`）。  
- 如遇错误，请先检查配置文件路径和 Python 环境。

---

*感谢使用 MyDiaryManager！*