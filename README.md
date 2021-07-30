# Rime键道输入法

这个仓库包含了我所有关于[星空键道](https://github.com/xkinput/Rime_JD)的配置与自定义文件。

## 回归初心

键道创始之初，其核心设计理念的一部分便是词库。“质量极高，大而不臃、全而不废，极低的词组打空率”曾一度是其闪光点。时过境迁，因缺乏统一的词库删改标准加上极其有限的审核维护资源，键道词库正渐渐趋于臃肿，怪词废词不断。

由于目前词库的删改逻辑与我的预想相去甚远，极低的更新频率更是使其雪上加霜。思前想后，我决定摒弃官方词库，另起炉灶，打造属于我自己的键道词库。

## 词库删改逻辑

以官方词库为参照，本仓库将从零开始构建键道词库。以下为词库删改逻辑：

- 审核改动字词是否合理且具有复用性与时效性，尊崇“少既是多”的原则而非盲目占用编码空间

- 将改动字词根据其性质与输入方式进行更细致的归类（[查看词库结构](https://github.com/pingshunhuangalex/rime-xkjd/blob/main/xkjd6.extended.dict.yaml)）

- 根据使用情况调整词频，同时调整四周具有相似编码的字词以优化该区域的平均码长

- 视实际编码情况，在不损害输入效率与可读性的前提下，尽可能利用次选位置与简码

- 视实际编码情况，在不损害输入效率与可读性的前提下，尽可能使相同结构的词拥有相同的编码长度

- 查看飞键的可行性，并做出相应的改动

> 以新构建的词库为蓝本，本仓库将会同步更新「极速跟打器」所使用的[编码文件](https://github.com/pingshunhuangalex/rime-xkjd/blob/main/%E6%9E%81%E9%80%9F%E8%B7%9F%E6%89%93%E5%99%A8/%E6%98%9F%E7%A9%BA%E9%94%AE%E9%81%93.txt)以保证词库在实际应用中的有效性。
>
> 更细化的字词归类同时将优化跟打器中的编码提示与可视化，使其优先映射长度更大且码长更小的字词。

---

想要进一步了解这款优雅的中文输入方案？来看看我自制的[Rime键道输入法文档](https://pingshunhuangalex.gitbook.io/rime-xkjd/)吧!
