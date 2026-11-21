# 出口唛头的转写、归属与并柜签收

业务资料使用虚构编号和合成叙述。文本保持来件拼写和措辞。各表是独立的来源记录。
TSV 文件采用 UTF-8，首行为列名。行首 id 是该表的稳定记录号，空格和标点属于原文，空单元格表示来件未填。
日期时间采用所在地本地时间。资料内注明为编号列表的字段用竖线分隔。

## 资料字段

- `materials/parties.tsv`。legal 是来函主张的登记名称，oldmark 是曾在该地点使用的标记，agent 为共有进口代理。
- `materials/mail.tsv`。note 为来件整句，received 是代理登记时点，filed_party 为签函者自己的声明方。
- `materials/packages.tsv`。master 和 seal 为实际包装上的容器及封条，bill 为独立分单，mask 说明接收阶段可见性。
- `materials/handoffs.tsv`。actor 为现有领运人登记文字，seen 是实际被交接人抄出的记录。
- `materials/inspection_points.tsv`。visibility 是代理记录的现场拆包许可及可重贴外标的地点说明。
- `materials/mark_changes.tsv`。现场抄标与换膜留档，point 指现场检查点。
- `materials/signing_letters.tsv`。签收授权来函，issuer 是所署机构，scope 保留原文。

## 运行资料检查

使用 CPython 3.11.2 和标准库。资料检查仅读取输入。

```sh
python3 pack_check.py
python3 -m unittest -v
```
