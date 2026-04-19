# cn-gov-docx

`cn-gov-docx` 是一个面向中文正式文档和公文式 Word 场景的 companion skill。

它不替代通用的 `docx` skill，而是补上中文正式写作里最容易缺失的一层：

- 文种判断
- 结构编排
- 中文正式语体约束
- 常见版式与字体默认值
- 交付前校核

适用场景包括：

- 建设方案
- 工作方案
- 汇报材料
- 常见问题说明
- 函件
- 请示
- 会议纪要
- 对外正式 `.docx` 材料

## 设计定位

这个 skill 的职责是先回答两个问题：

1. 这份文档到底属于哪一种正式文种
2. 应该按什么结构、语体和版式来落地

如果任务还需要真正生成、编辑或修补 `.docx` 文件，则由已安装的 `docx` skill 继续处理具体的 Word 文件操作。

也就是说：

- `cn-gov-docx` 负责中文正式文档的方法层
- `docx` 负责 Word 文件的操作层

## 当前包含的内容

- `SKILL.md`
  - skill 的触发条件、工作流和协同边界
- `references/document-types.md`
  - 常见正式文种的判断与结构
- `references/layout-and-typography.md`
  - 中文正式文档的版式和字体默认值
- `references/review-checklist.md`
  - 对外交付前的校核清单
- `scripts/render_starter_template.py`
  - 生成中文正式 `.docx` 起始骨架

## 快速使用

生成一份“建设方案”类型的起始 `.docx`：

```bash
python scripts/render_starter_template.py \
  --type implementation-plan \
  --title "山东省医学开放数据科研平台建设方案" \
  --unit "项目组" \
  --output ./山东省医学开放数据科研平台建设方案.docx
```

## 说明

- 这里提供的是通用中文正式文档默认规则，不替代具体单位的正式模板。
- 如果用户已经提供医院、高校、政府或企业的 Word 模板，应以该模板为准。
- 本仓是原创 companion skill，不是第三方 `docx` skill 的 fork。

## License

MIT
