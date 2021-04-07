شعار cgit	الفهرس : لينكس	

orange-pi-5.7
 
نواة لينكس	ميغوس
حول ملخص المراجع سجل شجرة الالتزام الصفحة الرئيسية فرق	

تسجيل الرسالة
 
 
المسار: الجذر / السائقين / صافي
خيارات فرق
سياق الكلام:	
3
الفراغ:	
يتجاهل
وضع:	
ssdiff
Diffstat (يقتصر على "السائقين / الشبكة")
-rw-r - r--	السائقين / صافي / إيثرنت / stmicro / stmmac / dwmac-sun8i.c	69	
تم تغيير 1 ملف ، 51 إدراجًا ، 18 حذفًا
diff --git a / drivers / net / ethernet / stmicro / stmmac / dwmac-sun8i.cb / drivers / net / ethernet / stmicro / stmmac / dwmac-sun8i.c 
index 58e0511badba..d1a47145fe4e 100644 
- a / drivers / net / ethernet / stmicro / stmmac / dwmac-sun8i.c
 +++ b / drivers / net / ethernet / stmicro / stmmac / dwmac-sun8i.c
-58،9 +58،13Struct emac_variant {
58		58	
59	/ * architecture sunxi_priv_data - احتفظ بجميع بيانات sunxi الخاصة	59	/ * architecture sunxi_priv_data - احتفظ بجميع بيانات sunxi الخاصة
60	 *tx_clk: إشارة إلى ساعة MAC TX	60	 *tx_clk: إشارة إلى ساعة MAC TX
61	 *ephy_clk: إشارة إلى ساعة EPHY الاختيارية لل PHY الداخلي	61	 *ephy_clk: إشارة إلى ساعة EPHY الاختيارية لـ
62	 * @ regulator: إشارة إلى المنظم الاختياري	62	 * PHY الداخلي
63	 *rst_ephy: إشارة إلى إعادة تعيين EPHY الاختيارية لطبقة PHY الداخلية	63	 *regulator_phy: إشارة إلى المنظم الاختياري
64	 *regulator_phy_io: إشارة إلى المنظم الاختياري لـ
65	 * دبابيس PHY I / O
66	 *rst_ephy: إشارة إلى إعادة تعيين EPHY الاختيارية لـ
67	 * PHY الداخلي
64	 * @ متغير: إشارة إلى متغير اللوحة الحالية	68	 * @ متغير: إشارة إلى متغير اللوحة الحالية
65	 *regmap: regmap لاستخدام syscon	69	 *regmap: regmap لاستخدام syscon
66	 *internal_phy_powered: هل تم تمكين PHY الداخلية	70	 *internal_phy_powered: هل تم تمكين PHY الداخلية
-69،7 +73،8architecture emac_variant {
69	هيكل sunxi_priv_data {	73	هيكل sunxi_priv_data {
70	        هيكل clk * tx_clk ؛	74	        هيكل clk * tx_clk ؛
71	        هيكل clk * ephy_clk ؛	75	        هيكل clk * ephy_clk ؛
72	        منظم الهيكل * منظم ؛	76	        منظم الهيكل * regulator_phy ؛
77	        منظم الهيكل * regulator_phy_io ؛
73	        هيكل reset_control * rst_ephy ؛	78	        هيكل reset_control * rst_ephy ؛
74	        إنشاء بنية emac_variant * البديل ؛	79	        إنشاء بنية emac_variant * البديل ؛
75	        هيكلة regmap_field * regmap_field ؛	80	        هيكلة regmap_field * regmap_field ؛
-544،23 +549،30static int sun8i_dwmac_init (Struct platform_device * pdev، void * priv)
544	        هيكل sunxi_priv_data * gmac = priv ؛	549	        هيكل sunxi_priv_data * gmac = priv ؛
545	        int متقاعد	550	        int متقاعد
546		551	
547	        إذا (gmac-> منظم) {	552	        ret = regulator_enable (gmac-> regulator_phy_io) ؛
548	                ret = regulator_enable (gmac-> regulator) ؛		
549	        إذا (يتراجع) {	553	        إذا (يتراجع) {
550	                        dev_err (& pdev-> dev، "فشل في تمكين المنظم \ n")؛	554	                dev_err (& pdev-> dev، "فشل في تمكين منظم PHY I / O \ n")؛
551	                عودة ret؛	555	                عودة ret؛
552	        }	556	        }
557	
558	        ret = regulator_enable (gmac-> regulator_phy) ؛
559	        إذا (يتراجع) {
560	                dev_err (& pdev-> dev، "فشل في تمكين منظم PHY \ n")؛
561	                انتقل إلى err_disable_regulator_phy_io ؛
553	        }	562	        }
554		563	
555	        ret = clk_prepare_enable (gmac-> tx_clk) ؛	564	        ret = clk_prepare_enable (gmac-> tx_clk) ؛
556	        إذا (يتراجع) {	565	        إذا (يتراجع) {
557	                إذا (gmac-> منظم)		
558	                        regulator_disable (gmac-> regulator) ؛		
559	                dev_err (& pdev-> dev، "تعذر تمكين ساعة AHB \ n")؛	566	                dev_err (& pdev-> dev، "تعذر تمكين ساعة AHB \ n")؛
560	                إعادة t urn ret؛	567	                go t o  e r r_disabl e _regula t or_phy ؛
561	        }	568	        }
562		569	
563	        العودة 0 ؛	570	        العودة 0 ؛
571	Err_disable_regulator_phy:
572	        regulator_disable (gmac-> regulator_phy) ؛
573	err_disable_regulator_phy_io:
574	        regulator_disable (gmac-> regulator_phy_io) ؛
575	        عودة ret؛
564	}	576	}
565		577	
566	شمس باطلة ثابتة 8i_dwmac_core_init (هيكل mac_device_info * hw ،	578	شمس باطلة ثابتة 8i_dwmac_core_init (هيكل mac_device_info * hw ،
-1017،8 +1029،8ستاتيك باطل sun8i_dwmac_exit (هيكلة platform_device * pdev، void * priv)
1017		1029	
1018	        clk_disable_unprepare (gmac-> tx_clk) ؛	1030	        clk_disable_unprepare (gmac-> tx_clk) ؛
1019		1031	
1020	        i f (gmac-> منظم)	1032	        regulator_d i sable (gmac-> regulator _phy ) ؛
1021	                regulator_disable (gmac-> regulator) ؛	1033	        regulator_disable (gmac-> regulator _phy_io ) ؛
1022	}	1034	}
1023		1035	
1024	sun8i_dwmac_set_mac_loopback (باطل __iomem * ioaddr ، تمكين منطقي)	1036	sun8i_dwmac_set_mac_loopback (باطل __iomem * ioaddr ، تمكين منطقي)
-1155،12 +1167،21static int sun8i_dwmac_probe (Struct platform_device * pdev)
1155	        }	1167	        }
1156		1168	
1157	        / * منظم اختياري لـ PHY * /	1169	        / * منظم اختياري لـ PHY * /
1158	        gmac-> regulator = devm_regulator_get_optional (dev، "phy") ؛	1170	        gmac-> regulator_phy = devm_regulator_get (dev، "phy") ؛
1159	        إذا (IS_ERR (gmac-> منظم)) {	1171	        إذا (IS_ERR (gmac-> regulator_phy)) {
1160	                إذا (PTR_ERR (gmac-> منظم) == -EPROBE_DEFER)	1172	                ret = PTR_ERR (gmac-> regulator_phy) ؛
1161	                        العودة -EPROBE_DEFER ؛	1173	                إذا (ret! = -EPROBE_DEFER)
1162	                dev_info (dev، "لم يتم العثور على منظم \ n")؛	1174	                        dev_err (dev، "Failed to get PHY regulator (٪ d) \ n"، ret)؛
1163	                gmac-> منظم = NULL ؛	1175	                عودة ret؛
1176	        }
1177	
1178	        / * منظم اختياري لدبابيس PHY I / O * /
1179	        gmac-> regulator_phy_io = devm_regulator_get (dev، "phy-io") ؛
1180	        إذا (IS_ERR (gmac-> regulator_phy_io)) {
1181	                ret = PTR_ERR (gmac-> regulator_phy_io) ؛
1182	                إذا (ret! = -EPROBE_DEFER)
1183	                        dev_err (dev، "Failed to get PHY I / O regulator (٪ d) \ n"، ret)؛
1184	                عودة ret؛
1164	        }	1185	        }
1165		1186	
1166	        / * قد يكون سجل "التحكم في ساعة GMAC" موجودًا في	1187	        / * قد يكون سجل "التحكم في ساعة GMAC" موجودًا في
-1250،6 +1271،17dwmac_exit:
1250	عودة ret؛	1271	عودة ret؛
1251	}	1272	}
1252		1273	
1274	sun8i_dwmac_shutdown ثابت باطل (هيكل platform_device * pdev)
1275	{
1276	        Struct net_device * ndev = dev_get_drvdata (& pdev-> dev) ؛؛
1277	        هيكل stmmac_priv * priv = netdev_priv (ndev) ؛
1278	        البنية sunxi_priv_data * gmac = priv-> plat-> bsp_priv ؛
1279	
1280	        dev_err (& pdev-> dev، "إيقاف التشغيل \ n") ؛
1281	        regulator_disable (gmac-> regulator_phy) ؛
1282	        regulator_disable (gmac-> regulator_phy_io) ؛
1283	}
1284	
1253	بنية ثابتة ثابتة of_device_id sun8i_dwmac_match [] = {	1285	بنية ثابتة ثابتة of_device_id sun8i_dwmac_match [] = {
1254	        {.comp Compatible = "allwinner، sun8i-h3-emac"،	1286	        {.comp Compatible = "allwinner، sun8i-h3-emac"،
1255	                .data = & emac_variant_h3} ،	1287	                .data = & emac_variant_h3} ،
-1270،6 +1302،7MODULE_DEVICE_TABLE (من ، sun8i_dwmac_match) ؛
1270	بنية ثابتة platform_driver sun8i_dwmac_driver = {	1302	بنية ثابتة platform_driver sun8i_dwmac_driver = {
1271	        .probe = sun8i_dwmac_probe ،	1303	        .probe = sun8i_dwmac_probe ،
1272	        .remove = stmmac_pltfr_remove ،	1304	        .remove = stmmac_pltfr_remove ،
1305	        .shutdown = sun8i_dwmac_shutdown ،
1273	        .driver = {	1306	        .driver = {
1274	                .name = "dwmac-sun8i" ،	1307	                .name = "dwmac-sun8i" ،
1275	                .pm = & stmmac_pltfr_pm_ops ،	1308	                .pm = & stmmac_pltfr_pm_ops ،
إذا كنت تريد الاتصال بي ، أرسل بريدًا إلكترونيًا إلى megous@megous.com .

الصفحة الرئيسية: https://megous.com . Markup reference for GitHub Docs <!-- omit in toc -->

## Table of contents <!-- omit in toc -->
- [Writing in Markdown](#writing-in-markdown)
- [Callout tags](#callout-tags)
  - [Usage](#usage)
- [Code sample syntax highlighting](#code-sample-syntax-highlighting)
  - [Usage](#usage-1)
- [Octicons](#octicons)
  - [Usage](#usage-2)
- [Operating system tags](#operating-system-tags)
  - [Usage](#usage-3)
- [Reusable and variable strings of text](#reusable-and-variable-strings-of-text)

## Writing in Markdown

[Markdown](http://daringfireball.net/projects/markdown/) is a human-friendly syntax for formatting plain text. Our documentation is written with [GitHub Flavored Markdown](https://docs.github.com/en/github/writing-on-github/about-writing-and-formatting-on-github), a custom version of Markdown used across GitHub.

This site's Markdown rendering is powered by [`/lib/render-content`](/lib/render-content), which is in turn built on the [`remark`](https://remark.js.org/) Markdown processor.

## Callout tags

Callouts highlight important information that customers need to know. We use standard formatting and colors for different types of callouts: notes, warnings, and danger notices. Use tags before and after the text you’d like included in the callout box.

### Usage

```
{% note %}

**Note:** Owners and administrators can add outside collaborators to a repository.

{% endnote %}
```

For information on when to use callout tags, see the [style guide](content-style-guide.md).

## Code sample syntax highlighting

To render syntax highlighting in command line instructions, we use triple backticks followed by the term `shell`.

### Usage

    ```shell
    git init <em>YOUR_REPO</em>
    ```

This syntax highlighting renders light text on a dark background, and should be reserved for command line instructions.

Within the command-line syntax, you can also use the `<em>` helper tag to indicate content that varies for each user, such as a user or repository name.

**Copy-able code blocks**

You can also add a header that includes the name of the language and a button to copy the contents of the code block:

    ```js{:copy}
    const copyMe = true
    ```

## Octicons

Octicons are icons used across GitHub’s interface. We reference Octicons when documenting the user interface. Find the name of the Octicon on the [Octicons site](https://primer.style/octicons). For accessibility purposes, use [the `aria-label` option](https://primer.style/octicons/packages/javascript#aria-label) to describe the Octicon.

### Usage

```
{% octicon "<name of octicon>" %}
{% octicon "plus" %}
{% octicon "plus" aria-label="The plus icon" %}
```

## Operating system tags

We occasionally need to write documentation for different operating systems. Each operating system may require a different set of instructions. We use operating system tags to demarcate information for each operating system.

### Usage

```
{% mac %}

These instructions are pertinent to Mac users.

{% endmac %}
```

```
{% windows %}

These instructions are pertinent to Windows users.

{% endwindows %}
```

```
{% linux %}

 These instructions are pertinent to Linux users.

{% endlinux %}
```

You can define a default platform in the frontmatter. For more information, see the [content README](../content/README.md#defaultplatform).

## Reusable and variable strings of text

Reusable strings (commonly called content references or conrefs) contain content that’s used in more than one place in our documentation and allow us to change the content in a single location rather than every place the string appears.

For longer strings, we use reusables, and for shorter strings, we use variables. For more information about reusables, see the [reusables README](../data/reusables/README.md). For more information about variables, see the [variables README](../data/variables/README.md).
