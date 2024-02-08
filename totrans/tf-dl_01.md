# 第一章：深度学习简介

深度学习已经彻底改变了技术行业。现代机器翻译、搜索引擎和计算机助手都是由深度学习驱动的。随着深度学习将其影响扩展到机器人技术、制药业、能源以及当代技术的所有其他领域，这一趋势只会继续发展。对于现代软件专业人员来说，发展对深度学习原理的工作知识正在迅速变得至关重要。

在本章中，我们将向您介绍深度学习的历史，以及深度学习对研究和商业社区产生的更广泛影响。接下来，我们将介绍一些最著名的深度学习应用。这将包括突出的机器学习架构和基本的深度学习原语。最后，我们将简要展望深度学习在未来几年将走向何方，然后在接下来的几章中深入探讨 TensorFlow。

# 机器学习正在吞噬计算机科学

直到最近，软件工程师们去学校学习了许多基本算法（图搜索、排序、数据库查询等）。毕业后，这些工程师会走出校门，将这些算法应用到系统中。如今的数字经济大部分是建立在由几代工程师辛苦拼凑在一起的复杂基本算法链上的。大多数这些系统无法自适应。所有的配置和重新配置都必须由经过高度训练的工程师执行，使系统变得脆弱。

机器学习承诺通过使系统能够动态适应来改变软件开发领域。部署的机器学习系统能够从示例数据库中学习所需的行为。此外，这些系统可以在新数据到来时定期重新训练。由机器学习驱动的非常复杂的软件系统能够在不对其代码进行重大更改的情况下显着改变其行为（只需对其训练数据进行更改）。随着机器学习工具和部署变得越来越简单，这一趋势只会加速发展。

随着软件工程系统行为的改变，软件工程师的角色也将发生变化。在某种程度上，这种转变将类似于在开发编程语言之后发生的转变。最初的计算机是经过艰苦编程的。电线网络被连接和互连。然后设置了打孔卡，以便在不更改计算机硬件的情况下创建新程序。在打孔卡时代之后，第一个汇编语言被创建。然后是高级语言如 Fortran 或 Lisp。随后的开发层次创建了像 Python 这样的非常高级语言，具有复杂的预编码算法生态系统。现代计算机科学甚至依赖于自动生成的代码。现代应用程序开发人员使用诸如 Android Studio 之类的工具自动生成他们想要制作的大部分代码。每一波简化的连续浪潮都通过降低进入门槛扩大了计算机科学的范围。

机器学习承诺进一步降低障碍；程序员很快将能够通过改变训练数据来改变系统的行为，可能甚至不需要编写一行代码。在用户端，基于口语和自然语言理解的系统，如 Alexa 和 Siri，将允许非程序员执行复杂的计算。此外，由 ML 驱动的系统可能会更加*鲁棒*，抵抗错误。重新训练模型的能力意味着代码库可以缩小，可维护性将增加。简而言之，机器学习很可能会彻底颠覆软件工程师的角色。今天的程序员将需要了解机器学习系统学习的方式，并需要了解常见机器学习系统中出现的错误类别。此外，他们需要了解支撑机器学习系统的设计模式（与传统软件设计模式在风格和形式上非常不同）。而且，他们需要了解足够的张量微积分，以了解为什么一个复杂的深度架构在学习过程中可能会出现问题。毫不夸张地说，理解机器学习（理论和实践）将成为未来十年每个计算机科学家和软件工程师都需要掌握的基本技能。

在本章的其余部分，我们将快速介绍现代深度学习的基础知识。本书的其余部分将更深入地讨论我们在这里提到的所有主题。

# 深度学习基元

大多数深度架构是通过组合和重组一组有限的架构基元构建的。这些基元通常称为神经网络层，是深度网络的基础构建模块。在本书的其余部分，我们将深入介绍这些层。然而，在本节中，我们将简要概述许多深度网络中常见的模块。本节并不旨在对这些模块进行全面介绍。相反，我们的目标是快速概述复杂深度架构的基本构建模块，以激发您的兴趣。深度学习的艺术在于组合和重组这些模块，我们希望向您展示语言的字母表，让您开始深度学习专业知识之路。

## 全连接层

一个全连接网络将一系列输入转换为一系列输出。这种转换被称为全连接，因为任何输入值都可以影响任何输出值。即使对于相对较小的输入，这些层也会有许多可学习的参数，但它们具有一个很大的优势，即假设输入中没有结构。这个概念在图 1-1 中有所说明。

![images/FCLayer@2x.png](img/tfdl_0101.png)

###### 图 1-1. 一个全连接层。入站箭头代表输入，出站箭头代表输出。互连线的粗细代表学习权重的大小。全连接层通过学习规则将输入转换为输出。

## 卷积层

卷积网络假设其输入具有特殊的空间结构。特别是，它假设在空间上彼此接近的输入在语义上是相关的。这种假设对于图像来说最有意义，因为彼此接近的像素很可能在语义上是相关的。因此，卷积层在深度架构中用于图像处理的广泛应用。这个概念在图 1-2 中有所说明。

就像全连接层将列表转换为列表一样，卷积层将图像转换为图像。因此，卷积层可用于执行复杂的图像转换，例如在照片应用程序中应用艺术滤镜。

![images/depthcol.jpeg](img/tfdl_0102.png)

###### 图 1-2. 卷积层。左侧的红色形状代表输入数据，而右侧的蓝色形状代表输出。在这种情况下，输入的形状为（32，32，3）。也就是说，输入是一个 32 像素乘 32 像素的图像，有三个 RGB 颜色通道。红色输入中的突出区域是“局部感受野”，一组一起处理以创建蓝色输出中的突出区域的输入。

## 循环神经网络层

循环神经网络（RNN）层是一种原语，允许神经网络从输入序列中学习。该层假设输入从步骤到步骤按照定义的更新规则发展，这个规则可以从数据中学习。这个更新规则提供了给定先前所有状态的情况下下一个状态的预测。RNN 在图 1-3 中有示例。

RNN 层可以从数据中学习这个更新规则。因此，RNN 对于语言建模等任务非常有用，工程师希望构建可以根据历史预测用户将要输入的下一个单词的系统。

![images/rnn.jpg](img/tfdl_0103.png)

###### 图 1-3. 循环神经网络（RNN）。输入从底部输入到网络中，输出从顶部提取。W 代表学习到的转换（在所有时间步共享）。网络在左侧概念上表示，在右侧展开以演示不同时间步的输入是如何处理的。

## 长短期记忆单元

在前一节中介绍的 RNN 层理论上能够学习任意序列更新规则。然而，在实践中，这些层无法学习来自遥远过去的影响。这种遥远的影响对于进行稳健的语言建模至关重要，因为复杂句子的含义可能取决于远处单词之间的关系。长短期记忆（LSTM）单元是对 RNN 层的修改，允许来自更深处过去的信号传递到现在。LSTM 单元在图 1-4 中有示例。

![images/Long_Short_Term_Memory.png](img/tfdl_0104.png)

###### 图 1-4. 长短期记忆（LSTM）单元。在内部，LSTM 单元具有一组特别设计的操作，可以获得 vanilla RNN 的大部分学习能力，同时保留来自过去的影响。请注意，图示展示了许多 LSTM 变体中的一个。

# 深度学习架构

在前一节中介绍的深度学习原语组合了数百种不同的深度学习模型。其中一些架构在历史上非常重要。其他是首次呈现的新设计，影响了人们对深度学习能做什么的看法。

在本节中，我们介绍了一系列不同的深度学习架构，这些架构对研究社区产生了影响。我们要强调这是一个片段性的历史，不试图穷尽一切。文献中肯定有一些重要的模型没有在这里呈现。

## LeNet

LeNet 架构可以说是第一个著名的“深度”卷积架构。于 1988 年推出，用于执行文档的光学字符识别（OCR）。尽管它表现出色，但 LeNet 的计算成本对当时的计算机硬件来说是极端的，因此设计在创作后的几十年里相对默默无闻。这个架构在图 1-5 中有示例。

![images/lenet_architecture.png](img/tfdl_0105.png)

###### 图 1-5. 用于图像处理的 LeNet 架构。于 1988 年推出，可以说是图像处理的第一个深度卷积模型。

## AlexNet

ImageNet 大规模视觉识别挑战赛（ILSVRC）于 2010 年首次组织，旨在测试视觉识别系统的进展。组织者利用了亚马逊的 Mechanical Turk，这是一个在线平台，将工作者与请求者连接起来，以目录化一个大量图像的集合，并附带图像中存在的对象列表。Mechanical Turk 的使用使得数据集的筛选比以前收集的数据集大得多。

挑战举办的头两年，更传统的依赖于 HOG 和 SIFT 特征（手动调整的视觉特征提取方法）的机器学习系统取得了胜利。2012 年，基于对 LeNet 进行修改并在强大的图形处理单元（GPU）上运行的 AlexNet 架构进入并主导了挑战，其错误率是最接近竞争对手的一半。这次胜利极大地推动了计算机视觉中对深度学习架构的（已经萌芽的）趋势。AlexNet 架构如图 1-6 所示。

![images/alexnet.jpg](img/tfdl_0106.png)

###### 图 1-6。用于图像处理的 AlexNet 架构。这个架构是 ILSVRC 2012 挑战的获胜作品，并引发了对卷积架构的兴趣的复苏。

## ResNet

自 2012 年以来，卷积架构一直在 ILSVRC 挑战赛中获胜（以及许多其他计算机视觉挑战）。每年举办比赛时，获胜架构的深度和复杂性都在增加。ResNet 架构是 ILSVRC 2015 挑战的获胜者，特别引人注目；ResNet 架构的深度可达 130 层，而 AlexNet 架构只有 8 层。

历史上，非常深的网络学习起来具有挑战性；当网络变得如此深时，它们会遇到梯度消失问题。随着信号在网络中传播，信号会衰减，导致学习减弱。这种衰减可以用数学方式解释，但效果是每个额外的层会乘法地减少信号的强度，导致网络的有效深度受到限制。

ResNet 引入了一项创新，即控制这种衰减的旁路连接。这些连接允许来自更深层的部分信号无损地通过，从而有效地训练更深的网络。ResNet 旁路连接如图 1-7 所示。

![images/resnetb.jpg](img/tfdl_0107.png)

###### 图 1-7。ResNet 单元。右侧的身份连接允许未经修改的输入通过单元。这种修改允许有效训练非常深的卷积架构。

## 神经字幕模型

随着从业者对深度学习基元的使用变得更加熟悉，他们开始尝试混合和匹配基元模块，以创建能够执行比基本目标检测更复杂任务的高阶系统。神经字幕系统会自动生成图像内容的字幕。它们通过将从图像中提取信息的卷积网络与为图像生成描述性句子的 LSTM 层相结合来实现。整个系统是进行端到端训练的。也就是说，卷积网络和 LSTM 网络一起训练，以实现为提供的图像生成描述性句子的目标。

端到端训练是现代深度学习系统的关键创新之一，因为它减少了对输入的复杂预处理的需求。不使用深度学习的图像字幕模型将不得不使用复杂的图像特征化方法，如 SIFT，这些方法无法与字幕生成器一起训练。

神经字幕模型如图 1-8 所示。

![images/neural_captioning.png](img/tfdl_0108.png)

###### 图 1-8。一个神经字幕架构。使用卷积网络从输入图像中提取相关的输入特征。然后使用递归网络生成一个描述性句子。

## Google 神经机器翻译

谷歌的神经机器翻译（Google-NMT）系统使用端到端训练的范例来构建一个生产翻译系统，直接将源语言的句子翻译成目标语言。Google-NMT 系统依赖于 LSTM 的基本构建块，它将 LSTM 叠加了十几次，并在一个极其庞大的翻译句子数据集上进行训练。最终的架构通过将人类和机器翻译之间的差距缩小了多达 60%，为机器翻译带来了突破性的进展。Google-NMT 架构在图 1-9 中有所说明。

![images/google-nmt-lstm.png](img/tfdl_0109.png)

###### 图 1-9。Google 神经机器翻译系统使用深度递归架构来处理输入句子，并使用第二个深度递归架构生成翻译后的输出句子。

## 一次性模型

一次性学习可能是机器/深度学习中最有趣的新想法。大多数深度学习技术通常需要大量的数据来学习有意义的行为。例如，AlexNet 架构利用大型 ILSVRC 数据集来学习视觉对象检测器。然而，认知科学的许多研究表明，人类可以从很少的例子中学习复杂的概念。以婴儿第一次了解长颈鹿为例。在动物园里看到一只长颈鹿的婴儿可能有能力从那时起认出她以后看到的所有长颈鹿。

深度学习的最新进展已经开始发明能够实现类似学习成就的架构。只给出一个概念的几个例子（但给出了丰富的附加信息来源），这样的系统可以学习在非常少的数据点上进行有意义的预测。最近的一篇论文（本书的作者之一）使用这个想法来证明一次性架构甚至可以在婴儿无法学习的情境中学习，比如在医药发现中。一种用于药物发现的一次性架构在图 1-10 中有所说明。

![images/schematic_v2.png](img/tfdl_0110.png)

###### 图 1-10。一次性架构使用一种卷积网络将每个分子转换为一个向量。对苯环氧的向量与实验数据集中的向量进行比较。最相似数据点的标签（对甲苯磺酸）被用于查询。

## AlphaGo

围棋是一种古老的棋盘游戏，在亚洲具有广泛的影响力。自 20 世纪 60 年代末以来，计算机围棋一直是计算机科学的一项重大挑战。使计算机国际象棋系统深蓝在 1997 年击败国际象棋大师加里·卡斯帕罗夫的技术并不适用于围棋。问题的一部分在于围棋的棋盘比国际象棋大得多；围棋棋盘的大小为 19×19，而国际象棋为 8×8。由于每步可能有更多的走法，可能的围棋走法树扩展得更快，使得使用当代计算机硬件进行 brute force 搜索对于足够的围棋游戏来说是不够的。图 1-11 展示了一个围棋棋盘。

![images/go_board.jpg](img/tfdl_0111.png)

###### 图 1-11。围棋棋盘的插图。玩家交替在一个 19×19 的网格上放置白色和黑色的棋子。

谷歌 DeepMind 的 AlphaGo 最终实现了大师级别的计算机围棋。AlphaGo 证明了自己能够在五局比赛中击败世界上最强的围棋冠军李世石。AlphaGo 的一些关键思想包括使用深度价值网络和深度策略网络。价值网络提供了对棋盘位置价值的估计。与国际象棋不同，从棋盘状态很难猜测黑白哪方正在赢得围棋比赛。价值网络通过学习从比赛结果中做出这种预测来解决这个问题。另一方面，策略网络帮助估计在当前棋盘状态下采取的最佳走法。这两种技术与蒙特卡洛树搜索（一种经典搜索方法）的结合帮助克服了围棋游戏中的大分支因子。基本的 AlphaGo 架构在图 1-12 中有所说明。

![images/value_policy.jpg](img/tfdl_0112.png)

###### 图 1-12。A）AlphaGo 架构的描述。最初，一个用于选择走法的策略网络在专家比赛数据集上进行训练。然后通过自我对弈来完善这个策略。“RL”表示强化学习，“SL”表示监督学习。B）策略网络和价值网络都在游戏棋盘的表示上运行。

## 生成对抗网络

生成对抗网络（GANs）是一种新型的深度网络，使用两个相互竞争的神经网络，生成器和对手（也称为鉴别器），它们相互对抗。生成器试图从训练分布中抽取样本（例如，尝试生成逼真的鸟类图像）。鉴别器则致力于区分从生成器抽取的样本和真实数据样本。（特定的鸟类是真实图像还是生成器创建的？）这种 GAN 的“对抗”训练似乎能够生成比其他技术更高保真度的图像样本，并且可能有助于使用有限数据训练有效的鉴别器。GAN 架构在图 1-13 中有所说明。

![images/gen_adv.jpg](img/tfdl_0113.png)

###### 图 1-13。生成对抗网络（GAN）的概念描述。

GAN 已经证明能够生成非常逼真的图像，并可能推动下一代计算机图形工具的发展。这些系统生成的样本现在接近照片级逼真。然而，这些系统仍然存在许多理论和实际的问题需要解决，仍然需要进行大量的研究。

## 神经图灵机

到目前为止，所提出的大多数深度学习系统学习了具有有限适用领域的复杂函数；例如，目标检测、图像描述、机器翻译或围棋对弈。但是，我们是否可以有学习排序、加法或乘法等一般算法概念的深度架构呢？

神经图灵机（NTM）是第一次尝试制作一个能够学习任意算法的深度学习架构。该架构向类似 LSTM 的系统添加了一个外部存储器，以允许深度架构利用临时空间来计算更复杂的函数。目前，类似 NTM 的架构仍然相当有限，只能学习简单的算法。然而，NTM 方法仍然是一个活跃的研究领域，未来的进展可能会将这些早期的演示转变为实用的学习工具。NTM 架构在图 1-14 中有所说明。

![images/neural-turing-machine-tutorial.jpg](img/tfdl_0114.png)

###### 图 1-14。神经图灵机的概念描述。它添加了一个外部存储器，深度架构可以读取和写入其中。

# 深度学习框架

研究人员几十年来一直在实施软件包，以便更容易地构建神经网络（深度学习）架构。直到最近几年，这些系统大多是专用的，仅在学术团体内部使用。这种缺乏标准化的、工业强度的软件使得非专家难以广泛使用神经网络。

这种情况在过去几年发生了巨大变化。谷歌在 2012 年实施了 DistBelief 系统，并利用它构建和部署了许多更简单的深度学习架构。DistBelief 的出现，以及类似的软件包如 Caffe、Theano、Torch、Keras、MxNet 等广泛推动了行业的采用。

TensorFlow 借鉴了这一丰富的知识历史，并基于其中一些软件包（特别是 Theano）的设计原则进行了构建。TensorFlow（和 Theano）特别使用张量的概念作为支持深度学习系统的基本基元。这种对张量的关注使这些软件包与 DistBelief 或 Caffe 等系统有所区别，后者不允许为构建复杂模型提供相同的灵活性。

尽管本书的其余部分将专注于 TensorFlow，但理解其基本原理应该使您能够轻松地将所学到的经验应用于其他深度学习框架。

## TensorFlow 的局限性

TensorFlow 目前的一个主要弱点是构建新的深度学习架构相对较慢（初始化一个架构需要几秒钟的时间）。因此，在 TensorFlow 中构建一些动态改变结构的复杂深度架构并不方便。其中一种架构是 TreeLSTM，它利用英语句子的句法解析树执行需要理解自然语言的任务。由于每个句子都有不同的解析树，因此每个句子需要稍微不同的架构。图 1-15 展示了 TreeLSTM 架构。

![images/treelstm.png](img/tfdl_0115.png)

###### 图 1-15。TreeLSTM 架构的概念描述。每个输入数据点的树形状都不同，因此必须为每个示例构建不同的计算图。

虽然这样的模型可以在 TensorFlow 中实现，但由于当前 TensorFlow API 的限制，这样做需要相当大的创造力。新的框架如 Chainer、DyNet 和 PyTorch 承诺通过使构建新架构足够轻便，以便像 TreeLSTM 这样的模型可以轻松构建来消除这些障碍。幸运的是，TensorFlow 开发人员已经在扩展基本 TensorFlow API（如 TensorFlow Eager）上进行了工作，这将使动态架构的构建更加容易。

一个要点是，深度学习框架的进展是迅速的，今天的新系统可能会成为明天的老旧消息。然而，底层张量计算的基本原理可以追溯到几个世纪前，并且无论未来编程模型如何变化，都将使读者受益匪浅。本书将强调使用 TensorFlow 作为开发对底层张量计算的直观了解的工具。

# 回顾

在本章中，我们解释了为什么深度学习对现代软件工程师至关重要，并快速浏览了许多深度架构。在下一章中，我们将开始探索 TensorFlow，谷歌用于构建和训练深度架构的框架。在接下来的章节中，我们将深入探讨一些深度架构的实际示例。

机器学习（尤其是深度学习），就像计算机科学的大部分领域一样，是一门非常经验主义的学科。只有通过大量的实践经验才能真正理解深度学习。因此，在本书的剩余部分中，我们包含了许多深入的案例研究。我们鼓励您深入研究这些例子，并动手尝试使用 TensorFlow 实验您自己的想法。仅仅理论上理解算法是远远不够的！