# ![Yjs](https://yjs.dev/images/logo/yjs-120x120.png)

=== "中文"

    > 一个具有强大共享数据抽象的 CRDT 框架
    
    Yjs 是一个 [CRDT 实现](./crdt-algorithm.md)，它将其内部
    数据结构暴露为 *共享类型*。共享类型是常见的数据类型，如 `Map`
    或 `Array`，具有超能力：更改会自动分发给其他
    对等方，并在没有合并冲突的情况下合并。
    
    Yjs 是 **网络无关的**（p2p！），支持许多现有的 **富文本
    编辑器**、**离线编辑**、**版本快照**、**撤销/重做** 和
    **共享光标**。它可以支持无限数量的用户，并且非常适合处理大型文档。
    
    * 演示: [https://github.com/yjs/yjs-demos](https://github.com/yjs/yjs-demos)
    * 讨论: [https://discuss.yjs.dev](https://discuss.yjs.dev)
    * 聊天: [Gitter](https://gitter.im/Yjs/community) | [Discord](https://discord.gg/T3nqMT6qbM)
    * 基准测试 Yjs vs. Automerge:
      [https://github.com/dmonad/crdt-benchmarks](https://github.com/dmonad/crdt-benchmarks)
    * 播客 [**“Yjs 深入探讨实时协作编辑解决方案”：**](https://www.tag1consulting.com/blog/deep-dive-real-time-collaborative-editing-solutions-tagteamtalk-001-0)
    * 播客 [**“在 Gutenberg 中使用 YJS 框架进行 Google Docs 样式编辑”：**](https://publishpress.com/blog/yjs/)
    
    :construction_worker_woman: 如果您正在寻找专业支持，请
    考虑通过 [GitHub Sponsors](https://github.com/sponsors/dmonad) 支持该项目，签订“支持合同”。我会更快处理您的问题，
    我们可以在定期视频会议中讨论问题和疑问。
    否则，您可以在我们的社区 [讨论论坛](https://discuss.yjs.dev) 找到帮助。
    

=== "英文"

    > A CRDT framework with a powerful abstraction of shared data
    
    Yjs is a [CRDT implementation](./crdt-algorithm.md) that exposes its internal
    data structure as *shared types*. Shared types are common data types like `Map`
    or `Array` with superpowers: changes are automatically distributed to other
    peers and merged without merge conflicts.
    
    Yjs is **network agnostic** (p2p!), supports many existing **rich text
    editors**, **offline editing**, **version snapshots**, **undo/redo** and
    **shared cursors**. It scales well with an unlimited number of users and is well
    suited for even large documents.
    
    * Demos: [https://github.com/yjs/yjs-demos](https://github.com/yjs/yjs-demos)
    * Discuss: [https://discuss.yjs.dev](https://discuss.yjs.dev)
    * Chat: [Gitter](https://gitter.im/Yjs/community) | [Discord](https://discord.gg/T3nqMT6qbM)
    * Benchmark Yjs vs. Automerge:
      [https://github.com/dmonad/crdt-benchmarks](https://github.com/dmonad/crdt-benchmarks)
    * Podcast [**"Yjs Deep Dive into real time collaborative editing solutions":**](https://www.tag1consulting.com/blog/deep-dive-real-time-collaborative-editing-solutions-tagteamtalk-001-0)
    * Podcast [**"Google Docs-style editing in Gutenberg with the YJS framework":**](https://publishpress.com/blog/yjs/)
    
    :construction_worker_woman: If you are looking for professional support, please
    consider supporting this project via a "support contract" on
    [GitHub Sponsors](https://github.com/sponsors/dmonad). I will attend your issues
    quicker and we can discuss questions and problems in regular video conferences.
    Otherwise you can find help on our community [discussion board](https://discuss.yjs.dev).

## 赞助

**Sponsorship**

=== "中文"
    
    请在财务上为项目贡献——特别是如果您的公司依赖
    Yjs。[![成为赞助商](https://img.shields.io/static/v1?label=Become%20a%20Sponsor&message=%E2%9D%A4&logo=GitHub&style=flat&color=d42f2d)](https://github.com/sponsors/dmonad)

=== "英文"

    Please contribute to the project financially - especially if your company relies
on Yjs. [![Become a Sponsor](https://img.shields.io/static/v1?label=Become%20a%20Sponsor&message=%E2%9D%A4&logo=GitHub&style=flat&color=d42f2d)](https://github.com/sponsors/dmonad)

## 专业支持

**Professional Support**

=== "中文"

    * [与维护者的支持合同](https://github.com/sponsors/dmonad) -
    通过对开源 Yjs 项目进行财务贡献，您可以直接从作者那里获得
    专业支持。这包括每周视频通话的机会，以讨论您的具体挑战。
    * [Synergy Codes](https://synergycodes.com/yjs-services/) - 专注于
    为视觉应用开发实时协作编辑解决方案，Synergy Codes 专注于
    互动图表、复杂图形、图表和各种数据可视化类型。他们的专业知识使开发人员能够构建
    引人入胜和互动的视觉体验，利用 Yjs 的强大功能。请查看
    他们在 [视觉协作展示](https://yjs-diagram.synergy.codes/) 中的工作。

=== "英文"

    * [Support Contract with the Maintainer](https://github.com/sponsors/dmonad) -
    By contributing financially to the open-source Yjs project, you can receive
    professional support directly from the author. This includes the opportunity for
    weekly video calls to discuss your specific challenges.
    * [Synergy Codes](https://synergycodes.com/yjs-services/) - Specializing in
    consulting and developing real-time collaborative editing solutions for visual
    apps, Synergy Codes focuses on interactive diagrams, complex graphs, charts, and
    various data visualization types. Their expertise empowers developers to build
    engaging and interactive visual experiences leveraging the power of Yjs. See
    their work in action at [Visual Collaboration
    Showcase](https://yjs-diagram.synergy.codes/).

## 谁在使用 Yjs

**Who is using Yjs**

=== "中文"

    * [AFFiNE](https://affine.pro/) 本地优先、隐私优先的开源知识库。 :star2:
    * [Huly](https://huly.io/) - 开源的一体化项目管理平台 :star2:
    * [Cargo](https://cargo.site/) 设计师和艺术家的网站构建工具 :star2:
    * [Gitbook](https://gitbook.com) 技术团队的知识管理 :star2:
    * [Evernote](https://evernote.com) 笔记应用 :star2:
    * [Lessonspace](https://thelessonspace.com) 企业级虚拟教室和在线培训平台 :star2:
    * [Ellipsus](ellipsus.com) - 讲故事等的协作写作应用。支持版本控制、变更归属和“责任归属”。为整个出版过程（包括销售）提供解决方案 :star:
    * [Dynaboard](https://dynaboard.com/) 协作构建 Web 应用。 :star:
    * [Relm](https://www.relm.us/) 一个协作游戏世界，用于团队合作和社区。 :star:
    * [Room.sh](https://room.sh/) 一款会议应用，集成协作绘图、编辑和编码工具。 :star:
    * [Nimbus Note](https://nimbusweb.me/note.php) 由 Nimbus Web 设计的笔记应用。 :star:
    * [Pluxbox RadioManager](https://getradiomanager.com/) 一款基于 Web 的应用，用于协作组织广播。 :star:
    * [modyfi](https://www.modyfi.com) - Modyfi 是为多学科设计师构建的设计平台。设计、生成、动画等——无需在应用之间切换。 :star:
    * [Sana](https://sanalabs.com/) 具有 Yjs 支持的协作文本编辑的学习平台。
    * [Serenity Notes](https://www.serenity.re/en/notes) 端到端加密的协作笔记应用。
    * [PRSM](https://prsm.uk/) 协作思维导图和系统可视化。 *[(来源)](https://github.com/micrology/prsm)*
    * [Alldone](https://alldone.app/) 下一代项目管理和协作平台。
    * [Living Spec](https://livingspec.com/) 产品团队协作的现代方式。
    * [Slidebeamer](https://slidebeamer.com/) 演示应用。
    * [BlockSurvey](https://blocksurvey.io) 端到端加密的表单/调查工具。
    * [Skiff](https://skiff.org/) 私人去中心化工作空间。
    * [JupyterLab](https://jupyter.org/) 协作计算笔记本。
    * [JupyterCad](https://jupytercad.readthedocs.io/en/latest/) JupyterLab 的扩展，支持 3D FreeCAD 模型的协作编辑。
    * [Hyperquery](https://hyperquery.ai/) 用于共享分析、文档、电子表格和仪表板的协作数据工作空间。
    * [Nosgestesclimat](https://nosgestesclimat.fr/groupe) 法国碳足迹计算器具有基于 Yjs 的小组 P2P 模式。
    * [oorja.io](https://oorja.io) 可扩展协作应用的在线会议空间，端到端加密。
    * [LegendKeeper](https://legendkeeper.com) 协作的活动策划和世界构建应用，适用于桌面 RPG。
    * [IllumiDesk](https://illumidesk.com/) 使用 AI 构建课程和内容。
    * [btw](https://www.btw.so) 开源 Medium 替代品。
    * [AWS SageMaker](https://aws.amazon.com/sagemaker/) 构建机器学习模型的工具。
    * [linear](https://linear.app) 精简问题、项目和产品路线图。
    * [btw](https://www.btw.so) - 个人网站构建器。
    * [AWS SageMaker](https://aws.amazon.com/sagemaker/) - 机器学习服务。
    * [Arkiter](https://www.arkiter.com/) - 实时面试软件。
    * [Appflowy](https://www.appflowy.io/) - 他们使用 Yrs。
    * [Multi.app](https://multi.app) - 多人应用共享：在共享应用中指点、绘制和编辑，就像它们在您的计算机上一样。它们正在使用 Yrs。
    * [AppMaster](https://appmaster.io) 无代码平台，用于创建可生产的应用程序并生成源代码。
    * [Synthesia](https://www.synthesia.io) - 协作视频编辑器。
    * [thinkdeli](https://thinkdeli.com) - 一款由 AI 驱动的快速简单笔记应用。
    * [ourboard](https://github.com/raimohanska/ourboard) - 一款协作白板应用。
    * [Ellie.ai](https://ellie.ai) - 数据产品设计与协作。
    * [GoPeer](https://gopeer.org/) - 协作辅导。
    * [screen.garden](https://screen.garden) - PKM 应用的协作后端。
    * [NextCloud](https://nextcloud.com/) - 内容协作平台。
    * [keystatic](https://github.com/Thinkmill/keystatic) - 基于 git 的 CMS。
    * [QDAcity](https://qdacity.com) - 协作定性数据分析平台。
    * [Kanbert](https://kanbert.com) - 项目管理软件。
    * [Eclipse Theia](https://github.com/eclipse-theia/theia) - 一款在浏览器中运行的云端和桌面 IDE。
    * [ScienHub](https://scienhub.com) - 浏览器中的协作 LaTeX 编辑器。

=== "英文"

    * [AFFiNE](https://affine.pro/) A local-first, privacy-first, open source
      knowledge base. :star2:
    * [Huly](https://huly.io/) - Open Source All-in-One Project Management Platform :star2:
    * [Cargo](https://cargo.site/) Site builder for designers and artists :star2:
    * [Gitbook](https://gitbook.com) Knowledge management for technical teams :star2:
    * [Evernote](https://evernote.com) Note-taking app :star2:
    * [Lessonspace](https://thelessonspace.com) Enterprise platform for virtual
      classrooms and online training :star2:
    * [Ellipsus](ellipsus.com) - Collaborative writing app for storytelling etc.
      Supports versioning, change attribution, and "blame". A solution for the whole
      publishing process (also selling) :star:
    * [Dynaboard](https://dynaboard.com/) Build web apps collaboratively. :star:
    * [Relm](https://www.relm.us/) A collaborative gameworld for teamwork and
      community. :star:
    * [Room.sh](https://room.sh/) A meeting application with integrated
      collaborative drawing, editing, and coding tools. :star:
    * [Nimbus Note](https://nimbusweb.me/note.php) A note-taking app designed by
      Nimbus Web. :star:
    * [Pluxbox RadioManager](https://getradiomanager.com/) A web-based app to
      collaboratively organize radio broadcasts. :star:
    * [modyfi](https://www.modyfi.com) - Modyfi is the design platform built for
      multidisciplinary designers. Design, generate, animate, and more — without
      switching between apps. :star:
    * [Sana](https://sanalabs.com/) A learning platform with collaborative text
      editing powered by Yjs.
    * [Serenity Notes](https://www.serenity.re/en/notes) End-to-end encrypted
      collaborative notes app.
    * [PRSM](https://prsm.uk/) Collaborative mind-mapping and system visualisation.
      *[(source)](https://github.com/micrology/prsm)*
    * [Alldone](https://alldone.app/) A next-gen project management and
      collaboration platform.
    * [Living Spec](https://livingspec.com/) A modern way for product teams to collaborate.
    * [Slidebeamer](https://slidebeamer.com/) Presentation app.
    * [BlockSurvey](https://blocksurvey.io) End-to-end encryption for your forms/surveys.
    * [Skiff](https://skiff.org/) Private, decentralized workspace.
    * [JupyterLab](https://jupyter.org/) Collaborative computational Notebooks
    * [JupyterCad](https://jupytercad.readthedocs.io/en/latest/) Extension to
      JupyterLab that enables collaborative editing of 3d FreeCAD Models.
    * [Hyperquery](https://hyperquery.ai/) A collaborative data workspace for
      sharing analyses, documentation, spreadsheets, and dashboards.
    * [Nosgestesclimat](https://nosgestesclimat.fr/groupe) The french carbon
      footprint calculator has a group P2P mode based on yjs
    * [oorja.io](https://oorja.io) Online meeting spaces extensible with
      collaborative apps, end-to-end encrypted.
    * [LegendKeeper](https://legendkeeper.com) Collaborative campaign planner and
      worldbuilding app for tabletop RPGs.
    * [IllumiDesk](https://illumidesk.com/) Build courses and content with A.I.
    * [btw](https://www.btw.so) Open-source Medium alternative
    * [AWS SageMaker](https://aws.amazon.com/sagemaker/) Tools for building Machine
      Learning Models
    * [linear](https://linear.app) Streamline issues, projects, and product roadmaps.
    * [btw](https://www.btw.so) - Personal website builder
    * [AWS SageMaker](https://aws.amazon.com/sagemaker/) - Machine Learning Service
    * [Arkiter](https://www.arkiter.com/) - Live interview software
    * [Appflowy](https://www.appflowy.io/) - They use Yrs
    * [Multi.app](https://multi.app) - Multiplayer app sharing: Point, draw and edit
      in shared apps as if they're on your computer. They are using Yrs.
    * [AppMaster](https://appmaster.io) A No-Code platform for creating
      production-ready applications with source code generation.
    * [Synthesia](https://www.synthesia.io) - Collaborative Video Editor
    * [thinkdeli](https://thinkdeli.com) - A fast and simple notes app powered by AI
    * [ourboard](https://github.com/raimohanska/ourboard) - A collaborative whiteboard
      applicaiton
    * [Ellie.ai](https://ellie.ai) - Data Product Design and Collaboration
    * [GoPeer](https://gopeer.org/) - Collaborative tutoring
    * [screen.garden](https://screen.garden) - Collaborative backend for PKM apps.
    * [NextCloud](https://nextcloud.com/) - Content Collaboration Platform
    * [keystatic](https://github.com/Thinkmill/keystatic) - git-based CMS
    * [QDAcity](https://qdacity.com) - Collaborative qualitative data analysis platform
    * [Kanbert](https://kanbert.com) - Project management software
    * [Eclipse Theia](https://github.com/eclipse-theia/theia) - A cloud & desktop
      IDE that runs in the browser.
    * [ScienHub](https://scienhub.com) - Collaborative LaTeX editor in the browser.