# Rime键道输入法（Colemak-DH Matrix）

这个仓库包含了我所有关于[星空键道](https://github.com/xkinput/Rime_JD)的配置与自定义文件。

---

想要进一步了解这款优雅的中文输入方案？来看看我自制的[Rime键道输入法文档](https://pingshunhuangalex.gitbook.io/rime-xkjd/)吧!

## 回归初心

键道创始之初，其核心设计理念的一部分便是词库。“质量极高，大而不臃、全而不废，极低的词组打空率”曾一度是其闪光点。时过境迁，因缺乏统一的词库删改标准加上极其有限的审核维护资源，键道词库正渐渐趋于臃肿，怪词废词不断。

由于目前词库的删改逻辑与我的预想相去甚远，极低的更新频率更是使其雪上加霜。思前想后，我决定摒弃官方词库，另起炉灶，打造属于我自己的键道词库。

## 词库归类逻辑

为加强字词检索时的效率与准确性，同时优化「极速跟打器」中的编码提示与可视化，新词库将更为细化的对字词进行归类，使长度更大且码长更小的字词优先得到映射（[查看词库结构](https://github.com/pingshunhuangalex/rime-xkjd/blob/main/xkjd6.extended.dict.yaml)）。

## 简码整理逻辑

- 移除简码三重

- 移除三级简码

- 避免将除一级简码以外的简码空间用于单字

- 尽可能利用所有简码与其次选的编码空间

- 移除完全由一级简码单字组成的二字词组

- 移除完全由特殊简码词组组成的多字词组（无论码长是否增加）

- 移除特殊简码词组所对应的声韵编码词组以节省声韵编码空间（关闭630提示）

- 在码长没有缩短的情况下（含上屏用空格或次码编码），优先采用简码编码形式或直接拆分为单字进行输入以节省声韵编码空间

- 如单字为一级简码，则在声韵编码空间只保留其所对应的声韵全码编码

- 为特殊简码添加次选从而将编码空间从630（`21*5+21*5*5=630`）扩充至1260

## 词库删改逻辑

- 审核改动字词是否为合理的汉语字词且具有复用性与时效性，尊崇“少既是多”的原则而非盲目占用编码空间（怪词废词越多，顶功效率越差）

- 将改动字词根据其性质与输入方式归类到相应词库

- 在码长没有明显降低（节省两码以上）的情况下，避免将泛用型前后缀（如`不`，`的`等）编入词组以避免编码膨胀

- 避免将数字、量词与名词同时编入词组以避免编码膨胀（不包括固定搭配或意义抽象）

- 根据使用频率调整字词顺序
  - 优先提升高频字词在其所在区域的顺位（无论同区域低频字词的码长是否会膨胀）
  - 在四周字词具有相似使用频率的情况下，调整字词的顺序使该区域的平均码长尽可能降低

- [标注首选与次选] 在出现字词编码长度超出其默认编码长度两位以上时，尽可能利用编码次选位置来降低平均码长

- 尽可能使相同结构的词拥有相同的编码长度
  - 词组如能同时与`得`、`地`与`的`搭配，则确保相应词组顺序为`得`，`地`，最后才是`的`

- 查看飞键的可行性，但在词库中只保留手感最佳的飞键方案（避免无名指、小指与同手）
  - `chao`（`jz`）
  - `che`（`we`）
  - `zhai`（`fh`）
  - `zhao`（`fz`）
  - `zhe`（`fe`）
  - `uang`（与声母不同手的`m`或`x`）

- 查看词组中是否存在多音单字
  - 如读音变化不影响其含义（方言或口语读音），则在词库中只保留手感最佳的读音方案（避免无名指、小指与同手），但在单字中仍保留所有读音所对应的编码
    - 谁（`ew`）
    - 这（`fe`）
    - 那（`ns`）
    - 哪（`ns`）
    - 血（`xh`）
  - 如不同的读音对应的含义不同，则遵循并保留其正确读音所对应的编码
    - 地（`de`，`dk`）
    - 得（`de`，`dw`）
    - 着（`fe`，`fl`）

- 确保改动单字（无论使用简码与否）保留了其对应的单字全码编码

- 测试编码的实际使用情况，确保编码无误且输入效率与可读性没有降低

## 极速跟打器

以新构建的词库为蓝本，本仓库将会同步更新「极速跟打器」所使用的[编码文件](https://github.com/pingshunhuangalex/rime-xkjd/blob/main/%E6%9E%81%E9%80%9F%E8%B7%9F%E6%89%93%E5%99%A8/%E7%BC%96%E7%A0%81%E6%96%87%E4%BB%B6/%E9%94%AE%E9%81%93%C2%B7%E6%88%91%E6%B5%81.txt)以保证词库在实际应用中的有效性。编码生成的步骤为：

- 将所需字词及其编码（不包含生僻单字、偏旁部首、符号等非必要词库）按词库优先级顺序进行集中

- 在标注次选的字词编码后添加次选编码（`'`）并删除首选与次选标注

- 在下列字词的编码后添加空格编码（`_`）
  - 所有简码字词（不包含特殊简码）
  - 编码的声码部分为奇数且无形码的词组
  - 编码的声码部分为声韵（`sy`）且无形码的单字

- 保持含次选词组、简码词组与所有单字的默认编码排列顺序

- 对多字词组按字数（含标点）进行倒序排列，使长度更大词组优先得到映射

- 在词组字数相同的情况下，对该组词组按编码进行倒序排列，使词组映射组合更加准确（不包含简码词组）

- 测试编码的实际使用情况，确保字词映射无误且理论码长结果理想
