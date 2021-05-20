# 由阅读源码想到

作者： https://www.terencexie.com/

#### I

阅读源代码，同数学、同任何一个知识密集型行业的吸收过程一样，是一个在反复地“读了忘、忘了读”的旅程。

记得本科时，从清北毕业的教授泛函分析的李老师说过一段闲话：“再来教你们泛函分析，对我来说是个重新拾起来的过程。数学就这样，反复地做、反复地读，反复地习得这个技能，然后又反复地忘掉。那怎么办呢？真要再用的时候再看看呗，拾起来就好了”。

我想，阅读源码是同样的，你不用那么费尽心力去叹息、去责备自己为何会忘记曾经熟稔的技术细节。等到要用的时候，又不得不重头开始。事实上，大家都会忘记。忘记了，在用的时候拾起来就好。

我想，这里真正让人泄气的一个问题是：既然终究会忘掉，那不如一开始就不要学习？但这便是tricky的部分。你读过的东西，忘掉，表面上什么都没得到。但事实是，你的技能，你对很多抽象的观点，会有具体深入的体会与理解。你会有切肤之感，进而它会以“直觉”的形式成为你潜意识的一部分。以此为基础，再去做触类旁通的相关事务，才懂得如何切入、有的放矢。

当然，阅读源码的挫败感，还在于它本身所需的大量基础知识造成的复杂性。往往，优秀的源码是由一系列的精妙技术组合而成。但并没有这样一套体系或者类似于打怪升级的系统去告诉你，哪一套是适合初级选手，哪一套适合进阶选手。于是，那些隐形的看不见的缺乏阶梯，横亘在了你的进步之路而你又浑然不知。也即是，读不懂它，仅仅是因为你和它之间缺乏的阶梯太多了而已。没有银弹，将那些缺乏的知识阶梯补上后，你自然可以读懂。

更何况，如同阅读文学名著一般。年少的阅读，中青年的阅读，以及成为了半个写作者的阅读，其对文本的理解和关注点都各有不同。不存在一种捷径或者参考列表，可以容纳对这个文本的所有理解和探索方式。倒不是说作者心思缜密，故意埋藏多个伏笔在那里。而是写出来的文本是头脑的磨刀石，它的作用是一扇引导门，启发你探索自己本身。这扇门的背后通往哪里，完全由自己的阅历和思维敏锐度决定。或许作者并未有某个方向的意思，但是，你却会因为那一句话，接合曾经的种种经历，进而完成自己的悟道。

阅读源码是同样的，你企图一下子要弄懂这段代码背后的所有技术，并不现实。且不说某些代码背后的知识量之巨让人生畏，你能够在这段代码当中读到多少东西，取决于你自身的技术高度和思想境界。好作品的阅读效果，不完全取决于作者，更取决于读者本身。阅读是一个读者和作者的共同创作的过程。读者本身的素质，会极大地影响最终的阅读产出。

所以，这其实是一个漫长的、反复不断地细品过程，急不来。想通了这点，便可以更为从容地去读这份代码。用个比喻讲，如果你不得不通读5次、实践5次，才能够达到下一个level的通悟。那么，知道了“你不可以跨过第三个包子而吃到第五个包子”的这一事实，便可以老老实实按部就班地从第一遍读起来。然后把剩下的焦虑托付给时间。

从这个角度讲，阅读源码这件事真的没有银弹，要依靠你的苦功夫和硬本领，去慢慢同它熬岁月。不要总想走捷径，这只会减缓自己的成长。欧几里得早已点出，“几何之中，并无王者之道”。应该拿出做数学的勇气，拿出干苦力的踏实，一点点缓慢进步。要知道，理解和习得一项本身就很复杂的技能，其本身就需要这么多的努力付出。

那为何你在数学上又有如此的勇气和魄力，去阅读那些一天甚至几天才能进展一页的大部头呢？

为何可以如此耐心？

#### II

那为何你在数学上又有如此的勇气和魄力，去阅读那些一天甚至几天只能进展一页的大部头呢？我想，这倒不是因为它是数学，而是年少时的浪漫情怀，以及更本质的：竞争中的优越感。

对于青年时期的自我来说，艰苦本身是值得期许或者追求的事情（类似于“为赋新词强说愁”）。你不会因为你处境的艰苦而垂头丧气、痛苦不已。相反，你期待这份艰苦，期待这份众人的不理解，因为似乎唯有这样，你才感觉你离那些传说中的人物更近些。艰苦本身似乎是在告诉你：“不是说天降大任要先苦其心志么，你看我现在多辛苦啊，看来大任必然是我的了。”你会因为颠倒的充分必要条件而让自己对艰苦期待不已。

回忆起来，就连自己最开始做数学的理由，也并不怎么高尚。虽然无数次地告诉自己，我是像那些伟大的数学大师一般，被数学的内在趣味和魅力所吸引，在上天的引领下走上了这条光辉的道路。可真相是，我是因为小孩子的虚荣心和在群体中的荣誉感而走上了这条路。

读书时，周围不断地在向你发声，不断重复地灌输一个观点：数学是困难的，数学是科学的皇后因而是一切理科的前提，学好数学才可以学好后门的物理和化学。与此同时，老师对学生的“引导”也颇有偏见（虽然现在想来，这也可以看作是份善意的偏见）。班里最受老师宠溺挂在嘴边表扬的，永远是那群站在数学之巅的同学，似乎其它成绩和优势都无法与之媲美。

于是，普通到不能再不同的我，自然而然地成了环境的产物：成为一个数学的爱好者。而实际目的是，成为老师终日夸奖的学生，成为班里有优越感的学生，得到周围同学羡慕的眼光。于是，披着爱好数学的外衣，我开始花大力气去研究数学、钻研数学，将与它相关的所有东西都拿来阅读和学习。

在这条路上，或许是花费足够巨大，以至于当周围的人已经不再以数学作为炫耀资本时，我依旧坚守在这条道路上。这或许是因为读了很多数学相关的东西，人物传记、历史发展，而在这些材料面，其内容当然会不断地做自我营销，暗示自己：学习数学是少数者的荣耀。大部分人都无法理解它，或是想要理解却不能，于是只好放弃。学习数学是一份特殊的光荣，而这份光荣，只有心智卓越者方能承受。

毕竟年少阅历贫瘠，我完全没有意识到这样的“宣传”，充满了异端邪教的味道。它背后的逻辑是：

你应该从事A，因为A好。

为什么A好呢？因为理解不了A的好处的人，都是笨蛋。

而你是聪明人，A的好，你应该是理解的吧。

所以，为什么A好呢？你自己知道。

整个一个“皇帝的新衣”改良版，真是太阳底下无鲜事，都是不断演重复上演的历史。

这样来看，这份对数学的坚持，不过是一个以“虚荣的邀宠”作开始，又以“宗教的布道”作持续。而因这份坚持所承受的所有甘苦，反倒因布道中充斥的“因艰苦而伟大、因困难而荣耀的故事”，被一一忽略漠视了。甚至更确切地说，你开始因布道的蛊惑而开始享受这样的艰难困苦，享受“长时间的投入却只能带来少许回报”的低产，因为你是那个心智卓尔不群的特别的人，你走在少数人的路上。

而等到年长以后，经历了生活的艰辛、欺骗与不公，这份“数学的执着”开始出现裂痕。愤怒、不满、失去耐心，一切负面的情绪开始席卷这份原始的热爱。即便是数学为我带来了许多不可磨灭的价值：清晰的逻辑、举一反三的能力、变态式的通悟，以及掌握本质的贯穿力。

曾经以为，这是多么不得了的价值观的挫败与蜕变。而现在看来，这不过是解开了那张披着“热爱数学”的狼皮，显露出了真正的追求——群体竞争中的优越感。原来我感兴趣的不是数学，而是群体中的优越感。当优越感在学生时代以数学体现时，我便热爱数学；当优越感在年长后以金钱与名誉体现时，我便热爱事业。这便是令人厌恶的伪善。可是，想要认清自己，并不是件容易的事情。因为它不仅涉及到你是否愿意，还取决于你当前是否有这个实力与洞察力，去看清被隐藏的“自欺”。

考察了上面这段经历，再回到阅读源码这件事情上。阅读源码，同做数学一样，投入巨大回报微小，并且这份回报往往还无法以金钱的方式来呈现。那么，摆在你面前的就几条路：

（一）

要么你好好地追问一下自己，自己是否真的是热爱编程？你从事这份职业的初衷，是否真的是因为它在智慧挑战上独有的魅力。如果不是，那么是否可以考虑从事其它你真正感兴趣的行业。

这是一条相对理想主义的建议，但却也不得不罗列，因为这是更进一步考虑的根基。

（二）

那么更现实来讲，你很可能同我一样，也是因为群体优越感的吸引进入了这个行业，又或者是，因为当前的薪酬优越，所以毅然决然地投入这个行业。无论是哪种，你的处境都比较纠结，你没有真心的纯粹的热爱，但却又不得不做这件高投入低产出的事情。

更细致地讲，即便是你真心热爱这份事业，你也会有倦怠期，也会在这样阴郁的时期低落消沉，但又偏偏赶巧，逼着你得持续阅读，以赶完工期。

那么，这时候，你或许可以反过来，好好地使用宗教的布道。去大量地阅读鸡汤、阅读你这个领域里先辈的艰苦故事、去历史的海洋里找寻一个个比你不幸生活艰辛的人物故事吧。然后用“皇帝新衣”式的逻辑为自己营造一种浪漫主义式的、自我感动的氛围。去拥抱艰辛、拥抱悲鸣，用苦难去实现自己荣誉上的满足。在这样的“你清楚自己的原始初衷、却又不得不妥协于现实压力和制约”的尴尬处境，便不再需要干净的逻辑，只需要干练地使用这份感性的兴奋剂，麻醉自我并让自己坚持下去。

如果非要讨论理性，我也可以给出一个答案，在某种意义上，这无非就是人类心理的自我保护机制。这是宗教得以建立信仰的本质。通过臆造神话和意义，去消解生活中的不幸。运用这份布道和扭曲逻辑的“信仰强力”，来阻止内心的崩塌。按照“历史”的说法：只要你有信仰，你就能上刀山下火海，能够抵御敌人的严刑拷打。因为，越是苦痛，越是能够激发你内心的成就感与满足感。你不会因为肉体的极端痛苦而丧失自己我，走向精神的崩坏。相反，你会因为这些苦痛而不断地升华、不断地感觉自己战果斐然、成就卓越。

通过这份心理的扭曲和欺骗，你的精神战胜了你肉体的极限。（爱，同是这样的精神力量的另一种形式。）

（P.S.：现代人的空虚，无非就是信仰的匮乏，缺乏宗教一般强烈的“精神毒品”。倒不一定将它看作是贬义的。尼采在宣称上帝已死之后，便指出了一条路：你能通过自己的标准，去建立你自己的善与恶吗？！）

（三）

再进一步，如果你能够突破精神上的这层诱骗，像一个成年人那样去清醒地接受现实，达到老子所说的境界“以万物为刍狗”。不偏不倚，耐心地花功夫，长时间地做事情。既不是享受痛苦，也不是因为对痛苦的不满而拒绝痛苦。而是可以心平气和地接受这份痛苦：

因为这项事业就是需要这么多的付出与艰辛，

因为这份事业就是在做西西弗斯的推石之旅，不断地读了忘、忘了读，

因为这份事业就是任重而道远，有无数厚砖头的书等着你去啃可你每天又只能进步一两页，它就是这么低产

而我又确实需要完成这件事情。那么，按照这件事自身的规律和特点，一一做完就好。没有喜怒哀乐，它仅仅是一份需要按照特定步骤做完的工作而已。

所以，哪一种方式更好呢？这取决于你自己对当前处境的判断，以及你实践之后的耐心调整。

#### III

Medium上有一篇文章Why You Don’t Deserve That Dream Developer Job，由一位漂亮的程序媛所写。文章不免贩卖了些焦虑，但也谈到些无法回避的问题：无论对于职业人士想在原有路线上继续发展、还是想要转行另寻它路，其中所蕴含的辛苦和挣扎，都不会有半点减少。

如果你认为自己的当前处境是在一个大坑里，那估计你就得再拼一些，再拼命一点才能够逃出四面埋伏的危地。对这时的你来说，“拼命”已经不是一种崇高的自我感动，而是再现实不过的对恐惧剧烈的回应。并且，你还不能简单地把拼搏交给情绪，你还需要用清晰系统的方式，把一个个横在眼前的障碍清扫干净。

如果需要夯实语言基础，就好好啃文档。

需要提高code技艺，就好好读源码。

需要增加实战经验，就好好积累代码。

不断练习，像学生时期做练习册那样去按部就班地练习。

阅读源码，容易着急。还没做好事情的准备工作，就急着深入细节，读得晕头转向。磨刀不误砍柴工，往往，我们会不由自主地跳过“磨刀”的过程，直接抡起斧头就开干。

那么，阅读源码的磨刀，应该是怎么样的呢？

首先，要伸展性地去解剖每一个概念。例如，对ss这个梯子项目来讲，一上来就陷入到各种网络协议之中，是极其不合适的。你应该先跳出来，从它的最终输出作用开始考察：跨过围墙。然后，根据这一概念不断地细究其功能和联系：例如什么叫做跨越？跨越的方式是什么？为了实现这个跨越动作，还需要什么功能做支撑？进而需要什么模块的实现？再进一步这个模块是由哪些类来实现的？

就这样从最直观的基本点出发，逐渐添加层层深入的细节，一步步去把握这个项目。而不是反过来，一开始就迷失到细节中去。

所以，阅读源码之前，其实需要花费大量功夫去查阅和理解那些宏观的视角，在宏观视角下，理解基建设施模块的必要性和原始考虑是什么，再层层深入。好的研究者，如同好的数学证明的阅读者，会花大力气在前期的宏观概念打磨、动机理清、出发点的明确与思路的连接。之后再进入到细节，有的放矢地施展精湛的技术。

这个漫长的对来龙去脉的探索，还可以再深入一些。你可以把这些零碎的东西，精心整理为slide或者文稿，在写作的整理中，进一步巩固自己在这方面系统而深入的认知。

甚至，就算你在这一过程中，还没有获得足够的正确理解，你也该好好归纳整理自己的所得、所失和当前处境。力求写出一份详尽的状态描述报告。你完全可以期望，在撰写这个总结性的报告中，获得思路的理清与灵感的迸发。
否则，你只会被细节带入到无底洞，既获得不了真知灼见，又会被无尽的挫败感包围，丧失信心。


#### IV
Eric S.Raymond的写于2014年的《How to learn hacking》是一篇出色的谈论如何阅读源码的文章。（Eric这里的hacking技术，指的是开源项目里的一种 an effective way to acquire general-purpose programming skills，即获取通用编程技艺的有效方法。）

这篇文字里，Eric创造性地提出了incremental-hacking cycle的概念。在他看来，建立起坚实的技术实力，需要经过这么一个循环过程：

1. 选择一个你感兴趣的开源项目。

2. 如果你不是太了解这个项目，通过阅读文档，去学习如何使用这个项目。

3. 为这个项目增添/修改一个小的feature。

4. 不断在代码库中做搜索，直至找到增添这个小feature的正确位置。

5. 为你的改动，生成一个build，对这个build做测试、调式。并为这个改动撰写文档。

6. 将你的改动作为这个项目的patch，发送给这个项目的维护者。

7. 继续询问自己：我现在理解了整个项目吗？如果不是，返回到第三步，选择另外一个更复杂的feature来重复上述操作。

短短7个步骤，蕴含了开源社区如何滋养技术人的合作方式（之后另写文章阐述），及自我技术修炼的精髓。

在这里，我想展开论述第三条。从技术角度讲，第三条是阅读源码的必要衍生——不仅仅是阅读代码，而是要和代码发生作用与反应。

但对于一个newbie来说，第三条充满了陷阱和不知晓的误导。特别是，当第三条的工作，是由你的上司或者同事指派下来，你往往会因为feature功能过于简单，更加无法领会第三条的精髓。

例如，如果这个项目本身有one click的功能，而你被指派的任务是实现一个double click的功能，估计很多newbie会为此抓狂，并深深地感觉受到了伤害和智商上的侮辱。

但实际情况是什么呢？

这里的重点，其实不是写一个简单的feature， 而是以这个小的feature做引子，去带动你找到能够正确添加这个feature的准确位置。

换言之，这是在训练你对代码的搜寻能力和对代码整体脉络的把握能力。当你能够自如地找寻到每一段代码正确的添加位置时，你也就基本掌握了这个项目的代码架构。

另一方面，“添加一段代码”这句话，其实隐含了很多老兵默认但newbie却不一定知道的东西：

如何证明你的添加是正确的？

这段代码会对整个项目产生哪些影响？

如何证明只会产生你认为的这些影响？

支撑这段代码的test case有哪些？

你撰写的test case能否覆盖、囊括了对项目产生的所有影响？

这些默认的隐藏思考点，对newbie是极其残酷的。老兵们没有义务去做过多的解释，往往就是一句“你要多写啊”，然后不断地给你“reject”，不断地重复“你要认真一点啊”这样粗糙的指导。

而如何认真呢？你从来不知道。其实就是这些默认的规则、规范和细致考虑。这些东西是开源社区的默认规则，你得通过不断地阅读其他人的邮件列表和提交工作，来一步步归纳总结：应该在每个看似简单的改动背后，做足、做踏实哪些相应的辅助工作。

如此，你更加可以理解：为什么不能够只是通过阅读代码，而必须通过“写代码”的方式来理解一个项目。所谓的“牵一发而动全身”，如果没有一个明确的操作目标和实际作用，你很难知道这个小小的位置，会造成那么可观的连锁反应。而添加代码，就如同往河里扔进去一颗石子，能够通过切切实实的作用，让那些隐藏在背后的连锁反应逐一显现，从而让你更深刻地去掌握项目背后的实质和逻辑关系。

这样，你也可以理解为什么需要添加一些功能上无足轻重的代码了。因为，如果你对本身的代码架构不够熟悉，而feature本身的技术细节又极端复杂，你将会陷入到一个double difficulty的处境。你的debug，不仅要解决feature的技术细节，还得考虑在代码构架中所引发的影响，这对一个newbie来说就太过困难了。

总结起来，对于newbie来说，一个很矛盾的困境、但却很少有人愿意为你解释清楚的是：你很可能因为这个feature自身的简陋甚至幼稚而轻视这项“添加feature”的任务。但你的轻视，源自于你将这项任务的“用意”弄错了。

这项任务的主菜，不在于feature的高技术含量，而在于让你去探索、评估、理解“即便是这么简单的一个feature添加，它到底会对这个项目本身产生哪些影响？又该如何去验证、测试这些影响？从而去加深你对项目的理解，提高自身吸收代码的技艺。”



#### 读代码的心态

阅读源代码的开始阶段，最好从感兴趣、自己有直观感受且有相对丰富准确的文档的项目开始。如同最开始阅读数学证明，最好从浅显易懂的教材开始，之后再开始最前沿的paper阅读。

阅读源代码需要同阅读证明一样的耐心，甚至更多。数学的定义或许就在前一页，可是源代码的某个新的类却需要你不断地Google，进而找到适合自己的关于原始概念的定义论述。

阅读源代码一定要放空自己的心，要做好精心死磕的准备。至少要在心理上给自己留出足够多的空间与时间。大不了拿出大段时间去浪费，去阅读、去死磕、去慢慢地把玩这个小片段的内容。（或者更成熟的想法是，完全集中注意力在自己的阅读工作上，根本不去关心它所需要花费的时间。）在这个阶段，最好拿出最为自私的气魄，TMD全世界的事情和期望都不管了，我就要在这个小小的代码片段所形成的逻辑框架里慢慢破解我的问题。

能否继续下去之后的阅读，这个阶段的心理就是绝对的分水岭。不要去想什么意义不意义，不要去思考什么浮躁的进度或者世界期望、又或是想什么此生也就如此的屁话，那些“存在”的问题是在决定是否开始阅读的时候考虑的，而不是阅读之中。在阅读的过程中，就如同已经在雪山上的登山者，已经毫无退路，最优做法就是不要把自己的精力浪费在任何无关事情之上，而是把所有力气花在问题攻坚上。

在这一刻，研究者是世界的王者。世界都必须为他而停止，他要拥有至高无上的心理信心。因为，一名研究者的珍贵价值之一，便是能够完全吃透繁杂深奥的问题和论述。而这项工作兼具思维的复杂性与劳作的漫长艰辛。他需要将自己的智慧挖掘到最深处。并在同时，他要像一名在流水线上劳作的工人，经历无意义的重复劳作和蛮长时间的煎熬。因为破解这些谜题，需要一次又一次西西弗斯式的基础工作。不断地提出一个猜想，然后找寻证据去证明或者否定，然后继续下一个问题，又或是提出另一个思路，继续做探索和验证。

而思路的建立或者潜在可行方案的直觉，都会牢牢建立在你对某个类或者某个文件的认知和相应定义的理解上。例如，向一个初学Android的人直接抛出PreferenceManager的概念会让人一头雾水。你可能会有潜在的猜测，偏好设置？仅仅是某个setting文件的管理？又或是神马？可是为什么在使用它的时候又会用到工厂模式？相应的edit是要去编辑神马呢？

不，这些都只是你一厢情愿的猜测。甚至，你的猜得越远，错得越厉害。而错误的起步，当然就是源自于你对PreferenceManager定义的猜测。这是代码世界中更加tricky的一个坑。不同于数学证明，由于数学领域的大多数术语都是稀奇古怪的或者生僻从未听说过，在阅读证明时，我们反而能更加警觉、仔细地去按图索骥，找到定义最原始的出处，去确保自己的理解无误。而在代码的世界里，由于命名需要可理解、通俗易懂，大多数的命名都会找寻生活中常见的词语。而这里，便是入坑的开始。

如果你对人文历史有足够充分的研究，你便会知道日常用语的多意性以及它所带来的后果的惨痛性。当在代码中充斥着各种似曾相识的名字时，你便会被这个“名”（名字）所迷惑。你会下意识地根据自身的经验去猜测它的作用和所指。虽然好的代码规范总是要求对命名要做到避免模糊和误用的特性，但你凭什么知道你阅读的这份代码遵从了它呢？

所以，真正正确的打开方式是，你必须确保你对其中的每一个术语都真正做到了知道它的原始定义所在。你必须要有可信程度极高的证据来支持你对定义的理解：最可信的莫过于定义这个术语的源代码，其次是它的官方API文档说明。你不可以用自己的历史经验来作为正确理解的论据。相反，你需要把这份艰辛的苦力做好、做扎实，为每一个术语找到最原始的依据，然后根据这个依据来确保自己的理解正确。

有了“术语考据”这一步的坚实基础，之后的代码阅读就会相对轻松。例如在上面的例子中，如果你查询过Android文档，查看过StackOverflow上的解析，你便会发现这个PreferenceManager是特有的存储临时信息（方便App内部沟通共享）的方式。那么，之后运用工厂模式的理由就变得显而易见了。所以，和数学证明的研读极其类似，找准了定义、吃准了最原始的“名”背后的“道”（真正所指），就能够为之后的过程起到四两拨千斤的巨大作用。

当然，这一过程无疑是费时费力的。往往，一个下午的尝试也就只能换取一行代码的正确理解。而身处这一耗尽心力的过程中，你绝望地感觉到，似乎所有的工作都毫无进展。然而，如同对数学证明的学习，这也正是其价值所在。没有多少人能够继续这种耗时耗力的孤独坚持，而这每一步的微小进展，其背后都有难以估量的时间与大量尝试的累积。所以在这一刻，阅读者需要在心里树立起毫无理由的自信心，让世界为自己去停止，让他人的期望在此刻消失。此时此刻，只有代码的破解与思维的运转。

如此耐心劳作，方能习得最精妙的技术，最坚实的设计。
