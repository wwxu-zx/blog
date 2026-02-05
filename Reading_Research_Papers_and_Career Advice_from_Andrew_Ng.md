# Reading Research Papers and Career Advice from Andrew Ng

## 1. Reading Research Papers

### 1.1 整合论文资源，记录理解程度

1. 收集和研究主题相关的资源。这些资源可以是**研究论文、Medium 文章、博客、视频、GitHub 项目**等等。
2. <span style="color: #e74c3c">**跟踪记录对列表内每一项资源的理解程度（至关重要）【分级理解】**</span>

   - **建议先至少对列表中的每项资源有10-20%的理解。这可以确保你对收集到的资源有足够的整体性了解，从而能够准确判断它与研究主题的相关度。**
   - **对于相关度最高的论文或资源，你可以进行更深层次的理解。**
     - <span style="color:#e74c3c;"> **与主题相关性高的重要文章多花点时间（多读几遍），不重要的略读（跳过）即可。**</span> 
3. **用自己的语言，将资源的**<span style="color: #e74c3c">**核心发现和技术**</span>**有条理的记录下来【**<span style="color: #e74c3c">**做结构化的笔记，用你自己的话总结**</span>**】**



> 基本上，具体地说，试着快速浏览并理解每一篇文章，而不是全部读完，也许你读了每一篇文章的10-20%，也许这足以让你对手头的文章有一个高水平的理解。在那之后，你可能会决定删除其中的一些论文，或者只是浏览一两篇论文，把它们通读一遍。
>

你应该<span style="color: #e74c3c">**以一种并行的方式阅读研究论文**</span>（一次处理多篇论文）:

> <span style="color:#000000;"> 如果我们列出 5 篇待读论文，每一篇列一行，表示从 0 到 100 的阅读进度。</span><span style="color: #e74c3c">最开始我们只需要阅读每一篇的 10% 左右，如果发现论文 2 不是我们想要的，就终结它。如果论文 3 是重要的，那么仔细阅读到进度 100%。</span>
>
> <span style="color: #e74c3c">由论文 3，我们可以发现其它相关研究，因此也可以加到论文列表中，例如第 6、7 篇。读完论文 3 也许会发现论文 4 也非常有意思，那么结合 4、6、7 继续阅读，并记录阅读进度。</span>



![](https://raw.githubusercontent.com/wwxu-zx/blog/main/assets/Reading_Research_Papers_and_Career_Advice_from_Andrew_Ng/5b36b5de8f57f2131a89c3b0e94f9d18.png)



吴恩达教授建议，用一个表格记录自己对相关资源的理解（**建议使用资源理解程度表**），类似下图所示：

![](https://raw.githubusercontent.com/wwxu-zx/blog/main/assets/Reading_Research_Papers_and_Career_Advice_from_Andrew_Ng/6034de2fbd3c481fe709bdd4e7b84394.png)



> [!TIP]
>
> **多少论文/资源才足够？**
>
> 吴恩达教授认为，<span style="color: #000000">5–20 篇论文可以让你对某个研究主题有一个基础了解</span>，或许可以进一步去了解实现技术。50-100 篇论文可以提供对特定领域比较深的理解。（如果阅读 <span style="color: #e74c3c">5-20 篇论文</span>，差不多我们对该领域就有一定的了解了。如果高效阅读 50 到 100 篇论文，那么对该领域的理解就比较完整了。）



### 1.2 如何具体阅读一篇论文

- **从第一个词浏览到最后一个词，这是最差的方式。一般而言，我们要多次阅读论文，且每一次的目的都不相同。**

- <span style="color: #000000">**重点论文至少读3遍，**</span><span style="color: #e74c3c">**Multiple passes（多遍阅读）**</span>

  - **第1遍**：start with reading the following sections within the paper: **title, abstract and figures**.
    - 快读，领略大意，判断是否值得阅读。要点：发现不感兴趣，随时停止阅读！
  - **第2遍**：reading the following sections: **introduction, conclusion, another pass through figures, scan through the rest of the content.**
    - **抓住主要思想**
  - **第3遍**：reading **the whole sections** within the paper but **skipping any complicated maths or technique formulations** that might be alien to you. During this pass, you can also **skip any terms and terminologies that you do not understand or aren’t familiar.**
    - **纵览论文主体，那些耗费时间的数学与推导部分可以暂时跳过，我们掌握整体脉络与框架就行。**
  - **第N遍：回头看**
    - **回过头再来理解论文中复杂的的数学和公式，以及不了解的的术语**
      - 如若要深入理解一个领域，这些公式和术语还是必须搞懂的。
      - 这时候肯定还会有一些部分不能理解，那么暂时跳过它们以后再攻坚。



- <span style="color: #e74c3c">**尝试重新推导数学并通过编程实现来练习。**</span>
- **更加深入的理解文中的数学部分**
    - 试着从头开始重新推导。虽然，这需要一些时间，但这是一个很好的练习。
- **代码练习**

  - 下载开源代码(如果你能找到的话)并运行它。

  - 从头开始重新实现：如果你能够做到这一点，那么这是一个强烈的信号，表明你已经真正理解了手头的算法。


**注：**

第1遍，也可以title, abstract, and conclusion（李沐老师建议），阅读论文时，首先阅读title, abstract, conclusion, figures, introductions.



> [!TIP]
>
> - 对于出于获取信息和工程目的而阅读论文的人来说，深入研究可能比较耗时，尤其是在有 20 多篇论文需要读的时候。
>
> - **跳过没有意义的部分**：出色的研究意味着我们发表的东西是在我们的知识和理解的边界上。
>  - 吴恩达还解释说，当你阅读论文（即使是最有影响力的人）时，可能会发现**某些部分应用得很少或者没有意义**。因此，如果阅读一篇论文并且文中一些内容**没什么用**（这并不罕见），没关系，最初可以略读。除非，你想要精通这些内容，可以随后再花更多的时间阅读。【<span style="color: #e74c3c">**舍弃论文中无用或无意义的部分**</span>】
>   
>- <span style="color: #e74c3c">**分级理解：有取舍，有选择性地读，不是每篇paper都值得细细读（有些略读即可）**</span>【<span style="color: #e74c3c"> **你的时间和精力都是稀缺资源，好钢要用在刀刃上**</span> 】
> 
>- **当你阅读一篇论文时，试着回答以下问题：**
>   1. 描述论文作者旨在实现或已经实现的研究目标【试图解决什么问题/完成什么工作】
>   2. 如果论文中提出了新的方法/技术，那么新方法的关键要素是什么【方法关键要素】
>   3. 这篇论文中哪些内容对你来说是有用的？【useful for you】
>   4. 你还想要阅读哪些参考资料？【other references, 阅读拓展】
> 
>​         如果你能回答这些问题，就说明你对论文有很好的理解。
> 
>​         事实证明，当你读更多的论文时，通过练习你会变得更快。因为，很多作者在写论文时使用的是通用格式。
> 
>- <span style="color: #e74c3c">**持续进步**</span>
> 
>  **<span style="color: #e74c3c">最重要的是不断学习，循序渐进，每周/每月读N篇。</span>**
> 
>  养成阅读研究论文的习惯：每周阅读两篇论文作为开始。





## 2. Career Advice（from Andrew  Ng）

**专注于做重要的工作**

![](https://raw.githubusercontent.com/wwxu-zx/blog/main/assets/Reading_Research_Papers_and_Career_Advice_from_Andrew_Ng/9aaeeba16b33abdd38eb23068cff080a.png)

### 2.1 找工作

- 具备扎实的基础技能（必学必会的知识，coding等）

- 对人工智能中许多不同的主题有广泛的理解，并在至少一个领域有非常深刻的理解

  - 对一些细分方向有深入的钻研和实践

- 既要有横向宽度，又要有纵向深度。（T字型人才）

  - **构建横向能力：**在这些领域建立基本技能的一个非常有效的方法是通过上课（课程）和阅读研究论文。


  - **构建纵向能力：**可以通过做相关项目、开源贡献、研究和实习来构建。

![](https://raw.githubusercontent.com/wwxu-zx/blog/main/assets/Reading_Research_Papers_and_Career_Advice_from_Andrew_Ng/a04309e5fcb274a2c4e6fd02ca6e7e76.png)

### 2.2 选择一份工作

**好工作的标准**

- **Learn the most** (Learn a lot on the way)【选择让你学到最多东西的工作】

	- 与优秀的人一起工作（你的manager，你将与之共事的团队（10～30人，你讲与他们合作/互动最多）

		- 被勤奋的人包围会影响你

	- 工作中能学到东西

	- 有空余去自学

- **Do important work** (Do work that matters)【做最重要的工作】

	- 从事有价值的项目，推动世界向前发展。

	- 博主个人认为：

		- 个人职业生涯要深耕的方向

		- 有深度的工作

		- 有影响力的工作

- Do meaning work

	- 有意义，有价值，e.g., helps other people

	- 尝试将机器学习带到传统行业

		- 我们在科技行业已经改变了很多，但我认为最令人兴奋的工作之一可能是在传统行业(科技行业之外)，因为你可以在那里创造更多的价值。

### 2.3 学习基础技术技能

在学习时，优先选择主题至关重要。吴恩达认为，对于机器学习技术职业来说，最重要的主题是：

<span style="color: #e74c3c">**基础机器学习技能**</span>：例如，理解线性回归、逻辑回归、神经网络、决策树、聚类和异常检测等模型非常重要。除了特定模型之外，更重要的是理解机器学习如何以及为什么工作的核心概念，例如偏差/方差、成本函数、正则化、优化算法和误差分析。

<span style="color:#e74c3c;"> **深度学习**</span>：深度学习在机器学习领域所占的比重很大，如果不了解它，很难在该领域取得卓越的成就！了解神经网络的基本知识、使它们工作的实际技能（如超参数调整）、卷积网络、序列模型和transformer是非常有价值的。

<span style="color:#e74c3c;">**与机器学习相关的数学**</span>：关键领域包括线性代数（向量、矩阵以及它们的各种操作）以及概率和统计（包括离散概率和连续概率、标准概率分布、独立性和贝叶斯规则等基本规则以及假设检验）。此外，探索性数据分析（EDA）——使用可视化和其他方法系统地探索数据集——是一种被低估的技能。我发现 EDA 在以数据为中心的 AI 开发中特别有用，在那里分析错误和获得见解真的可以帮助推动进展！最后，对微积分的基本直观的理解也将有所帮助。机器学习所需的数学一直在变化。例如，虽然一些任务需要微积分，但改进的自动微分软件使得发明和实现新的神经网络架构而不进行任何微积分成为可能。这在十年前几乎是不可能的。

<span style="color:#e74c3c;"> **软件开发**</span>: 虽然你只需要机器学习建模技能就可以找到一份工作并做出巨大贡献，但如果你还能编写好的软件来实施复杂的人工智能系统，那么你的就业机会就会增加。这些技能包括编程基础、数据结构（特别是与机器学习相关的数据帧）、算法（包括与数据库和数据操作相关的算法）、软件设计、熟悉 Python、熟悉 TensorFlow 或 PyTorch 等关键库以及 scikit-learn。

> <span style="color:#000000;"> 有很多东西要学习！即使你掌握了这份清单上的所有内容，我也希望你</span> <span style="color: #e74c3c">**能继续学习，不断深化你的技术知识**</span> 。<span style="color:#000000;"> 我认识很多机器学习工程师，他们在自然语言处理或计算机视觉等应用领域或概率图模型或构建可扩展软件系统等技术领域掌握了更深层次的技能，从中受益匪浅。</span> 
>
> <span style="color:#000000;"> 最后，没有人能在一个周末甚至一个月的时间里掌握他们需要知道的一切。<span style="color: #e74c3c">我认识的所有擅长机器学习的人都是终身学习者。</span>鉴于我们的领域变化如此之快，如果你想跟上步伐，除了不断学习，你几乎别无选择。</span>
>
> <span style="color:#000000;">如何才能多年保持稳定的学习步伐？<span style="color: #e74c3c">如果你能养成每周学习一点点的习惯</span>，你就可以在不费吹灰之力的情况下取得重大进展。</span>



### 2.4 良好的习惯和个人纪律

**很少有人会知道你周末是学习还是看电视，但他们会注意到随着时间的推移而产生的变化。许多成功人士在饮食、锻炼、睡眠、人际关系、工作、学习和自我保健方面都养成了良好的习惯。这些习惯帮助他们前进，同时保持健康。**



### 2.5 克服冒名顶替综合症

<span style="color: #e74c3c">**不要怀疑自己，你不要什么都会（也没有人是样样精通的专家），要坚定信心，日拱一卒，你就已经远远超过绝大多数人了。**</span>

在信息爆炸的今天，尤其要注意这一点。

![](https://raw.githubusercontent.com/wwxu-zx/blog/main/assets/Reading_Research_Papers_and_Career_Advice_from_Andrew_Ng/373e2167204282461471dd4e010f4b96.png)

**来自吴恩达老师对大家的鼓励：**

我曾经很难理解线性回归背后的数学原理。当逻辑回归在我的数据上表现异常时，我感到很困惑，我花了好几天时间才找到我实现的基本神经网络中的一个错误。<span style="color: #e74c3c">**今天，我仍然发现许多研究论文很难阅读**</span>，<span style="color:#e74c3c;"> **我最近**</span>在调整神经网络超参数时犯了一个明显的错误（幸运的是，一位工程师发现了这个问题并纠正了它）。

<span style="color:#e74c3c;"> **所以，如果你也觉得人工智能有挑战性，没关系。我们都经历过。我敢保证，每个发表过有影响力的人工智能论文的人，都在某个时候为类似的技术挑战而苦苦挣扎过。**</span> 

<span style="color:#e74c3c;"> **没有人是样样精通的专家。认识到自己擅长什么。**</span> 我三岁的女儿（连数到 12 都费劲）经常试图教我一岁的儿子东西。<span style="color:#e74c3c;"> **无论你的水平有多高——如果你至少像三岁孩子一样见多识广——你都可以鼓励和提升你身后的人。 **</span>这样做也会对你有所帮助，因为你身后的人会认可你的专业知识，并鼓励你继续发展。



### 2.6 最后的想法

<span style="color: #e74c3c">**让每一天都有意义。**</span>每年我的生日，我都会思考过去的日子和可能到来的日子。

<span style="color: #e74c3c">**这是我们与所爱之人共度时光、学习、为未来打拼、帮助他人的全部时间。无论你今天在做什么，是否值得你生命的1/30000？**</span>





## 3. 阅读就是在你大脑中建立认知模型的过程。

**保持阅读，不断构筑你的认知模型。**

> <span style="color: #000000">**我想再次强调，大家一定要有耐心，**</span><span style="color: #e74c3c">**因为阅读就是在你大脑中建立认知模型的过程**</span>，<span style="color: #000000">**虽然不知道今天读的文章/书未来什么时候能够派上用场，但是请大家保持阅读、建立认知的习惯。**</span>
> 																					<span style="color: #000000">——沈向洋@微软亚洲研究院</span>





## References

Stanford CS230: Deep Learning | Autumn 2018 | Lecture 8 - Career Advice / Reading Research Papers

YouTube link: [https://www.youtube.com/watch?v=733m6qBH-jI](https://www.youtube.com/watch?v=733m6qBH-jI)

记录理解程度、一篇至少读3遍，吴恩达建议这样读论文（机器之心）:

[https://mp.weixin.qq.com/s/WpAzkJM3h-NJuGHRW4eoZA](https://mp.weixin.qq.com/s/WpAzkJM3h-NJuGHRW4eoZA)

Andrew Ng(吴恩达)关于机器学习职业生涯以及阅读论文的一些建议（AI公园）：

[https://mp.weixin.qq.com/s/ih8_0lxVo0YSEQ1BH_N5cg](https://mp.weixin.qq.com/s/ih8_0lxVo0YSEQ1BH_N5cg)

机器学习研究者的养成指南，吴恩达建议这么读论文（机器之心）：

[https://mp.weixin.qq.com/s/QMDNKC0-sZu5p8LdMIULfg](https://mp.weixin.qq.com/s/QMDNKC0-sZu5p8LdMIULfg)

How to Read a Paper——如何阅读一篇论文：三遍阅读法

[https://mp.weixin.qq.com/s/p_soCw9Ou3Ok5SrZZpSqWw](https://mp.weixin.qq.com/s/p_soCw9Ou3Ok5SrZZpSqWw)

吴恩达：如何在人工智能领域打造你的职业生涯？（机器之心）：

[https://mp.weixin.qq.com/s/bJFT8R8VAunmvPPqoc7JXQ](https://mp.weixin.qq.com/s/bJFT8R8VAunmvPPqoc7JXQ)

<span style="color:#e74c3c;"> **如何阅读一篇学术论文 [译]**</span> ：

[https://baoyu.io/translations/learning/how-to-read-a-paper](https://baoyu.io/translations/learning/how-to-read-a-paper)

How to Read a Paper: 

[http://ccr.sigcomm.org/online/files/p83-keshavA.pdf](http://ccr.sigcomm.org/online/files/p83-keshavA.pdf)

[https://ics.uci.edu/~cs237/reading/files/howtoread.pdf](https://ics.uci.edu/~cs237/reading/files/howtoread.pdf)

如何阅读学术论文:

[https://qclab.wang/post/reading/](https://qclab.wang/post/reading/)

沈向洋、华刚：读科研论文的三个层次、四个阶段与十个问题:

[https://zhuanlan.zhihu.com/p/163227375](https://zhuanlan.zhihu.com/p/163227375)

沈向洋：读论文的三个层次

[https://zhuanlan.zhihu.com/p/144335900](https://zhuanlan.zhihu.com/p/144335900)

如何阅读论文？How to Read a Paper

[https://zhuanlan.zhihu.com/p/158709625](https://zhuanlan.zhihu.com/p/158709625)