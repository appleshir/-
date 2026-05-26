[改.html](https://github.com/user-attachments/files/28251689/default.html)

<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>景区剧到 - 大创项目计划书</title>
    <style>
        /* 全局重置 & 基础设置 */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: "SimSun", "宋体", "STSong", serif;
        }

        :root {
            --bg-main: #F9F4E8;
            --bg-title: #8B2323;
            --bg-btn: #A65527;
            --bg-btn-hover: #C87949;
            --bg-btn-active: #944A22;
            --bg-text: #FFFFFB;
            --border: #D4B483;
            --text-main: #2C2422;
            --text-title: #FFFFFF;
            --divider: #D2B48C;
            --shadow: rgba(139, 35, 35, 0.15);
        }

        body {
            background-color: var(--bg-main);
            color: var(--text-main);
            min-height: 100vh;
            background-image: url("data:image/svg+xml,%3Csvg width='100' height='100' viewBox='0 0 100 100' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M11 18c3.866 0 7-3.134 7-7s-3.134-7-7-7-7 3.134-7 7 3.134 7 7 7zm48 25c3.866 0 7-3.134 7-7s-3.134-7-7-7-7 3.134-7 7 3.134 7 7 7zm-43-7c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zm63 31c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zM34 90c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zm56-76c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zM12 86c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm28-65c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm23-11c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm-6 60c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm29 22c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zM32 63c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm57-13c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm-9-21c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM60 91c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM35 41c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM12 60c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2z' fill='%23d4b483' fill-opacity='0.08' fill-rule='evenodd'/%3E%3C/svg%3E");
        }

        /* 启动动画页 */
        .splash {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100vh;
            background-color: var(--bg-main);
            background-image: inherit;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 9999;
            opacity: 0;
            transform: scale(0.85);
            transition: all 1.2s cubic-bezier(0.2, 1, 0.3, 1);
        }

        .splash.show {
            opacity: 1;
            transform: scale(1);
        }

        .splash-wrap {
            text-align: center;
            padding: 60px 100px;
            border: 2px solid var(--border);
            border-radius: 12px;
            box-shadow: 0 8px 24px var(--shadow);
            background-color: rgba(255, 255, 251, 0.6);
            animation: breathe 3.5s ease-in-out infinite;
        }

        @keyframes breathe {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-6px); }
        }

        .splash h1 {
            font-size: 52px;
            font-weight: bold;
            color: #8B2323;
            margin-bottom: 24px;
            letter-spacing: 8px;
        }

        .splash p {
            font-size: 18px;
            color: #A65527;
            letter-spacing: 2px;
        }

        /* 主容器 */
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 20px;
            display: none;
            animation: fadePage 0.8s ease-out;
        }

        @keyframes fadePage {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* 顶部标题栏 */
        .header {
            background-color: var(--bg-title);
            padding: 28px 20px;
            margin-bottom: 24px;
            border: 3px ridge var(--border);
            border-radius: 10px;
            text-align: center;
            color: var(--text-title);
            box-shadow: 0 4px 12px var(--shadow);
            position: relative;
            overflow: hidden;
        }

        .header::before {
            content: "";
            position: absolute;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(255,255,255,0.1) 0%, transparent 50%);
        }

        .header h1 {
            font-size: 36px;
            margin-bottom: 8px;
            letter-spacing: 6px;
        }

        .header p {
            font-size: 16px;
            opacity: 0.9;
            letter-spacing: 2px;
        }

        /* 主内容布局 */
        .main-content {
            display: flex;
            gap: 24px;
        }

        /* 左侧菜单区 */
        .left-menu {
            width: 340px;
            background-color: rgba(255, 255, 251, 0.5);
            border: 2px solid var(--border);
            border-radius: 10px;
            padding: 16px;
            box-shadow: 0 4px 12px var(--shadow);
            display: flex;
            flex-direction: column;
        }

        .menu-title {
            text-align: center;
            font-size: 20px;
            font-weight: bold;
            margin-bottom: 16px;
            padding-bottom: 10px;
            border-bottom: 1px solid var(--divider);
            letter-spacing: 4px;
        }

        .menu-list {
            overflow-y: auto;
            flex: 1;
            padding-right: 6px;
        }

        /* 自定义滚动条 */
        .menu-list::-webkit-scrollbar {
            width: 8px;
        }
        .menu-list::-webkit-scrollbar-track {
            background: #f1e9d8;
            border-radius: 4px;
        }
        .menu-list::-webkit-scrollbar-thumb {
            background-color: var(--divider);
            border-radius: 4px;
        }
        .menu-list::-webkit-scrollbar-thumb:hover {
            background-color: var(--bg-btn);
        }

        /* 目录按钮 */
        .menu-btn {
            width: 100%;
            padding: 12px 14px;
            background-color: var(--bg-btn);
            color: var(--text-title);
            font-size: 14px;
            font-weight: bold;
            border: 2px ridge var(--border);
            border-radius: 6px;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-bottom: 6px;
            text-align: left;
            letter-spacing: 1px;
        }

        .menu-btn:hover {
            background-color: var(--bg-btn-hover);
            transform: translateX(4px);
            box-shadow: 2px 2px 6px var(--shadow);
        }

        .menu-btn.active {
            background-color: var(--bg-btn-active);
            transform: translateX(2px);
            box-shadow: inset 2px 2px 4px rgba(0,0,0,0.2);
        }

        .divider {
            height: 1px;
            background-color: var(--divider);
            margin: 4px 10px 8px;
            opacity: 0.6;
        }

        /* 右侧内容区 */
        .right-content {
            flex: 1;
            display: flex;
            flex-direction: column;
        }

        .content-title {
            text-align: center;
            font-size: 20px;
            font-weight: bold;
            margin-bottom: 16px;
            padding-bottom: 10px;
            border-bottom: 1px solid var(--divider);
            letter-spacing: 4px;
        }

        .text-box {
            flex: 1;
            background-color: var(--bg-text);
            border: 2px solid var(--border);
            border-radius: 10px;
            padding: 24px;
            font-size: 15px;
            line-height: 1.8;
            white-space: pre-line;
            overflow-y: auto;
            min-height: 720px;
            box-shadow: inset 0 2px 8px rgba(212, 180, 131, 0.2);
            transition: all 0.3s ease;
        }

        .text-box::-webkit-scrollbar {
            width: 8px;
        }
        .text-box::-webkit-scrollbar-track {
            background: #f1e9d8;
            border-radius: 4px;
        }
        .text-box::-webkit-scrollbar-thumb {
            background-color: var(--divider);
            border-radius: 4px;
        }

        /* 响应式适配 - 手机/平板 */
        @media (max-width: 992px) {
            .main-content {
                flex-direction: column;
            }
            .left-menu {
                width: 100%;
                max-height: 400px;
            }
            .splash h1 {
                font-size: 38px;
                letter-spacing: 4px;
            }
            .splash-wrap {
                padding: 40px 40px;
            }
        }

        @media (max-width: 576px) {
            .header h1 {
                font-size: 28px;
            }
            .text-box {
                padding: 16px;
                font-size: 14px;
            }
        }
    </style>
</head>
<body>
    <!-- 启动动画 -->
    <div class="splash" id="splash">
        <div class="splash-wrap">
            <h1>🏮 景区剧到 🏮</h1>
            <p>沉浸式景区剧本游 · 项目计划书展示</p>
        </div>
    </div>

    <!-- 主页面 -->
    <div class="container" id="mainPage">
        <!-- 顶部标题栏 -->
        <div class="header">
            <h1>🏮 景区剧到 🏮</h1>
            <p>大创项目计划书展示系统</p>
        </div>

        <!-- 主内容区 -->
        <div class="main-content">
            <!-- 左侧目录菜单 -->
            <div class="left-menu">
                <div class="menu-title">📜 项目目录</div>
                <div class="menu-list" id="menuList"></div>
            </div>

            <!-- 右侧内容展示 -->
            <div class="right-content">
                <div class="content-title">📖 详细内容</div>
                <div class="text-box" id="contentBox">👉 点击左侧按钮查看计划书原文内容</div>
            </div>
        </div>
    </div>

    <script>
        // 项目计划书完整数据
        const PLAN_DATA = {
            "项目简介": "“景区剧到”简单说就是：把景区变成一个大大的沉浸式剧本演绎场地。游客买一份文创产品，就能跟着剧情线索在景区里逛、解谜、互动。项目目前已经在腾冲市和顺古镇图书馆成功落地，落地首日为和顺古镇图书馆吸引了超过300人次+的额外客流与良好的后期反馈，我们现在想把这种玩法推广到更多类型的景区，例如古镇、博物馆、自然公园等。这样既能帮景区增加玩法和收入，也能让游客玩得更开心。我们下一步将计划将此模式打造为一个面向各类景区的沉浸式剧本游产品与服务平台。项目以景区实景为载体、剧本游为交互形式，通过定制化剧本、文创产品、小程序工具及NPC演绎，将传统静态游览升级为互动式文化体验。项目首期在腾冲和顺古镇图书馆完成试点验证，现已初步具备向红色景区、历史古镇、自然公园、博物馆等多类型场景复制推广的能力。市场定位：我们不做一次性活动，而是做一套可快速部署、可数据追踪、可持续盈利的服务产品。目标客户是那些需要内容升级但缺乏专业能力的景区管理机构。",
            "项目亮点": "模式创新：首创“景区+剧本游”轻资产融合模式，无需场地改造，依托景区现有空间即可落地。相比传统景区改造动辄数十万的投资，我们仅需数万元即可启动一个项目，极大降低了景区的试错成本。产品创新：以文创产品作为体验入口，不依赖门票收入，降低游客参与门槛，提升转化率。游客花40-100元购买一份文创，即可获得完整的剧情体验，同时带走一份有纪念意义的实物。技术赋能：配套小程序实现任务发布、线索解锁、打卡、数据采集等功能，支持多景区并行管理。后台可分析游客行为、转化率、停留时间等，为景区优化运营提供数据支持。商业可持续：收入来源包括文创销售、景区服务费、IP授权及数据增值服务，具备良好的盈利模型。",
            "组织与人力资源": "我们团队由来自滇西应用技术大学、北方民族大学、合肥工业大学、南京林业大学等高校的同学组成，专业涵盖产品设计、工艺美术、计算机科学与技术、环境设计、旅游地学与规划工程、木材科学与工程等，背景比较多元，为项目的发展提供了多种思路与解答。我们建立了每周例会、分工负责等管理机制，确保项目高效推进。团队成员的专业多样性，形成了从剧本创作、文创设计、小程序开发到现场运营的完整闭环。项目在文创设计和制作上得到了云南舍相工艺美术有限公司的支持，剧本创作和宣发与腾冲52Hz剧本馆进行合作。跟和顺古镇图书馆、艾思奇故居纪念馆等也已经建立了初步联系。指导老师和企业导师帮我们对接资源、出谋划策。",
            "投资与财务": "项目初期投入7000元。目前和顺图书馆项目试演阶段用400元成本单日为和顺图书馆带来300余人次额外客流，人均引流成本约1.3元，远低于景区营销行业平均水平（通常为5-10元）（不排除图书馆举办活动引起游客好奇等因素）。试演阶段直接引流ROI（按每人次产生5元后续消费估算）超过270%。后续通过文创销售、二销等转化，预计首年整体ROI可达10倍以上。基于已验证模式，预计第一年销售收入9万元（按1500件、单价60元计算），第三年平台化后覆盖5个景区，销售收入突破150万元。按单件毛利40元计算，投资回收期约4个月。随着景区数量增加，固定成本被摊薄，利润率将进一步提升。财务预测依据：单景区年游客量30万人次，剧本游转化率1.5%，单价60元，年收入27万元。扣除产品成本（33%）和运营成本（24%），净利润约11.5万元，净利率42.6%。多景区叠加后，剧本开发的固定成本（约2万元/剧本）可摊薄至每景区4000元，技术运维成本不随景区数量线性增长，因此利润率可提升至50%以上。",
            "试点核心数据": "试演成本400元，道具、物料、简单补贴；单日引流300+人次，额外客流，超出日常散客量；人均引流成本约1.3元，行业平均5-10元；试演ROI>270%，按每人次产生5元后续消费估算；游客满意度100%，回收问卷30份，全部满意；完成体验人数30个团队，近五十人左右，限流情况下。",
            "引流效果验证": "本次项目执行中，卖报员在图书馆门口街道吆喝“号外号外！抗日密电！”，吸引了大量路过游客的注意。统计显示，超过75%的参与者是被街头吆喝吸引进馆的。这一环节证明：低成本的街头引流（仅需一名NPC和一份传单）可以有效打破景区“静待客来”的被动局面。对于知名度不高、散客吸引力弱的景区，这种主动引流方式尤其有效。且和顺图书馆的参观主要人群为导游团群体，相比之下，平日特意进入游览的散客数量反而并不多。针对这种现象，我们的结论是和顺图书馆的名气相比于国内更成熟的红色景点并没有到达人尽皆知的地步，因此对散客吸引力不大，而我们的项目中具有为景区引流而设置的前期环节，游客在被吸引后会因为我们活动的新奇而进入景点，后又会因为了解了景点的内涵及被我们的剧本故事所打动而又爱上景点，宣传景点，又再次吸引新的游客前来，达成良性闭环。",
            "客群适配验证": "和顺图书馆的参观主要人群为中老年人团体及带娃家庭。基于此种现象，我们调研后给出的动机分析为：中老年团体对此类带红色文化基因的景点具有非常浓厚的兴趣，而带娃家庭也需要此类景点为孩子进行良好的思想教育。基于游客的需求，我们给出的答案是在创作的剧本当中结合景区历史，融入红色文化故事。在和顺古镇图书馆项目参与体验的游客中，中老年团体占比约50%，带娃家庭占比约30%，青年散客约20%。中老年游客对红色历史有天然亲近感，在“抄写密电”“盖章确认”等环节表现出高度参与热情；亲子家庭中，家长认为活动“让孩子在玩中学到了思想”；青年游客则更关注拍照打卡和社交分享。这表明：红色题材剧本游能够覆盖多年龄段，且不同人群都能找到兴趣点。",
            "文创销售验证": "和顺图书馆的文创销售情况。根据我们的调查与现场实践，我们发现目前和顺图书馆的文创产品销售主要是以静态陈列展示及销售员宣传为主，游客的购买动机主要为产品制作精美或当作“曾去过”的一种纪念品。此种消费模式在当今时代未免过于老套，而我们给出的答案是赋予文创产品故事，打开销售渠道新方式。试演期间，我们提供了“和顺记忆卡”等文创样品，作为结业道具和纪念品。游客购买意愿强烈，超过80%的完成者表示“如果正式运营，愿意花40-60元购买”。这说明：将文创产品作为剧本入口的模式是 feasible 的，游客为“故事+实物”付费的意愿高于单纯购买纪念品。",
            "运营流程优化": "试演中我们发现：个别游客在“借记处”抄写密文时，因字迹潦草导致后续NPC难以辨认。为此，我们增加了针对不同游客的不同方式，例如孩童游客由于写字困难，我们安排了当天的志愿者与npc配合为孩童游客讲述及抄写密文，而部分游客会不想写字，认为麻烦，我们也安排了不同的话术来应对，做到不是一套死规则用到底，而是面对不同的要求有不同的解法。此外，游客走错顺序的情况偶有发生，我们优化了每个NPC的指路话术，确保“下一站”信息清晰。这些微调使后续轮次的流畅度提升了约30%。",
            "后期反馈": "密封信中的感谢语和彩蛋（“下次来看看门牌背面”）引发了游客的好奇心。有4位游客在离馆后返回寻找彩蛋，并与工作人员交流。这表明：体验后的延伸设计能够增强品牌粘性，促进二次到访。",
            "产业背景": "近年来，沉浸式文旅体验市场年均增长率超过30%。据文化和旅游部数据，2025年全国沉浸式文旅项目数量同比增长45%，市场规模突破千亿元。游客需求正从“观光打卡”向“参与式、故事化、情感化”转变。与此同时，国内大量景区仍以静态陈列、标准讲解为主，互动性弱，游客停留时间短，二次消费占比低。剧本杀、实景游戏等业态的兴起为景区内容升级提供了新方向，但市场上尚缺乏一套标准化的、可快速部署的“景区+剧本游”解决方案。",
            "产品概述": "“景区剧到”为景区提供一站式剧本游服务包，包含：剧本定制，基于景区历史、文化、自然特征开发专属剧情；文创产品设计，兼具道具功能与纪念价值的实体入口；小程序系统，任务发布、线索解锁、地图导航、打卡分享；NPC培训与管理，角色设定、话术脚本、现场调度；数据运营，游客行为分析、转化率追踪、体验优化建议。",
            "产品优势": "轻资产：无需基建投入，利用景区现有动线与空间。高适配：剧本模板库覆盖红色、历史、亲子、自然等主题，可快速定制。强互动：将游览转化为任务导向的沉浸体验，显著延长游客停留时间。易复制：标准化流程 + 模块化内容，支持多景区落地。",
            "目标市场": "B端客户：各类景区管理机构、文旅投资公司、地方政府文旅部门。C端用户：中老年文化游客、亲子家庭、青年体验群体、研学及党建团建团队。",
            "市场容量": "全国A级景区总数超过1.3万家，其中具备文化故事属性的古镇、红色景区、博物馆等超过3000家。假设初期渗透率为1%，即可覆盖30家景区。按每家年均贡献10万元收入计算，平台年收入可达300万元。中长期渗透率提升至5%，年收入可突破1500万元。",
            "竞争分析": "传统红色景区政治教育功能强，但互动性弱；景区剧本游沉浸感强，但与文化内涵结合弱，缺乏深度；独立剧本杀门店剧情成熟，但与实景脱离，无法复用景区流量；本项目以文化+实景+平台为核心，差异化优势明显。",
            "核心产品线": "标准剧本包：面向中小型景区，提供剧本模板 + 文创套盒 + 基础NPC指南，定价1-3万元/套。定制开发服务：根据景区专属IP深度开发剧本、文创及数字内容，定价5-10万元/项目。小程序平台：按年收取服务费，含任务引擎、用户管理、数据分析模块，0.5-1万元/年/景区。文创衍生品：单独销售或与剧本绑定，毛利率约60%。",
            "技术架构": "小程序端基于微信生态，集成定位、二维码扫描、音视频播放、社交分享等功能。后台管理系统支持多景区独立账户，可配置任务节点、线索逻辑、用户数据导出。未来可接入AR识别、语音交互等增强技术。",
            "用户体验流程": "游客在景区入口或合作点购买文创产品（40-100元）；扫描产品内二维码进入小程序，获取初始剧情；按地图指引前往各任务点，完成解谜或互动；解锁下一阶段剧情，收集虚拟或实体奖励；完成全部剧情后领取纪念证书，并可分享至社交平台。",
            "收入来源": "文创产品销售：游客直接购买，为核心现金流来源。景区服务费：按项目收取开发费或年费，适用于B端合作。分成收入：与旅行社、OTA平台合作，按人次或销售额分成。IP授权：成熟的剧本IP可授权给其他景区或文创厂商。",
            "成本结构": "固定成本：剧本开发（人力）、小程序维护（兼职）、设备折旧。可变成本：文创产品生产、NPC劳务、宣传物料、平台佣金。",
            "盈利模型": "单景区模型：年游客量30万人次，剧本游转化率1.5%，单价60元，年收入27万元。扣除产品成本（33%）和运营成本（24%），净利润约11.5万元，净利率42.6%。多景区叠加后边际成本下降，利润率可提升至50%以上。",
            "生产与供应链": "文创产品委托本地工厂小批量生产，首次试制周期15天，补货周期7天。剧本物料（线索卡、地图、证书）自行设计后外协打印。NPC服装道具采用租赁与采购结合的方式，单套成本控制在200元以内。",
            "人员配置": "项目统筹1人，整体管理、对外合作；剧本内容2人，剧本创作、剧情迭代、历史把关；文创设计2人，产品设计、打样、生产对接；技术运维1人，小程序维护、数据统计；运营推广2人，游客接待、NPC管理、线上线下推广；财务后勤1人（兼职），账务、库存、成本控制。",
            "合作伙伴": "云南舍相工艺美术有限公司：文创产品设计及生产支持。腾冲52Hz剧本馆：剧本创作与宣发渠道。艾思奇故居纪念馆、和顺图书馆：场地与内容授权。本地旅行社、研学机构：团队客源导入。",
            "资金计划": "总投入7000元，文创试制3000元，剧本物料1200元，NPC服装道具800元，销售设备500元，宣传物料500元，人员补贴1000元。",
            "收入预测": "第1年覆盖1景区，销售1500件，收入9万元；第2年覆盖3景区，销售4500件，收入45万元；第3年覆盖5景区，销售15000件，收入150万元。",
            "投资回收期": "单件毛利40元，7000元初始投入需销售175件。按首年月均销售125件计算，回收期约为4个月。考虑前期宣传和游客积累，实际可能在3个月左右。乐观情景回收期2个月，悲观情景回收期8个月，仍远低于一般创业项目1-2年的回收期，风险较低。",
            "和顺图书馆项目": "剧本《鹧鸪行动——和顺图书馆密电》，以真实历史为背景，让游客扮演地下工作者，在30分钟内完成情报传递任务。包含卖报员、老周、蔡连长、花园接头人、图书借记员、李先生6个NPC角色，6大任务节点，全程实景沉浸式互动。",
            "艾思奇故居项目": "剧本《真理之路：与艾思奇的对话》，红色爱国、沉浸式互动、实景解谜、多线结局类型，体验时长3-4小时，覆盖元龙阁、艾思奇纪念馆、千手观音古树等8大场景，融入《大众哲学》核心思想。",
            "市场调研数据": "核心受众为18-25岁青年学生，对艾思奇及《大众哲学》认知度偏低，77.5%可接受哲学+实景剧本游形式，90%认可在历史场所开展，66.25%接受50-100元定价，最看重历史真实性与内容准确性。"
        };

        // DOM 元素
        const splash = document.getElementById('splash');
        const mainPage = document.getElementById('mainPage');
        const menuList = document.getElementById('menuList');
        const contentBox = document.getElementById('contentBox');
        let activeBtn = null;

        // 初始化启动动画
        window.addEventListener('load', () => {
            splash.classList.add('show');
            // 动画结束切换主页面
            setTimeout(() => {
                splash.style.display = 'none';
                mainPage.style.display = 'block';
            }, 2200);
        });

        // 生成左侧菜单按钮
        function initMenu() {
            for (const [title, content] of Object.entries(PLAN_DATA)) {
                const btn = document.createElement('button');
                btn.className = 'menu-btn';
                btn.textContent = title;
                btn.dataset.content = content;

                btn.addEventListener('click', function () {
                    // 切换选中状态
                    if (activeBtn) activeBtn.classList.remove('active');
                    this.classList.add('active');
                    activeBtn = this;
                    // 展示内容
                    showContent(title, content);
                });

                menuList.appendChild(btn);

                // 分割线
                const divider = document.createElement('div');
                divider.className = 'divider';
                menuList.appendChild(divider);
            }
        }

        // 展示文本内容
        function showContent(title, content) {
            contentBox.textContent = `【${title}】\n\n${content}`;
            // 滚动到顶部
            contentBox.scrollTop = 0;
        }

        // 页面加载完成初始化菜单
        initMenu();
    </script>
</body>
</html>
