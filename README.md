# sd2.5--Enhanced-Human-Likeness
Seedance 2.5真人感带货视频技能，整合「去AI感」与「去广告感」相关优化。四大真实感支持（混合光源、生活杂物、纹理纹理、手机拍摄）+六条核心语句+谴责轰炸+三段锁定+结尾质量指令块+15–25秒带货四段式脚本。当用户需要：(1)做AI真人带货/UGC口播/种草视频，(2)让AI视频更真实更真实的手机实拍、降低AI味和广告感，(3)排查塑料皮肤、崩坏手多指、视觉指示、口型不同步、跨镜头崩脸图、画面冒乱码文字与logo、假冒头，(4)写或优化Seedance提示词，(5)让角色在多镜头间保持一致，(6)设计带货口播脚本钩子与节奏时使用。
Seedance 2.5 真人感带货视频
核心矛盾：AI带货视频有两个死穴——「瞬间AI」（塑料皮肤、崩手、假光）和「瞬间广告」（棚拍打光、干净桌面、完美构图）。两者要同时躲开。

解法是逆向优化：不追求精致，主动制造真实世界的不完美。欠指定的提示词，模型一定取通用默认值填——那就是AI味的起源。

核心能力：Seedance 2.5单次30秒（可延长至90秒）、最多50个参考素材、原创4K、单次生成内可处理场景切换。带货建议单段15-25秒直出，不可拆段——拼接处的色调跳变本身就是AI味源。

实测基线：乱码文字规避100%（N=12）、认知稳定性95、角色跨镜头一致性92、手部调整正确性89。

一、核心模块语句库（全部默认加上）
不要等出问题才加。预打补丁并不会增加提示词复杂度，但会显着降低重抽率。

AI痕迹	直接粘贴这句话
塑料/过度磨皮	Skin shows natural texture with pores and subtle imperfections, not over-smoothed plastic.
AI-art 玻璃轮廓	Documentary realism throughout, NOT AI-art aesthetic, NOT 3D render, NOT illustration.
崩手 / 多指 / 手粘连	Hands have natural anatomy with five fingers and correct proportions.
眼神照明 / 靠近	Eyes remain stable and focused without flickering or jitter.
中文口型	Mouth movement strictly synchronized to dialogue per shot — closed and still otherwise. Lip-sync precise to each Mandarin syllable.
品牌名读错	Word pronunciation: "[品牌]" pronounced as "[音标]".
物质间背景	Same room as Segment A.
中文版（写中文提示词时用）：

皮肤有自然纹理、可见毛孔和细微瑕疵，不是光滑塑料感，不要过度磨皮。
纪实写实风格贯穿全片，不要 AI 绘画质感，不要 3D 渲染感，不要插画感。
手部解剖自然，五指完整、比例正确。
眼神稳定聚焦，无闪烁无抖动。
口型严格对应每句台词，不说话时闭合静止；对准每个中文音节。
二、四大真实感支柱
支持1·光源：混合光源
通用灯光是最大的人工智能味源。均匀受光不存在于现实世界，现实一定有明暗。

必须指定三件事：色温（warm 3000K key light）、方向（side light from camera-left）、亮度（soft, diffused或hard, contrasty）。

❌ professional lighting / studio lighting / 三点布光 / 柔光箱

✅ Mix lighting: cool daylight from a window on camera-left combined with
   a warm overhead household lamp. Color temperatures clash naturally,
   creating uneven shadows across the face. Natural falloff, no fill light.
进阶（更真实）：指定可信唯一光源，比三点布光真实剃须：

仅靠窗边自然光，光从窗户侧壁进入，右半边脸自然沉入遮挡，无补光
只有头顶一盏暖色吸顶灯，上方受光、下颌有自然投影
落地窗余光 + 手机屏幕冷光反射在侧面
选择真实感照明的灯光方案：自然天光（纪实感最强）>实景光源（画面里能看见灯具/屏幕）>蓝调时刻/阴天（冷调漫射，中性）>三点布光（影棚感，偏「制作过」）。

避免：无来源的均匀亮光、说不出方向的柔光、雨水过头的彩色光。

提案 2 · 场景：主动塞杂物
clean background是时装。关键是「用过的痕迹」、「摆好的道具」：

假（摆拍感）	真实（生活感）
整齐叠放的毛巾	揉皱随手放的纸巾
未开封的包装盒	拆开一半、胶带翘起的快递袋
空咖啡杯	喝了一半、杯壁有水痕的咖啡杯
摆正的手机	屏幕朝下扣着+缠着的充电线
空白	贴了便利贴、有插座和电线的墙
Lived-in cluttered background: a half-finished coffee mug with visible
stains, an opened express delivery bag with tape peeling off, a crumpled
tissue tossed nearby, a tangled charging cable, a few receipts.
NOT a styled set, NOT a clean background.
Pro 3 · 皮肤：活力要毛孔
观众第一眼察觉「不对」的地方。

Skin has visible texture and pores, natural uneven skin tone with slight
redness on cheeks and nose, faint under-eye shadows, a few small blemishes.
Real human skin, NOT smoothed, NOT retouched, NOT plastic, NOT CGI.
提案 4·镜头：指定手机拍摄
打破「精致广告片」惯性最快的一招，就写。四大要素缺一不可：

Shot on iPhone, handheld with subtle natural shake, slight motion blur,
composition slightly off-center, casual framing, vertical 9:16.
Amateur home-video feel.
可大幅：（slight lens smudge镜头脏污）、auto-exposure hunting（自动曝光调整）、slight rolling shutter wobble（果冻效果）。

完美无瑕的画面本身就是AI特征——微小的镜头凹陷、光晕、呼吸感都显着提升了真实度。

三、反向轰炸（治画面幻觉出文字/logo + 广告感）
单条NO text会被软性理解，超过 5 条以上将被视为硬约束。 带货场景必然「去广告感」和「去 AI 感」立即词一起堆：

professional photography, studio lighting, softbox, three-point lighting,
perfect skin, flawless, retouched, symmetrical, centered composition,
clean background, minimalist set, 3D render, CGI, oversaturated,
hyperreal, AI-art aesthetic, illustration, plastic skin, over-smoothed,
NO text, NO Chinese characters, NO English text, NO numbers, NO logos,
NO UI elements, NO recognizable symbols, NO punctuation
前半段砍广告感，后半段砍AI感。

实测数据：1条否定 → 47% 出现乱码文字；3条 → 18%；6条以上 → 0%（N=12）。

放置位置：既要写在对应镜头块内，也要在提示词结尾重复重复。模型生成每帧前会重读最后一段，近因效应下结尾规则的激活强度大致埋在中段的3倍。

配位：正向替代（关键）
只说「不要」会留下空白，模型会用变体填回来。每条重要的 NO 都要配一条「要什么」：

❌ 浮动卡片。卡片上不要有文字。

✅ 柔和抽象的发光矩形悬浮在右侧边缘（紫/粉/蓝渐变色调，
   无可识别图案或文字），卡片呈失重半透明状，暗示全息数据。
   NO text, NO characters, NO numbers, NO logos, NO UI elements.
对文字、标志、品牌标记、肤色、光线、背景这些真正重要的内容，否定和正向描述都要保留。

确实需要屏幕文字时
不要指望模型写对。在AI外部生成再合成：

HTML 做版 → 无头浏览器截图 → 当首帧图喂进去
用真实拍摄的招牌照片
后期用剪辑软件崛起
四、三段锁定（制作跨镜头崩脸基础）
把角色/场景/声音提到的镜头脚本之前的独立块。模型把置顶块设置为架构（全局恒真事实）而不是叙述细节。

实测：三段锁定置顶→7个镜头角色一致性92分；同样细节内联写在每个镜头里→掉到68分。

[Character Lock — 名字]
6–8 行具体外观：体型 / 年龄 / 发型 / 眼镜 / 服装 / 配饰。
所有 N 个镜头保持同一套服装与外观。
皮肤有自然纹理和可见毛孔，不是光滑塑料感。

[Setting Lock]
环境 + 光源方向 + 色温 + 道具 + 空间构图。
所有镜头同一场景。

[Voice Lock]
语言 / 口音 / 年龄段 / 音色 + 音频行为规则（口型同步、停顿模式）。
做系列带货内容时，把这三块存成可重复用的头部。第二条视频用两个的字符锁定和设置锁定，人设一致自动提醒。

五、带货剧本结构（15–25秒四段式）
段落	时长	写法要点
钩子	前 2 秒	具体数字/反常识/直接人群/从动作中段切入
痛点	3–8 秒	说场景不说形容词——「每次挤地铁妆就花」胜过「持妆不好」
展示	8–18 秒	手抓真实产品、可见效果变化
行动	最后3秒	一句话说清怎么买
口播真实感：句子4–12字（长句必然拉低口型准确率）、允许口语碎词（「就是」「其实」「你懂吧」）、不要排比押韵（那是广告腔）、语速指定偏慢。

手部规避：手部是已知的弱项。用「控制」「放桌面推近」这类简单动作，避免转动、翻面、多指精细操作——非必要不写手部动作。

运镜要给量：

说时长：slow push-in over 3 seconds，不要只说push-in
说幅度：subtle 1.05x zoom，不要只说zoom
说时机：push-in starts at 1s, ends at shot end
六、结束质量指令块（构成）
[Quality directives]
[角色名]的面部特征在全部 N 个镜头中保持一致——同一张脸、同样的发型角度、
同样的眼镜、同样的服装与配饰。

Hands have natural anatomy with five fingers and correct proportions.
Skin shows natural texture with pores and subtle imperfections, not
over-smoothed plastic.
Eyes remain stable and focused without flickering or jitter.
Mouth movement strictly synchronized to dialogue per shot — closed and
still otherwise. Lip-sync precise to each Mandarin syllable.

光照全程与[光源]一致。

NO text, NO Chinese characters, NO English text, NO numbers,
NO logos, NO UI elements, NO recognizable symbols.

Documentary realism throughout, NOT AI-art aesthetic, NOT 3D render,
NOT illustration. NOT professional advertising footage.
实测：带末端质量指令的生成，AI玻璃皮肤痕迹降低12%，手部解剖改善8%，不良指令表皮率100%（不带时78%）。

七、提示词排列顺序
三段锁定（角色/设定/语音锁定，独立置顶区块）
镜头声明（提案4，开头就写）
光线（旋转1）
场景杂物（提案2）
皮肤纹理+核心皮肤语句（支持3+第一章）
动作与口播台词（四段式，逐段带时间轴与运镜量）
结束质量指令区块 + 负面轰炸（第六章，重申）
八、症状 → 修复对照表
症状	根因	修复
简短就是广告片	棚拍光+整洁台面+完美构图	换混合光/单一光源+塞生活杂物+构图偏心+声明手机拍摄
皮肤像塑料 / 玻璃 / CGI	模型默认审美偏「美颜」	正向描述纹理+拒绝AI-art风格，两句都要
光线假、脸上没阴影	均匀受光无来源	光源色温冲撞，或混合单一光源+no fill light
背景太空像影棚	欠指定，模型给默认干净场	逐件上市带使用痕迹的杂物+负向词加clean background
画面齐全锐利完美	缺镜头照射	加slight motion blur+ handheld shake+lens smudge
镜头间人脸变了	锁定不足，细节内联埋在镜头里	字符锁提到的设置顶独立块+结束符+首尾帧定
眼神一直在颤	模型默认给予「有趣」的眼部动画	添加稳定语句
手指数量正确	已知弱点，动态中尤甚	加手部解剖语句 + 改用简单静脉
口型对不上（中文尤其）	模型默认按英文音素	准确指定语言口音（如Mandarin, Taiwan accent）+音节级同步+放慢语速+每周句子
画面冒出乱码文字/logo	模型倾向于「填充」细节	轰炸轰炸6条以上，镜头块与结尾各写一遍
立体拼接处画面	段间背景	加Same room as Segment A.+ 转场时长从 0.4s 加到 0.6–0.8s
多段色调不统一	各段独立生成	晚期统一LUT
确实需要屏幕文字	模型能力外	高层亮度，或 HTML 截图当首帧图
后期统一调色（最后一个关）：多段生成的素材色调必然有差异。用同一套LUT压过去——稍微去保湿+遮光偏蓝品红+一点胶片颗粒——让所有镜头外观像同一台机器拍的。这一下能救回很多素材。

九、重抽3次还没怎么办
问题可能不在提示词，而在模型：

换生成档位——不同推理路径表现有差异
转换分辨率——有时低分辨率反而更稳定
换参考图——首帧图可能在跟提示词打架
换模型——不同模型的舒适区不同
十、容量上限（生成前就说清楚）
维度	快速档上限
自然度/去AI感	70–80
中文口型同步	70-85%
超过5次剪辑的多镜头	65–80% 精度
跨角色镜头一致性	80-90%
不要事后解释，生成前置愿景。

十一、提交前自查
五条皮肤语句是否全加（皮肤/手/眼/口型/纪实风格）
负面否定是否堆到6条以上，且镜头块与结尾各写一遍
去广告感负向词是否加了（摄影棚灯光/干净的背景/完美的皮肤/居中构图）
三段锁定是否置顶成独立区块，而非镜头里内联
终结是否有[Quality directives]区块加密关键规则
灯光是否指定了色温+方向+亮度，且为混合光或单一可信光源
背景 逐件上市是否带有使用痕迹的杂物
是否声明了手机拍摄四要素（支持晃动 / 模糊动态 / 构图偏心 / 竖屏）
运镜是否给了时长和幅度
是否注意到了复杂的手部动作
口播句子是否控制在4-12字、语速偏慢
钩子是否在前2秒落地
任意一个没勾，提示词就是欠指定的，模型会取通用默认值填——那就是AI味的来源。

