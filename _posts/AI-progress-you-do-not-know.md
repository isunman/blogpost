---
title: 你所不知道的 AI 进展  
tags: [思考, AI]
categories: 未来探索
date: 2019-10-29 12:02
---

人工智能现在是常见词汇，大多数人可能觉得，它是学术话题，跟普通人关系不大。
但是实际上，AI 突飞猛进，正在脱离实验室，进入日常生活。仅仅是现在的技术水平，就足以模糊现实与虚拟的界限，颠覆一般民众的认知。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102801.jpg)

（图1：2018年10月，世界第一幅 AI 生成的肖像画，[拍卖](https://www.christies.com/features/A-collaboration-between-two-artists-one-human-one-a-machine-9332-1.aspx)成交价43.25万美元。）

为了让普通人了解 AI 的进展，谷歌的机器学习专家格里高利·萨普诺夫（Grigory Sapunov）写了一篇通俗的[科普文章](https://blog.inten.to/welcome-to-the-simulation-dd0d8cb6534d)，介绍目前的技术成果。这盘文章非常精彩，有大量的图片，加上一些简单的解释，信息量很大，对于了解技术动态很有帮助。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102802.jpg)

（图2：谷歌的机器学习专家格里高利·萨普诺夫）
下面就是那篇文章的翻译，比较长，图片很多，但是值得耐心读完。我保证，有些内容一定会让你感到吃惊。

## 一、图像处理

人工智能最早是从图像处理开始的。图像处理是一种常见任务，智能要求比较高，需要使用 PhotoShop 之类的软件人工编辑，一般的算法解决不了。

### 1.1 对象补全

2017年，日本科学家提出了一种[图像的对象补全模型](https://web.archive.org/web/20191016060740/http://iizuka.cs.tsukuba.ac.jp/projects/completion/en/)。经过训练，模型可以补全图片上缺失的部分。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102803.jpg)

（图3：图像的对象补全模型）
上图中，左边是原始图片，然后把中间的花盆涂掉，输入模型。模型会自动补全缺失的部分（右图），由于它不知道，那里有一个花盆，所以只会根据没有涂掉的部分，补上地板和扶手。
下面是更多这样的例子。涂掉的部分，模型都会补上，哪怕它根本不知道，那里原来是什么。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102804.jpg)

（图4：图像的对象补全示例）
Nvidia 公司将这个模型做成了产品，放在网上。你可以到[它的网站](https://www.nvidia.com/research/inpainting/)，上传一张图片，然后涂掉一些部分，让网站替你补全。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102805.jpg)

（图5：涂掉沙发旁边的茶几）
有的[图像软件](https://www.slashgear.com/adobes-entry-level-photoshop-elements-gets-new-ai-powered-tools-04594215/)已经应用这项技术，去除人像脸上的斑点。

### 1.2 背景处理

背景处理指的是，将前景物体从图片分离出来，再对背景进行加工。目前，已经有[很好的智能算法](https://towardsdatascience.com/background-removal-with-deep-learning-c4f2104b3157)可以去除图片背景。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102806.jpg)
（图6：图片的背景去除）
在模型内部，图片会转成像素的色块。下图的浅紫色块就是前景物体，然后再把这些像素提取出来。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102807.jpg)
（图7：背景去除模型）
这个模型也已经做成了[线上服务](https://www.remove.bg/)，大家可以上传图片感受一下它的效果。
既然可以去除背景，那当然就可以[更改背景](https://arxiv.org/abs/1703.03872)，为图片合成打开方便之门。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102808.jpg)
（图8：更改图片背景）

### 1.3 样式转换

人工智能还能够[识别](https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf)图片的风格样式（即像素的变化规律），将其套用在另一张图片。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102809.jpg)
（图9：原始图片）
上图是两张原始图片，第一张是梵高的名画《星夜》，第二张是普通的风景照。模型可以提取第一张图片的风格，将其套用在第二张图片。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102810.jpg)
（图10：套用梵高的《星夜》风格）
其他名画的风格，同样可以套用。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102812.jpg)
![](https://www.wangbase.com/blogimg/asset/201910/bg2019102813.jpg)
（图11：图像的风格转换）

### 1.4 图像着色

一旦识别出图片中的物体，模型就可以统计不同物体的像素颜色规律，然后就能推断黑白照片可能的颜色，从而实现[照片着色](https://arxiv.org/abs/1603.06668)。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102814.jpg)
（图12：黑白照片的着色）
网上也有免费的[着色服务](https://colorize.cc/)，大家可以体验。

## 二、GAN 方法

### 2.1 简介
GAN 是"生成对抗网络"（Generative Adversarial Networks）的缩写，它是一种革命性的提升人工智能模型效果、生成虚拟图像的方法。
原理很简单，就是两个神经网络互相对抗。一个神经网络负责生成虚拟图像，另一个神经网络负责鉴定假图像。理论上，如果 GAN 训练成功，那么生成的假图像与真图像将无法区分。2014年，这种方法提出以后，快速发展，目前效果已经可以乱真。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102815.jpg)
（图13：GAN 的改进速度）
上图是过去几年，GAN 生成的虚拟人像。可以发现，每过一年，图片越来越大，细节越来越丰富，越发接近真实人像。它的工作方法也是如此，第一步生成一张低分辨率图片，然后慢慢放大，依次修改每一个像素，确定该像素怎样才能最大概率通过鉴定器。
GAN 不仅能生成虚拟图像，还能生成音频、文本，甚至是化合物分子。AI 模型可能创造出来的任何东西，都能使用 GAN 提升效果。GitHub 有一个[仓库](https://github.com/hindupuravinash/the-gan-zoo)，专门收集不同用途的 GAN，目前已经有500多种模型。

### 2.2 StyleGAN

目前，生成虚拟人像效果最好的模型是 Nvidia 公司的 [StyleGAN](https://arxiv.org/abs/1812.04948)。下面两张头像，你能分辨哪张是虚拟的，哪张是真实的吗？

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102816.jpg)
（图14：GAN 虚拟人像）
这是网站截图，你可以去[那个网站](http://www.whichfaceisreal.com/)试试看，能猜对多少张。需要提醒的是，这是2018年底的模型产物，随着模型进化，迟早将无法分辨真假。
GAN 不仅能生成人像，实际上可以生成任何图像。下面是 [BigGAN](https://arxiv.org/abs/1809.11096) 模型生成的各种图像，图片里的东西都是不存在的。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102817.jpg)
（图15：BigGAN 模型生成的虚拟图像）

### 2.3 图像翻译

一种图像通过 GAN 转变为另一种图像，称为图像翻译。空拍照片变成地图、黑白照片变成彩色照片，都是图像翻译的例子。
[pix2pix](https://github.com/phillipi/pix2pix) 是图像翻译的开源工具，它可以让黑夜变成白天，示意图变成实物图。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102818.jpg)
（图16：图像翻译）
也可以让春天变成夏天，晴天变成雨天。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102819.jpg)
（图17：图像翻译）
图像翻译的难点在于，它需要有成对的示例（源图像和相应的目标图像），告诉模型应该怎么翻译，这些示例可能很难创建。但是反过来，只要有配对的示例，就可以翻译图像，不管这种翻译是否合理。下面是两只小猫翻译成对应的豹子、狮子和老虎。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102820.jpg)
（图18：图像翻译）
[CycleGAN](https://github.com/junyanz/CycleGAN) 模型还支持跨域翻译，将照片翻译成油画，斑马翻译成马。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102821.jpg)
（图19：图像翻译）
Nvidia 开发了一个 [GauGAN](http://nvidia-research-mingyuliu.com/gaugan) 软件，可以在线试玩。用户只需手绘一个示意图，软件就能生成一张对应的风景照片。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102829.jpg)
（图20：GauGAN 将示意图变成照片）

### 2.4 人像翻译

图像翻译用于人像，就是人像翻译。[StarGAN](https://github.com/yunjey/StarGAN) 模型可以翻译面部属性，比如头发的颜色、性别、肤色等。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102824.jpg)
（图21：脸部属性的改变）
还可以把其他人的表情移植到你的脸上，下图分别是愤怒、快乐、恐惧的表情翻译。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102825.jpg)
（图22：表情的改变）
[SC-FEGAN](https://github.com/run-youngjoo/SC-FEGAN) 是人像翻译的开源软件，可以让你编辑人像，比如加上刘海，去除墨镜等等。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102826.jpg)
![](https://www.wangbase.com/blogimg/asset/201910/bg2019102827.jpg)
（图23：人像编辑软件 SC_FEGAN）

### 2.5 文本到图像生成

GAN 最惊人的成果之一，大概就是[根据文本生成图像](https://arxiv.org/abs/1711.10485)。用户提供一个句子，软件生成对应的图像。原始文本"一只红中透白、长着非常短的尖嘴的鸟"，可以得到下面的图像。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102830.jpg)
（图24：根据文本生成图像）
论文甚至提到，将来存在可能，根据剧本直接生成一部电影。

## 三、视频生成

图像处理逐渐成熟以后，人工智能业界的关注重点就转向了视频。
从一个视频生成另一个视频，这就叫视频翻译。目前比较成熟的两个方向是运动传递和面部交换。

### 3.1 运动传递

运动传递指的是，将一个人的动作（包括身体、眼睛或嘴唇的动作）翻译到另一个人身上，使得另一个人出现一模一样的动作。
2018的论文[《Everybody Dance Now》](https://carolineec.github.io/everybody_dance_now/)，给出了一个模型，可以将舞者的动作移植到任何人身上。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102831.jpg)
（图25：动作传递）
上图中，蓝衣女子的跳舞视频完全是假的，是将左上角舞者的动作套用在她身上，自动生成的。
NVIDIA 公司的开源软件 [vid2vid](https://github.com/NVIDIA/vid2vid) 更为强大，可以生成高分辨率的、连贯的逼真视频。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102832.jpg)
（图26：vidvid 软件）

### 3.2 脸部生成

脸部生成指的是，根据一张脸的表情和动作，重建另一张脸。最著名的例子是虚拟的[奥巴马演讲](http://grail.cs.washington.edu/projects/AudioToObama/)。2017年，华盛顿大学的团队发表了一段奥巴马的演讲视频。奥巴马其实从未做过这个演讲，是将别人的表情和口型套在他脸上生成的，语音也是合成的。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102833.jpg)
（图27：虚拟的奥巴马演讲）
这种伪造的视频被称为 [Deepfake](https://en.wikipedia.org/wiki/Deepfake)（深度伪造），具有很大的欺骗性，许多在线平台都禁止上传这一类视频。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102834.jpg)
（图28：伪造的特朗普演讲，将喜剧演员的表演变成特朗普自己在讲。）

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102837.jpg)
（图29：深度伪造的普京）
2018年出现的[《深度视频肖像》](https://web.stanford.edu/~zollhoef/papers/SG2018_DeepVideo/page.html)更进了一步，生成的视频不局限于虚拟的面部表情，还会头部旋转、眼睛凝视和眨眼，是 3D 的肖像重构。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102835.jpg)
（图29：深度视频肖像）
这些技术还在[继续发展](https://www.theverge.com/2019/6/10/18659432/deepfake-ai-fakes-tech-edit-video-by-typing-new-words)，现在你可以给出任意文本，从任何你指定的对象嘴里说出来。甚至只凭一张照片，就可以生成一段表情变化的视频。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102836.jpg)
（图30：一张照片生成各种表情）

### 3.3 中国的实践

国内的人工智能视频生成，并不落后于国外。换脸应用 ZAO 只需用户上传一张照片，就能把影视剧主人公的脸换掉，好像你本人在表演电影一样。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102838.jpg)
（图31：换脸应用 ZAO）
2018年，新华社与搜狗合作推出了虚拟新闻主播，具有真人的形象，带有声音、面部表情和动作，在电视上播报新闻，已经开通了英语、俄语、阿拉伯语的主持人。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102839.jpg)
（图32：虚拟新闻主播）

### 3.4 视频渲染

除了视频生成，人工智能在视频渲染上也取得了很大进展。
Nvidia 公司2018年展示了实时光线追踪 RTX 技术。这项技术用人工智能预测光线的变化，从而不用耗费大量计算去追踪光线，因此可以实时渲染出高画质的 3D 动画。这对于视频游戏有重大意义。
下面是使用这项技术的 Unreal Engine 4，实时渲染出的一个女子的[3D 动画](https://venturebeat.com/2018/03/21/epic-games-shows-off-amazing-real-time-digital-human-with-siren-demo/)，可以一边计算生成，一边播放，完全没有延迟。

![](https://www.wangbase.com/blogimg/asset/201910/bg2019102840.jpg)
![](https://www.wangbase.com/blogimg/asset/201910/bg2019102841.jpg)
（图32：实时渲染的动画）
实时光线追踪技术还可以用于自动驾驶，在白天和黑夜的不同时间，不同的路面和环境下，预测出暴雨、风雪和强烈的眩光导致的光线变化，对驾驶做出调整。

## 四、文本和声音处理

最后，简单提一下，人工智能在文本和声音处理领域的进展。
#### （1）语音合成
谷歌在2018年推出了智能助手 Google Duplex，它会根据你的日程，自动打电话去餐厅订座位。谷歌 CEO 说，这个机器人的对话能力，使得对方完全没有发现这是机器人。
#### （2）音乐合成
OpenAI 基金会推出的 [MuseNet](https://openai.com/blog/musenet/)，通过学习数十万段 MIDI 音乐，能做到使用10种乐器，生成一段4分钟的音乐。它的官网有这些音乐的下载，相当动听。
#### （3）自动评论
据报道，使用 Yelp 网站的数据进行训练的模型，可以自动生成餐厅评论。

    - 我喜欢这个地方，一直来这里已经好多年。它是与朋友和家人相聚的好地点，我喜欢这里的食物和服务，从未有过糟糕的经历。
    - 我吃了烤蔬菜汉堡配薯条！哦，很好吃！
    - 我和我的家人都是这个地方的忠实粉丝。工作人员超级好，食物也很棒。鸡肉很好，大蒜酱也很完美。配水果的冰淇淋也很美味。强烈推荐！
    - 上面这些都是机器生成的评论。
 
#### （4）智能邮件
Gmail 会根据电子邮件的来信内容，自动生成[三种不同的回复](https://www.blog.google/products/gmail/save-time-with-smart-reply-in-gmail/)，让用户选择。如果只是简单回应，用户不用自己动手写。
Gmail 的[另一个功能](https://ai.googleblog.com/2018/05/smart-compose-using-neural-networks-to.html)是，根据用户已经写的内容，预测接下来会写的句子，供用户选择。

## 五、小结

毫无疑问，人工智能是很酷的技术，创造出了神奇的产品，有着难以想象的巨大应用前景。
但是，人工智能也是一把双刃剑，模糊了现实与虚拟之间的界限，把我们带上了一条不可预测的道路。作为个人，了解这些技术的进展和潜力，有助于保持一份清醒，享受技术之福的同时，避免它带来的一些副作用。
（正文完）

----------

References

[1] 拍卖: https://www.christies.com/features/A-collaboration-between-two-artists-one-human-one-a-machine-9332-1.aspx
[2] 科普文章: https://blog.inten.to/welcome-to-the-simulation-dd0d8cb6534d
[3] 腾讯课堂: https://ke.qq.com/?utm=ruanyifeng
[4] “腾讯课堂101计划”: https://edu.qq.com/a/20190119/005414.htm
[5] 图像的对象补全模型: https://web.archive.org/web/20191016060740/http://iizuka.cs.tsukuba.ac.jp/projects/completion/en/
[6] 它的网站: https://www.nvidia.com/research/inpainting/
[7] 图像软件: https://www.slashgear.com/adobes-entry-level-photoshop-elements-gets-new-ai-powered-tools-04594215/
[8] 很好的智能算法: https://towardsdatascience.com/background-removal-with-deep-learning-c4f2104b3157
[9] 线上服务: https://www.remove.bg/
[10] 更改背景: https://arxiv.org/abs/1703.03872
[11] 识别: https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf
[12] 照片着色: https://arxiv.org/abs/1603.06668
[13] 着色服务: https://colorize.cc/
[14] 仓库: https://github.com/hindupuravinash/the-gan-zoo
[15] StyleGAN: https://arxiv.org/abs/1812.04948
[16] 那个网站: http://www.whichfaceisreal.com/
[17] BigGAN: https://arxiv.org/abs/1809.11096
[18] pix2pix: https://github.com/phillipi/pix2pix
[19] CycleGAN: https://github.com/junyanz/CycleGAN
[20] GauGAN: http://nvidia-research-mingyuliu.com/gaugan
[21] StarGAN: https://github.com/yunjey/StarGAN
[22] SC-FEGAN: https://github.com/run-youngjoo/SC-FEGAN
[23] 根据文本生成图像: https://arxiv.org/abs/1711.10485
[24] 《Everybody Dance Now》: https://carolineec.github.io/everybody_dance_now/
[25] vid2vid: https://github.com/NVIDIA/vid2vid
[26] 奥巴马演讲: http://grail.cs.washington.edu/projects/AudioToObama/
[27] Deepfake: https://en.wikipedia.org/wiki/Deepfake
[28] 《深度视频肖像》: https://web.stanford.edu/~zollhoef/papers/SG2018_DeepVideo/page.html
[29] 继续发展: https://www.theverge.com/2019/6/10/18659432/deepfake-ai-fakes-tech-edit-video-by-typing-new-words
[30] 3D 动画: https://venturebeat.com/2018/03/21/epic-games-shows-off-amazing-real-time-digital-human-with-siren-demo/
[31] MuseNet: https://openai.com/blog/musenet/
[32] 自动生成: https://www.theverge.com/2017/8/31/16232180/ai-fake-reviews-yelp-amazon
[33] 三种不同的回复: https://www.blog.google/products/gmail/save-time-with-smart-reply-in-gmail/
[34] 另一个功能: https://ai.googleblog.com/2018/05/smart-compose-using-neural-networks-to.html

----------

严重声明：本文转载自阮一峰的博客，版权属于原作者所有。
[原文链接](http://www.ruanyifeng.com/blog/2019/10/artificial-intelligenence.html)。


