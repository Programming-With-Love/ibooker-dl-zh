# 前言

> “我不能创造的东西，我就不理解。”
> 
> 理查德·费曼

生成式人工智能是我们这个时代最具革命性的技术之一，改变了我们与机器互动的方式。它有潜力彻底改变我们生活、工作和娱乐的方式，已经成为无数对话、辩论和预测的主题。但如果这种强大技术还有更大的潜力呢？生成式人工智能的可能性是否超出了我们当前的想象？生成式人工智能的未来可能比我们想象的更令人兴奋...

自我们早期以来，我们一直在寻找创造原创和美丽作品的机会。对早期人类来说，这体现在洞穴壁画上，描绘着野生动物和抽象图案，用谨慎和有条不紊地放置在岩石上的颜料创作而成。浪漫主义时代赋予我们柴可夫斯基交响曲的掌握，通过声波激发胜利和悲剧感情的能力，编织在一起形成美丽的旋律和和谐。最近，我们发现自己在午夜赶往书店购买关于虚构巫师的故事，因为字母的组合创造了一个叙述，激励我们翻开页面，看看我们的英雄会发生什么。

因此，毫不奇怪，人类已经开始提出创造力的终极问题：我们能否创造出本身具有创造力的东西？

这就是生成式人工智能试图回答的问题。随着方法和技术的最新进展，我们现在能够构建能够以给定风格绘制原创艺术作品、写出有长期结构的连贯文本块、创作令人愉悦的音乐，以及通过生成虚构未来场景来制定复杂游戏的获胜策略的机器。这只是生成式革命的开始，将迫使我们不得不寻找关于创造力机制的一些最大问题的答案，最终，这意味着什么是人类。

简而言之，现在学习生成式人工智能再也没有比现在更好的时机了，所以让我们开始吧！

# 目标和方法

本书假设读者对生成式人工智能没有先前的知识。我们将从头开始逐步建立所有关键概念，以一种直观易懂的方式进行讲解，所以如果你对生成式人工智能没有经验也不用担心。你来对地方了！

本书不仅涵盖当前流行的技术，还作为生成建模的完整指南，涵盖了广泛的模型系列。没有一种技术在客观上比其他技术更好或更差——事实上，许多最先进的模型现在混合了来自生成建模各种方法的想法。因此，重要的是要及时了解生成式人工智能各个领域的发展，而不是专注于某一种特定的技术。有一点是肯定的：生成式人工智能领域发展迅速，你永远不知道下一个突破性想法将从何而来！

考虑到这一点，我将采取的方法是向您展示如何在自己的数据上训练自己的生成模型，而不是依赖预训练的现成模型。虽然现在有许多令人印象深刻的开源生成模型可以下载并在几行代码中运行，但本书的目的是从第一原则深入挖掘它们的架构和设计，以便您完全了解它们的工作原理，并可以使用 Python 和 Keras 从头开始编写每种技术的示例。

总的来说，这本书可以被看作是当前生成式人工智能领域的地图，涵盖了理论和实际应用，包括文献中关键模型的完整工作示例。我们将逐步演示每个步骤的代码，清晰地标明代码如何实现支撑每种技术的理论。这本书可以从头到尾阅读，也可以作为您随时查阅的参考书。最重要的是，我希望您觉得这本书有用且愉快！

###### 注意

在整本书中，您将找到一些简短的寓言故事，帮助解释我们将构建的一些模型的机制。我认为教授新的抽象理论的最佳方法之一是首先将其转化为不那么抽象的东西，比如一个故事，然后再深入技术解释。故事和模型解释只是在两个不同领域中解释相同机制，因此在学习每个模型的技术细节时，参考相关故事可能会很有帮助！

# 先决条件

这本书假定您有 Python 编程经验。如果您对 Python 不熟悉，最好的起点是通过[LearnPython.org](https://www.learnpython.org)开始。在线有许多免费资源，可以让您掌握足够的 Python 知识，以便使用本书中的示例。

另外，由于一些模型使用数学符号描述，对线性代数（例如矩阵乘法）和一般概率论有扎实的理解将会很有帮助。一本有用的资源是 Deisenroth 等人的书籍[*Mathematics for Machine Learning*](https://mml-book.com)（剑桥大学出版社），可以免费获取。

本书假定您对生成建模（我们将在第一章中探讨关键概念）或 TensorFlow 和 Keras 没有先验知识（这些库将在第二章中介绍）。

# 路线图

这本书分为三个部分。

第一部分是生成建模和深度学习的一般介绍，我们在其中探讨了贯穿本书后续部分所有技术的核心概念：

+   在第一章，“生成建模”中，我们定义生成建模，并考虑一个玩具示例，我们可以用来理解一些对所有生成模型都重要的关键概念。我们还列出了我们将在本书的第二部分中探索的生成模型家族的分类法。

+   在第二章，“深度学习”中，我们通过使用 Keras 构建我们的第一个多层感知器（MLP）来开始探索深度学习和神经网络。然后，我们将其调整以包括卷积层和其他改进，以观察性能上的差异。

第二部分介绍了我们将用于构建生成模型的六种关键技术，每种技术都有实际示例：

+   在第三章，“变分自编码器”中，我们考虑变分自编码器（VAE），看看它如何用于生成人脸图像，并在模型的潜在空间中在人脸之间进行变形。

+   在第四章，“生成对抗网络”中，我们探索生成对抗网络（GAN）用于图像生成，包括深度卷积 GAN，条件 GAN 以及改进的 Wasserstein GAN，使训练过程更加稳定。

+   在第五章，“自回归模型”中，我们将注意力转向自回归模型，从介绍循环神经网络（如长短期记忆网络（LSTM））开始，用于文本生成，以及用于图像生成的 PixelCNN。

+   在第六章“归一化流模型”中，我们专注于归一化流，包括对该技术的直观理论探索以及如何构建 RealNVP 模型生成图像的实际示例。

+   在第七章“基于能量的模型”中，我们涵盖了基于能量的模型，包括如何使用对比散度进行训练以及如何使用 Langevin 动力学进行采样等重要方法。

+   在第八章“扩散模型”中，我们深入探讨了构建扩散模型的实用指南，这些模型驱动着许多最先进的图像生成模型，如 DALL.E 2 和 Stable Diffusion。

最后，在第三部分中，我们基于这些基础探索了最先进的图像生成、写作、音乐创作和基于模型的强化学习模型的内部运作：

+   在第九章“Transformer”中，我们探讨了 StyleGAN 模型的渊源和技术细节，以及其他用于图像生成的最先进 GANs，如 VQ-GAN。

+   在第十章“高级 GANs”中，我们考虑了 Transformer 架构，包括一个实用的指南，教你如何构建自己的 GPT 版本用于文本生成。

+   在第十一章“音乐生成”中，我们将注意力转向音乐生成，包括如何处理音乐数据以及应用技术如 Transformers 和 MuseGAN 的指南。

+   在第十二章“世界模型”中，我们看到生成模型如何在强化学习的背景下使用，应用世界模型和基于 Transformer 的方法。

+   在第十三章“多模态模型”中，我们解释了四种最先进的多模态模型的内部运作，这些模型结合了多种类型的数据，包括 DALL.E 2、Imagen 和 Stable Diffusion 用于文本到图像生成以及 Flamingo，一种视觉语言模型。

+   在第十四章“结论”中，我们回顾了迄今为止生成式人工智能的关键里程碑，并讨论了生成式人工智能将如何在未来几年彻底改变我们的日常生活方式。

# 第二版的变化

感谢所有阅读本书第一版的人们——我很高兴看到这么多人发现它是一个有用的资源，并提供了关于第二版中希望看到的内容的反馈。自 2019 年第一版出版以来，生成式深度学习领域取得了显著进展，因此除了更新现有内容外，我还添加了几个新章节，以使材料与当前的最新技术保持一致。

以下是关于各个章节和整体书籍改进的主要更新摘要：

+   第一章现在包括了有关不同生成模型家族的部分以及它们之间关系的分类法。

+   第二章包含了改进的图表和更详细的关键概念解释。

+   第三章通过一个新的实例和相关解释进行了更新。

+   第四章现在包括了对条件 GAN 架构的解释。

+   第五章现在包括了有关图像自回归模型（例如 PixelCNN）的部分。

+   第六章是一个全新的章节，描述了 RealNVP 模型。

+   第七章也是一个新章节，重点介绍了诸如 Langevin 动力学和对比散度等技术。

+   第八章是一个新撰写的章节，介绍了驱动当今许多最先进应用的去噪扩散模型。

+   第九章是第一版结尾提供的材料的扩展，更深入地关注了各种 StyleGAN 模型的架构以及关于 VQ-GAN 的新材料。

+   第十章是一个探索 Transformer 架构细节的新章节。

+   第十一章包括现代 Transformer 架构，取代了第一版中的 LSTM 模型。

+   第十二章包括更新的图表和描述，其中有一节介绍了这种方法如何影响当今最先进的强化学习。

+   第十三章是一个新章节，详细解释了像 DALL.E 2、Imagen、Stable Diffusion 和 Flamingo 这样令人印象深刻的模型是如何工作的。

+   第十四章已更新，以反映自第一版以来该领域取得的杰出进展，并更全面详细地展示生成式人工智能未来的发展方向。

+   所有对第一版的反馈和发现的拼写错误都已经得到了解决（尽我所知！）。

+   每章的开头都添加了章节目标，这样您在开始阅读之前就可以看到章节涵盖的关键主题。

+   一些寓言故事已经被重新编写，更加简洁和清晰——我很高兴许多读者说这些故事帮助他们更好地理解关键概念！

+   每章的标题和副标题都已对齐，以便清楚地显示章节中哪些部分是解释重点，哪些部分是关于构建自己模型的重点。

# 其他资源

我强烈推荐以下书籍作为机器学习和深度学习的一般介绍：

+   [*使用 Scikit-Learn、Keras 和 TensorFlow 进行实践机器学习：构建智能系统的概念、工具和技术*](https://learning.oreilly.com/library/view/hands-on-machine-learning/9781098125967) by Aurélien Géron（O’Reilly）

+   *《Python 深度学习》* by Francois Chollet（Manning）

这本书中的大部分论文都是通过[arXiv](https://arxiv.org)获取的，这是一个免费的科学研究论文库。现在，作者们通常会在论文完全经过同行评审之前将论文发布到 arXiv 上。查看最新提交的论文是了解该领域最前沿发展的绝佳方式。

我还强烈推荐网站[Papers with Code](https://paperswithcode.com)，在那里您可以找到各种机器学习任务中最新的最先进结果，以及指向论文和官方 GitHub 存储库的链接。这是一个极好的资源，适合任何想快速了解当前哪些技术在各种任务中取得最高分数的人，并且肯定帮助我决定在本书中包含哪些技术。

# 本书中使用的约定

本书中使用了以下排版约定：

*斜体*

指示新术语、URL、电子邮件地址、文件名和文件扩展名。

`等宽`

用于命令和程序清单，以及在段落中引用程序元素，如变量或函数名。

*`等宽斜体`*

显示应该用用户提供的值或上下文确定的值替换的文本。

###### 提示

这个元素表示一个提示或建议。

###### 注意

这个元素表示一个一般性说明。

###### 警告

这个元素表示一个警告或注意。

# 代码库

本书中的代码示例可以在 GitHub [存储库](https://github.com/davidADSP/Generative_Deep_Learning_2nd_Edition)中找到。我特意确保没有任何模型需要大量的计算资源来训练，这样您就可以开始训练自己的模型，而不必花费大量时间或金钱购买昂贵的硬件。如果需要，存储库中有一个全面的指南，介绍如何使用 Docker 开始以及如何在 Google Cloud 上设置带有 GPU 的云资源。

自第一版以来，对代码库进行了以下更改：

+   现在所有示例都可以在单个笔记本中运行，而不是从代码库中导入模块。这样您可以逐个单元格运行每个示例，并深入了解每个模型是如何逐步构建的。

+   每个笔记本的部分现在在示例之间基本对齐。

+   本书中的许多示例现在利用了来自惊人的[开源 Keras 存储库](https://oreil.ly/1UTwa)的代码片段，这是为了避免创建一个完全独立的 Keras 生成 AI 示例的开源存储库，因为 Keras 网站已经有了优秀的实现。我在整本书和存储库中添加了参考和链接，指向我从 Keras 网站中利用的代码的原始作者。

+   我添加了新的数据来源，并改进了第一版的数据收集过程——现在，有一个脚本可以轻松运行，从所需的来源收集数据，以便训练本书中的示例，使用诸如[Kaggle API](https://oreil.ly/8ibPw)之类的工具。

# 使用代码示例

补充材料（代码示例、练习等）可在[*https://github.com/davidADSP/Generative_Deep_Learning_2nd_Edition*](https://github.com/davidADSP/Generative_Deep_Learning_2nd_Edition)下载。

如果您有技术问题或在使用代码示例时遇到问题，请发送电子邮件至*bookquestions@oreilly.com*。

本书旨在帮助您完成工作。一般来说，如果本书提供了示例代码，您可以在程序和文档中使用它。除非您复制了代码的大部分内容，否则无需征得我们的许可。例如，编写一个使用本书中几个代码块的程序不需要许可。销售或分发 O’Reilly 图书中的示例需要许可。通过引用本书回答问题并引用示例代码不需要许可。将本书中大量示例代码合并到产品文档中需要许可。

我们感谢您的致谢，但不要求。致谢通常包括标题、作者、出版商和 ISBN。例如：“*生成式深度学习*，第 2 版，作者 David Foster（O’Reilly）。版权所有 2023 年应用数据科学合作伙伴有限公司，978-1-098-13418-1。”

如果您认为您使用的代码示例超出了合理使用范围或上述许可，请随时联系我们*permissions@oreilly.com*。


# 致谢

有很多人我想要感谢他们帮助我写这本书。

首先，我想感谢所有抽出时间来技术审查这本书的人，特别是 Vishwesh Ravi Shrimali、Lipi Deepaakshi Patnaik、Luba Elliot 和 Lorna Barclay。还要感谢 Samir Bico 帮助审查和测试伴随这本书的代码库。你们的意见和建议是无价的。

此外，特别感谢我的同事们在[Applied Data Science Partners](https://adsp.ai)，Ross Witeszczak、Amy Bull、Ali Parandeh、Zine Eddine、Joe Rowe、Gerta Salillari、Aleshia Parkes、Evelina Kireilyte、Riccardo Tolli、Mai Do、Khaleel Syed 和 Will Holmes。感谢你们在我完成这本书时对我的耐心，我非常期待我们将来一起完成的所有机器学习项目！特别感谢 Ross——如果我们没有决定一起创业，这本书可能永远不会成形，所以感谢你相信我作为你的商业伙伴！

我还要感谢任何曾经教过我任何数学知识的人——我在学校非常幸运地有出色的数学老师，他们培养了我对这门学科的兴趣，并鼓励我在大学进一步深造。我要感谢你们的奉献和不辞辛劳地与我分享你们对这门学科的知识。

非常感谢 O'Reilly 的工作人员在引导我写这本书的过程中。特别感谢 Michele Cronin，在每一步都在那里，提供有用的反馈并发送友好的提醒，让我继续完成章节！还要感谢 Nicole Butterfield、Christopher Faucher、Charles Roumeliotis 和 Suzanne Huston 将这本书制作出版，以及 Mike Loukides 首先联系我询问我是否有兴趣写书。你们从一开始就对这个项目非常支持，我要感谢你们为我提供一个平台，让我写我热爱的事物。

在写作过程中，我的家人一直是我不断鼓励和支持的源泉。非常感谢我的妈妈 Gillian Foster，她检查了每一行文字中的拼写错误，并教会我如何首先进行加法运算！你的注重细节在校对这本书时非常有帮助，我真的很感激你和爸爸给予我的所有机会。我的爸爸 Clive Foster 最初教会了我如何编程——这本书充满了实用示例，这要归功于他在我十几岁时在 BASIC 中摸索时的耐心，试图制作足球游戏。我的哥哥 Rob Foster 是你能找到的最谦逊的天才，尤其在语言学领域——和他聊天关于人工智能和基于文本的机器学习的未来一直非常有帮助。最后，我要感谢我的奶奶，她一直是我们所有人的灵感和乐趣源泉。她对文学的热爱是我第一次决定写书会是一件令人兴奋的事情的原因之一。

我还想感谢我的妻子 Lorna Barclay。在写作过程中，除了给我无尽的支持和茶水外，你还细致地检查了这本书的每一个字。没有你，我无法完成这本书。感谢你一直在我身边，让这段旅程变得更加愉快。我保证在书出版后的几天内，我不会在餐桌上谈论生成式人工智能。

最后，我要感谢我们可爱的宝贝女儿 Alina，在写书的漫长夜晚里给予无尽的娱乐。你可爱的笑声成为我打字时完美的背景音乐。谢谢你给予我的灵感，让我时刻保持警惕。你才是这次行动的真正智囊。