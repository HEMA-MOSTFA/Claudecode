# بحث جدوى: «بصمة موشن ستوديو» (Basma Motion Studio) كستارت أب

**تاريخ البحث:** 15 أكتوبر 2026 · **أعدّه:** Claude لإبراهيم (وكالة بصمة)

## ملاحظات منهجية (اقرأها الأول)

- **تعبير «موثّق»** معناه إني قرأت الصفحة الرسمية بنفسي في الجلسة دي (وهي: صفحة Anthropic Legal & Compliance، وصفحة دعم Claude، وشروط Consumer Terms، وREADME بتاع motion-starter-kit، وLICENSE.md بتاع Remotion على GitHub).
- **تعبير «من نتائج بحث»** معناه إن المعلومة جت من مقتطفات نتائج البحث أو من مواقع ثانوية، ومقدرتش أفتح الصفحة الأصلية. السبب إن الـ sandbox بتاعي ما قدرش يوصل لمواقع remotion.dev وlearn.microsoft.com وpolar.sh وtheregister.com (خطأ DNS). الأرقام دي لازم تتأكد من الموقع الرسمي قبل أي قرار مالي.
- **«غير مؤكد»** يعني معلومة مش لاقيلها مصدر كفاية. مفيش أي رقم أو سعر اتخمّن.
- الأقسام اللي معرفتش أبحث فيها بعمق (Captions/Descript/Higgsfield/Canva، وPaymob، ورسوم Cloudflare R2، وتراخيص الخطوط والموسيقى) معلّمة بوضوح، ومعتمدة على معرفة عامة لازم تتحقق.
- فصل المحتوى: **[حقيقة]** = موثّق أو من مصدر مذكور · **[استنتاج]** = تحليلي من الحقائق · **[فرضية]** = محتاجة تحقق.

---

# الملخص التنفيذي (10 أسطر)

1. **قابلة للتنفيذ؟** آه تقنيًا وقانونيًا، بشرط إن التطبيق يفضل «غلاف» حوالين Claude Code الأصلي بتاع المستخدم، من غير ما يلمس أي توكن.
2. **أكبر عائق:** مش التقنية. العائق هو **اعتماد منتج كامل على سياسة Anthropic اللي اتغيّرت 3 مرات في 2026** (يناير وفبراير وأبريل ومايو/يونيو/أكتوبر). صفحة Anthropic الرسمية دلوقتي بتسمح بالنمط ده بشروط، بس بتقول إن حدود Pro/Max «بتفترض استخدامًا عاديًا فرديًا».
3. **ثاني عائق: ترخيص Remotion.** الشركات اللي أكتر من 3 موظفين محتاجة ترخيص، ومش واضح مين اللي يدفع: أنت كبائع، ولا العميل. لازم رد مكتوب من Remotion قبل أي تسعير.
4. **التوقيع الرقمي:** Azure Artifact Signing (الأرخص، 9.99$/شهر) **مش متاح لمصر**. البديل شهادة OV بحوالي 220–440$ في السنة، أو MSIX عبر Microsoft Store (غير مؤكد، محتاج تحقق).
5. **الدفع:** Polar بتدعم مصر في قائمة دول الدفع (من نتائج البحث). Paddle وLemon Squeezy مش مؤكد.
6. **المنافسة:** مفيش منتج لاقيته بيجمع (Remotion + Claude Code بتاع المستخدم + عربي RTL). في منافسين عامين زي Motionvid.ai (199$/مستخدم/شهر) وvidio.ai. دي فجوة محتملة، **مش مثبتة**.
7. **أكبر خطر استراتيجي:** إن Anthropic نفسها (أو Conductor وأمثاله) تضيف الميزة أو تقفل الباب. لازم تبني `AgentAdapter` من اليوم الأول.
8. **التوصية:** كمّل، لكن كـ **تجربة سوق قبل بناء** لمدة 30 يوم، مش بناء كامل.
9. **أول 3 خطوات هذا الأسبوع:** (أ) ابعت إيميل لـ Anthropic (sales) ولـ Remotion بأسئلة محددة (نصهم تحت) · (ب) اعمل landing page عربية + قائمة انتظار + 10 مقابلات مع صنّاع محتوى ووكالات · (ج) ابني benchmark صغير يقارن Claude وCodex وOpenCode على نفس 3 تكليفات Remotion.
10. **قاعدة الإيقاف:** لو الرد القانوني من Anthropic أو Remotion سلبي، أو 10 مقابلات ما طلعوش بـ 3 عملاء مستعدين يدفعوا مقدم، **غيّر المسار** (مثلًا: المنتج يتحول لأداة مفتوحة + خدمة وكالة).

---

# المحور 1: أساسيات الستارت أب من نوع «واجهة فوق وكيل برمجة»

### حقائق
- **Conductor** (تطبيق Mac يشغّل Claude Code وCodex وCursor وOpenCode بالتوازي، كل واحد في git worktree): أعلنوا Series A بـ 22$ مليون من Spark وMatrix بتاريخ 30 مارس 2026. النسخة المحلية مجانية، وفي Pro بـ 50$/شهر وCloud مدفوع. Mac فقط. **مفيش أرقام إيرادات منشورة.** ([conductor.build](https://www.conductor.build/blog) · [rywalker.com](https://rywalker.com/research/conductor)) — *من نتائج بحث*
- **Claudia / opcode** (Tauri 2، ترخيص AGPL-3.0): مفتوح المصدر ومجاني، حوالي 20 ألف نجمة حسب مصدرين، **ومفيش نموذج ربح لاقيته**. مش تابع لـ Anthropic. ([implicator.ai](https://www.implicator.ai/claudia-gives-claude-code-a-gui-makeover-aiming-to-broaden-ai-coding-access/) · [claudelog](https://claudelog.com/addons/claudia)) — *من نتائج بحث*
- مقارنة لـ 42 تطبيق وكلاء برمجة وصفت **«الامتصاص من الشركة الأم»** كالخطر البنيوي الأول، لأن تطبيق Claude Code المكتبي الرسمي بقى فيه جلسات متوازية. ([rywalker.com](https://rywalker.com/research/mac-coding-agent-apps)) — *من نتائج بحث*
- تطبيق «Zad Loop» اللي ذكرته: **ملقتش عنه أي معلومة**، فمش هقارن بيه.

### استنتاجات
- الأدوات الأفقية («واجهة أحلى لـ Claude Code للمبرمجين») بتتأكل من الشركة نفسها. اللي بيعيش: **الأدوات العمودية** اللي جوّاها معرفة مجال وأصول جاهزة (هنا: ستايلات الموشن + RTL عربي + سير عمل مراجعة قبل الرندر).
- نموذج الربح عند المموَّلين: مجاني محلي + اشتراك مدفوع على السحابة. ده **مش** متاح لك (مفيش سيرفر بتشغّل عليه Claude بحسابهم). نموذجك الطبيعي: ترخيص للبرنامج + محتوى (ستايلات/تحديثات) مدفوع.
- **[فرضية]** قيمتك الحقيقية مش «الواجهة»، دي **مكتبة الستايلات + الـ pipeline المضبوط + الجودة العربية**.

---

# المحور 2: القانوني والسياسات (الأخطر)

## 2.1 Anthropic

### حقائق موثّقة (صفحة [Legal and compliance](https://code.claude.com/docs/en/legal-and-compliance) على code.claude.com، قريتها في 15 أكتوبر 2026؛ الصفحة نفسها ما عليهاش تاريخ تحديث)

1. الترخيص: *«Commercial Terms of Service – for Team, Enterprise, and Claude API users»* و*«Consumer Terms of Service – for Free, Pro, and Max users»*.
2. *«Advertised usage limits for Pro and Max plans assume ordinary, individual usage of Claude Code and the Agent SDK.»*
3. تحت عنوان **«Can customers offer Claude Code in their products?»**:
   - *«preinstalling or running Claude Code in your products or services ... requires agreeing to our Commercial Terms of Service and complying with the conditions below»*
   - *«The Claude Code binary must not be modified ... customers may not remove, disable, or restrict any authentication method built into it»*
   - *«Customers may not pay for, resell, or intermediate Claude usage on their end users' behalf. Each end user must authenticate with their own Anthropic API key, Claude subscription plan credentials, or 3P inference provider credential.»*
4. **«Authentication and credential use»:**
   - *«Anthropic does not permit third-party developers to offer Claude.ai login into their own applications, or to route requests through Free, Pro, or Max plan credentials on behalf of their users. Moreover, developers may not collect, store, or intermediate Claude.ai credentials or session tokens.»*
   - الفقرة اللي بعدها (**دي أهم جملة لمنتجك**): *«Nor does it prevent an end user from signing in to the unmodified Claude Code binary with their own Claude subscription, including where a platform hosts Claude Code as described under 'Can customers offer Claude Code in their products?' above.»*
5. *«Anthropic reserves the right to take measures to enforce these restrictions and may do so without prior notice.»*
6. **الاسم والشعار:** *«you can't use the Claude Code or Anthropic names or logos as part of your own product, feature, or company name ... or in a way that suggests Anthropic built, endorses, or is partnered with your product.»* مسموح تقول بنص عادي إن منتجك «يشغّل Claude Code».

**صفحة الدعم** [support.claude.com/en/articles/15036540](https://support.claude.com/en/articles/15036540) (قريتها اليوم):
- تحديث **7 أكتوبر 2026:** خطط Max وTeam فيها دلوقتي رصيد API شهري يغطي Agent SDK وclaude -p وClaude API وManaged Agents. ولسه ينفع تستخدم *«the Agent SDK, claude -p, and third-party apps with your subscription limits»*.
- تحديث **15 يونيو 2026:** التغييرات اللي كانت معلنة على استخدام Agent SDK **اتوقفت** («nothing has changed»).

**Consumer Terms** ([anthropic.com/legal/consumer-terms](https://www.anthropic.com/legal/consumer-terms)، Effective October 8, 2025 حسب النسخة اللي قريتها):
- البند 3 (7): الوصول الآلي (bots/scripts) ممنوع *«Except when you are accessing our Services via an Anthropic API Key or where we otherwise explicitly permit it»*.
- *«Use of our Services for evaluation purposes are for your personal, non-commercial use only»* وفي تنبيه إن Commercial Terms لا تشمل «Claude.ai or Claude Pro use». *(قد يكون في نسخة أحدث؛ غير مؤكد.)*

### من مصادر ثانوية (غير موثّق من Anthropic مباشرة)
- بدأ التنفيذ يناير 2026، وتحديث توثيق 19 فبراير 2026 منع استخدام OAuth tokens في أي أداة ثانية، وفي **4 أبريل 2026** ما بقاش اشتراك Claude يغطي أدوات الطرف الثالث زي OpenClaw (تسحب من «extra usage»). ([The Register](https://www.theregister.com/2026/04/06/anthropic_closes_door_on_subscription/) · [Engadget](https://www.engadget.com/ai/its-no-longer-free-to-use-claude-through-third-party-tools-like-openclaw-160912082.html) · [winbuzzer](https://winbuzzer.com/2026/02/19/anthropic-bans-claude-subscription-oauth-in-third-party-apps-xcxwbn/)) — *من نتائج بحث*
- في 13–14 مايو 2026 أُعلن رصيد برمجي منفصل من 15 يونيو، ثم اتوقف (كما في صفحة الدعم فوق).

### التحليل (استنتاج)
- **تصميمك (تشغيل `claude` الأصلي المثبّت عند المستخدم وهو مسجّل دخوله بنفسه، من غير ما تلمس توكن)** هو بالظبط النمط اللي الصفحة الرسمية بتقول إنه لا يتم منعه: *«an end user signing in to the unmodified Claude Code binary with their own subscription»*.
- الفرق الجوهري عن اللي اتمنع في أبريل: الأدوات الممنوعة كانت بتستخدم **توكن الاشتراك مباشرة** من برنامج غير Claude Code. أنت بتستخدم **الـ binary الرسمي**.
- **لكن في 4 مناطق رمادية لازم تتأكد منها مكتوب:**
  1. **«running Claude Code in your products ... requires agreeing to our Commercial Terms»**: هل لازم تفتح حساب Console وتقبل Commercial Terms كمطوّر حتى لو العميل هو اللي بيدخل باشتراكه؟ القراءة الحذرة: **آه**.
  2. **«ordinary, individual usage»**: لو عميل وكالة شغّل 30 فيديو في اليوم عبر `claude -p`، ممكن يتخطى «الاستخدام العادي». ده خطر على تجربة العميل، مش عليك قانونيًا.
  3. **Consumer Terms** على Pro/Max: مبدأيًا «non-commercial» لعبارة التقييم، ومنع الأتمتة «إلا لو سمحنا صراحة». الأقرب إن وكالة بتبيع خدمة فيديو للعملاء تستخدم **Team أو Max** وتتأكد. (غير مؤكد قانونيًا.)
  4. **عدم تعديل الـ binary وعدم تعطيل أي طريقة تسجيل دخول**: يعني ما تضيفش wrappers بتغيّر سلوكه، وماتعملش auto-login بتمرير توكنات.
- **مفيش بند اتحقق منه بيمنع استخدام التطبيق تجاريًا، لكن الخطر الفعلي هو «قابلية السياسة للتغيير بدون إشعار».**

### نص الإيميل المقترح لـ Anthropic (sales + legal)
> «We're building a Windows desktop app (Basma Motion Studio) that spawns the user's own installed, unmodified Claude Code CLI (`claude -p --output-format stream-json`) as a subprocess. The user signs in themselves through Anthropic's own flow; we never read, store or transmit credentials or tokens, and we don't resell or pay for usage. Does this fit the 'Can customers offer Claude Code in their products?' conditions? Do we need to sign the Commercial Terms? Are there rate-limit or "ordinary individual usage" expectations for batch agency use? May we say "Works with Claude Code" in plain text?»

## 2.2 Remotion

### حقائق
- **LICENSE.md على GitHub** (قريته): *«You are required to obtain a Company License to use Remotion»* لو مش من الفئات المؤهلة للترخيص المجاني. ومحظور *«copy or modify Remotion code for the purpose of selling, renting, licensing, relicensing, or sublicensing your own derivative of Remotion.»* ([remotion LICENSE.md](https://github.com/remotion-dev/remotion/blob/main/LICENSE.md))
- **من نتائج بحث لصفحات remotion.dev الرسمية (ما اتفتحتش عندي — لازم تتأكد):**
  - مجاني: فرد، أو شركة ربحية **حتى 3 موظفين**، ومؤسسات غير ربحية، والتقييم. ([pricing](https://www.remotion.dev/docs/license/pricing) · [terms](https://www.remotion.dev/docs/terms))
  - **Creators:** 25$/Seat/شهر.
  - **Automators:** 0.01$ لكل render، **حد أدنى 100$/شهر**، «للشركات اللي بتبني محررات فيديو وتطبيقات prompt-to-video». المطوّرين اللي على مشروع الأتمتة مش محتاجين Seat.
  - **Enterprise:** من 500$/شهر.
  - تعريف الأتمتة: امتلاك كود بينادي `renderMedia()` أو مكوّن `<Player>` برمجيًا.
  - في Remotion 5.0 يبقى `licenseKey` والـ telemetry **إلزامي** لعملاء Automators (حسب مقتطف؛ غير مؤكد). ([License FAQ](https://www.remotion.dev/docs/license/faq))

### التحليل (استنتاج)
- **الفئات الخضراء:** الفرد وشركة ≤3 موظفين = مجاني. وده **عملاءك الأقرب**: صنّاع محتوى فرديين ووكالات صغيرة.
- **السؤال المفتوح الأخطر:** التطبيق بيشغّل Remotion على جهاز العميل. مين «الشركة المستخدِمة»؟ (أ) العميل (فبيطبق عليه قاعدة ≤3 موظفين أو Creators) · (ب) أنت كمطوّر لتطبيق «prompt-to-video» (فهتتحاسب Automators على كل render، **حتى لو الرندر على جهاز العميل**؟). **مفيش مصدر لقيته بيجاوب.**
- لو (ب): الحد الأدنى 100$/شهر يعني منتج بـ 15$/شهر محتاج 7 عملاء بس عشان تغطي الترخيص. مش كارثة لكن لازم يدخل في التسعير.
- **حل تصميمي مقترح [فرضية]:** التطبيق **ما يضمّنش Remotion** ولا يوزعه، بل يثبّته عبر `npm` في مجلد المشروع عند المستخدم، ويعرض للمستخدم شرط الترخيص («Bring Your Own Remotion License»). ده بيقلل المخاطرة لكن مش بيلغيها.
- **خطة بديلة:** [HyperFrames](https://github.com/heygen-com/hyperframes) من HeyGen، ترخيص **Apache-2.0**، بيحوّل HTML لـ MP4 وجاهز للوكلاء (21 skill، Node ≥22). *(من نتائج بحث؛ تاريخ الإطلاق متضارب بين 10 مارس و17 أبريل 2026.)* ده يخليك مش مربوط بـ Remotion لو الرد سلبي. [فرضية] تحتاج benchmark جودة.

### نص الإيميل لـ Remotion
> «We build a desktop app that runs on end users' machines and uses Remotion Studio/renderMedia locally via a coding agent. Who needs a license: us as the app vendor (Automators), or each end user? Is a user with ≤3 employees covered by the free license when using Remotion through our app? How is telemetry/licenseKey handled in this case?»

## 2.3 ترخيص motion-starter-kit

### حقائق (README قريته من GitHub)
- ترخيص **MIT**، 10 ستايلات (plotter, doodle, whiteboard, chalkboard, stickman, isometric, fake3d, infographic, map-journey, product)، وبيشتغل مع Claude Code وCodex وAntigravity، والـ workflow مطابق لفكرتك (يحلل الستايل، يكتب السكريبت والـ scene plan، يبني في Remotion، يفتح Studio للمراجعة، ما يرندرش قبل الموافقة).
- المتطلبات: Node 18+ وffmpeg وuv، وحوالي **2 GB** (PyTorch + نموذج alignment) في أول استخدام لضبط توقيت الصوت، ومتصفح Remotion حوالي 90 MB.
- **16 نجمة و8 forks** فقط. README بيقول: الـ agent ياخد **الستايل فقط، مش اللوجوهات ولا النصوص ولا الصور**، ونصح باستخدام فيديوهات تملك حق التعلّم منها.
- README **ما يذكرش** الخطوط ولا تراخيص الصور المعاينة.

### التحليل
- MIT **تسمح** بالتضمين والبيع، بشرط الإبقاء على إشعار حقوق النشر. لكن MIT تغطي كود المشروع فقط، **مش بالضرورة** صور المعاينة أو أي أصول أو فيديوهات مرجعية جايبها المؤلف من طرف تاني. لازم تجرد كل ملف في `styles/` و`reference/` و`public/`.
- **16 نجمة = مشروع صغير جدًا.** خطر الاعتماد: المؤلف يتوقف أو يغيّر الترخيص في النسخ الجاية. **اتواصل مع المؤلف (motalim-ai)** واعرض شراكة أو اتفاق مكتوب، وخد snapshot بالنسخة الحالية.
- **«تعلّم الستايل من فيديو مرجعي»:** عمومًا الأسلوب البصري كفكرة يختلف عن التعبير المحمي بحقوق النشر. لكن **ما لقيتش مصدر قانوني مصري/دولي مدقق** في الجلسة، وبالتالي: غير مؤكد. **إجراءات حماية مقترحة:** (1) ماتشحنش أي فيديو مرجعي مع التطبيق، (2) المستخدم يرفع فيديوه الخاص ويقر بملكيته/حقه، (3) الفيديو يفضل محلي على جهازه ومايترفعش لسيرفرك، (4) شروط استخدام صريحة. وخد استشارة محامٍ متخصص في الملكية الفكرية قبل التسويق للميزة دي تحديدًا.

## 2.4 الخطوط والموسيقى والمؤثرات والأصول المولّدة
*(لم أبحث في الجلسة دي؛ ما يلي معرفة عامة تحتاج تحقق مصدريًا.)*
- **الخطوط:** استخدم خطوط OFL فقط (Cairo, Tajawal, IBM Plex Sans Arabic, Noto Naskh/Kufi) المسموح تجاريًا والتضمين. ابعد عن الخطوط المدفوعة والمأخوذة من مواقع «مجانية» بدون ترخيص.
- **الموسيقى والمؤثرات:** لا تضمّن أي ملف إلا بترخيص صريح يسمح بإعادة التوزيع داخل منتج. الأسلم: **لا تشحن موسيقى**، واربط بمصادر المستخدم.
- **الأصول المولّدة (صور/صوت من ElevenLabs أو غيره):** كل خدمة ليها شروط خاصة بالاستخدام التجاري والصوت المستنسخ. ارجع لشروط كل مزوّد واعرضها للمستخدم.

---

# المحور 3: التوزيع الاحترافي على Windows

### حقائق (من نتائج بحث؛ الصفحة الأصلية على learn.microsoft.com ما فتحتش)
- **Azure Artifact Signing** (الاسم الجديد لـ Trusted Signing): 9.99$/شهر لحد 5,000 توقيع. الأفراد لازم يكونوا في **أمريكا أو كندا**. المنظمات: أمريكا وكندا والاتحاد الأوروبي وبريطانيا وغيرها. **مصر مش في القائمة** فرد أو منظمة. ([Microsoft quickstart](https://learn.microsoft.com/en-us/azure/artifact-signing/quickstart) · [devclass](https://www.devclass.com/security/2026/01/14/code-signing-windows-apps-may-be-easier-and-more-secure-with-new-azure-artifact-service/4079554))
- Microsoft بتنصح اللي خارج المناطق المؤهلة بشهادات OV من DigiCert أو Sectigo أو GlobalSign. ([Windows apps code signing options](https://learn.microsoft.com/en-us/windows/apps/package-and-deploy/code-signing-options))
- أسعار تقريبية من مقارنات ثانوية: Sectigo OV من حوالي **220$/سنة**، DigiCert OV من حوالي **439$/سنة**. SSL.com عندها شهادة Individual Validated (السعر ما ظهرش). **سمعة SmartScreen بتتبني مع الوقت** ولو شهادة EV. ([sslinsights](https://sslinsights.com/digicert-vs-sectigo-code-signing/))
- شهادة Certum المفتوحة: **غير مؤكد** إنها تنفع للتوزيع العام.

### توصية
1. **الأرخص عمليًا لفرد في مصر [استنتاج]:** شهادة OV/IV من CA أو reseller معتمد (200–450$/سنة). تحقق من متطلبات التحقق من الهوية للأفراد في مصر قبل الشراء. ([Microsoft Store كبديل: MSIX يُوقَّع من المتجر ويتجاوز SmartScreen، لكن رسوم حساب المطوّر وإتاحته لمصر **غير مؤكدين**؛ تحقق.])
2. **للمرحلة الأولى (presales/beta):** وزّع نسخة غير موقعة على عدد صغير مع شرح تخطي SmartScreen، **وماتصرفش فلوس على شهادة** قبل ما يتحقق الطلب.
3. **بديل:** تأسيس كيان في دولة مؤهلة (US/UK/EU) يفتح لك Artifact Signing ويحل مشكلة الدفع أيضًا (شوف المحور 6). *(شروط التحقق وخبرة الشركة المطلوبة غير مؤكدة؛ تحقق.)*

### باقي عناصر التوزيع
*(معرفة عامة + مصدر Keygen، ولا مصادر رسمية إضافية في الجلسة؛ تحقق منها.)*
- **التغليف:** `electron-builder` → NSIS installer (الأبسط)، مع `electron-updater` للتحديث التلقائي. التحديثات من GitHub Releases (مجاني) أو Cloudflare R2.
- **Crash reporting:** Sentry (مستوى مجاني)، أو Electron `crashReporter` لسيرفر خاص.
- **التيليمتري:** opt-in واضح، مجهول الهوية، بدون محتوى المستخدم أو prompts. وثّقها في سياسة خصوصية (مهم لأنك بتتعامل مع محتوى عملاء).
- **تثبيت غير التقنيين (Node/ffmpeg/uv):** أول تشغيل يعمل «فحص بيئة» ثم يحمّل الناقص تلقائيًا في مجلد التطبيق (portable Node + ffmpeg static + uv) بدل ما يطلب من المستخدم يثبّت يدويًا. حمّل نموذج الـ alignment الـ 2 GB عند الحاجة فقط مع شريط تقدم، واحتفظ ببدائل أخف.
- **تثبيت Claude Code نفسه:** **ما تضمّنوش في installer** لو عايز تقلل المخاطر القانونية. وجّه المستخدم لتثبيت الرسمي والدخول بنفسه، وتطبيقك يتحقق من وجوده فقط.

---

# المحور 4: الربط بوكلاء آخرين

| الوكيل | Headless | تدفق الإخراج | اشتراك بدل API | ترخيص | ملاحظات |
|---|---|---|---|---|---|
| **Claude Code** | `claude -p` | `--output-format stream-json` | آه (بشروط المحور 2) | تجاري/ملكي | الأساس |
| **Codex CLI** | `codex exec` | `--json` (JSONL) | آه بخطط ChatGPT (Plus/Pro/Business...)؛ OpenAI قالت إنها عايزة الناس تستخدم اشتراكها «wherever they like» (مصدر ثانوي) | غير مؤكد (أظن مفتوح المصدر؛ تحقق) | تحذير: الطريق عبر backend خاص ممكن يتغير |
| **Gemini CLI** | `-p` أو non-TTY | `--output-format stream-json` أحداث: `init`, `message`, `tool_use` | غير مؤكد | غير مؤكد | بدون stream-json input، وتقرير إن `--approval-mode` بلا أثر في headless (كل الأدوات تتوافق تلقائيًا) |
| **OpenCode** | `opencode run` | `--format json` (nd-JSON: step-start/text/step-finish) | دخول ChatGPT OAuth مدعوم (يحتاج متصفح على نفس الجهاز) | غير مؤكد (تحقق) | متعدد المزوّدين |
| **Aider** | لم أبحث | — | — | — | أنسب للتعديل على ملفات من بناء مشاريع كاملة؛ **أولوية منخفضة** |

المصادر: [Gemini CLI headless](https://www.geminicli.com/docs/cli/headless) · [OpenCode CLI](https://opencode.ai/docs/en/cli) · [Codex subscription (ثانوي)](https://codex.danielvaughan.com/2026/04/24/codex-subscription-api-programmatic-access-gpt-5-5-chatgpt-plan/) — *كلها من نتائج بحث*.

### جودة توليد كود Remotion
**ما اتختبرتش.** أي ترتيب جودة دلوقتي تخمين. اعمل **benchmark بسيط**: نفس 3 تكليفات (ستايل whiteboard وisometric وmap-journey) × 3 وكلاء، وقيّم: (1) هل يبني من غير أخطاء، (2) كم محاولة تصحيح، (3) جودة RTL والنص العربي، (4) الوقت والتكلفة.

### الترتيب المقترح للمرحلة الثانية [استنتاج]
1. **Codex CLI:** الاشتراك مدعوم رسميًا حسب مصدر ثانوي، وأكبر قاعدة مستخدمين خارج Anthropic.
2. **OpenCode:** adapter واحد = وصول لمزوّدين كتير (بما فيهم موديلات أرخص/محلية)، تدعم من ليس عنده اشتراك.
3. **Gemini CLI:** ثالثًا بسبب ضعف التحكم في headless حسب التقرير الثانوي. *(المستوى المجاني: غير مؤكد.)*

**قرار معماري:** ابنِ `AgentAdapter` (واجهة موحدة: `start(prompt, cwd)`, `onEvent`, `cancel`, `healthCheck`) من اليوم الأول، وأضف عقد اختبار (contract tests) على نموذج أحداث stream-json، لأن تغيير الصيغة خطر حقيقي.

---

# المحور 5: المنافسة والسوق

### حقائق (من نتائج بحث)
- **HyperFrames** (HeyGen، Apache-2.0): إطار HTML→MP4 للوكلاء. منافس غير مباشر وبديل تقني.
- **Motionvid.ai:** منصة motion graphics بالـ AI تدعم الإنجليزي والعربي، بسعر **199$ لكل مستخدم/شهر**. ([zoftwarehub](https://zoftwarehub.com/products/motionvid-ai/overview?click=tab))
- **vidio.ai:** مولّد motion graphics من prompt، ويدّعي أكتر من مليون مستخدم (ادعاء تسويقي).
- **Mootion، Simplified (فيديو عربي بسكريبت وصوت)، CapCut (قوالب عربية).**
- **Remotion نفسه:** بيدفع باتجاه أدوات prompt-to-video عبر ترخيص Automators، أي إنه يسمح بوجود منافسين.
- Captions وDescript وHiggsfield وCanva: **لم أبحث فيها** في الجلسة. موقعها [فرضية]: Captions/Descript = تحرير فيديو ببشر، Higgsfield = توليد بصري، Canva = قوالب جاهزة؛ كلهم SaaS مغلق وبدون «كود مفتوح قابل للتعديل».

### الفجوة المحتملة [فرضية تحتاج تحقق بالمقابلات]
1. **عربي أولًا:** RTL وخطوط وصوت وتوقيت عربي حقيقي، مش ترجمة.
2. **تكلفة صفر على الـ AI من جهتك:** العميل يستخدم اشتراكه الحالي، فمفيش «credits» تنفد.
3. **مخرجات كود قابلة للتعديل:** مش فيديو مقفول. كل مشهد مكوّن React/Remotion.
4. **مراجعة قبل الرندر:** مناسب لسير عمل الوكالات.
5. **سعر أرخص بكثير** من 199$.

### عميلك الأول بالتحديد [فرضية]
**صانع محتوى/مونتير أو وكالة صغيرة (1–3 أشخاص) في مصر والخليج**، بتنتج فيديوهات شرح (explainer) أسبوعيًا للعملاء أو لقناتها، **عندها فعلًا اشتراك Claude** (أو مستعد يشتريه)، وبتصرف حاليًا وقت مونتير أو اشتراك Canva/Animaker. الوكالات ≤3 موظفين أيضًا تحت حد الترخيص المجاني لـ Remotion، وده توافق مفيد.
**ابدأ بنفسك:** وكالة «بصمة» هي حالة الاستخدام الأولى (dogfooding). وثّق التوفير الفعلي في الوقت والتكلفة كدليل تسويقي.

---

# المحور 6: المدفوعات والتسعير من مصر

### حقائق (من نتائج بحث)
| الخدمة | الرسوم | السحب | مصر |
|---|---|---|---|
| **Polar** (MoR) | 5% + 50¢ للحسابات الجديدة بعد 27 مايو 2026 (4%+40¢ لقدام)؛ **المصادر متضاربة** | عبر Stripe Connect Express؛ انتظار 7 أيام للمنظمات الجديدة؛ يجوز حجز الأموال حتى 120 يومًا لأسباب مخاطر | **مدرجة في قائمة دول الدفع** حسب docs ([Polar supported countries](https://polar.sh/docs/merchant-of-record/supported-countries)) |
| **Paddle** (MoR) | 5% + 0.50$ | شهريًا، حد أدنى 100$، تحويل بنكي أو Payoneer، 15$ SWIFT لبعض الدول | **غير مؤكد**؛ Paddle بتقول «200+ دولة» لكن ما اتحققتش من مصر |
| **Lemon Squeezy** (تابعة لـ Stripe) | 5% + 0.50$ + رسوم إضافية للدفع الدولي (1.5%) والاشتراكات (0.5%) | حد أدنى 50$؛ حساب غير أمريكي 1% | **غير مؤكد**؛ بتتحول لـ Stripe Managed Payments |
| **Gumroad** (MoR من 1 يناير 2025) | غير مؤكد | بنك محلي ممكن؛ Payoneer **غير مدعوم**؛ PayPal لمصر محل شك | **غير مؤكد** |
| **Paymob** | — | — | **لم أبحث**؛ للدفع المحلي بالجنيه فقط |

المصادر: [Polar vs Paddle vs Lemon Squeezy](https://www.buildmvpfast.com/blog/lemon-squeezy-vs-polar-paddle-merchant-of-record-2026) · [Paddle payouts](https://www.paddle.com/help/manage/get-paid/when-and-how-do-i-get-paid) · [Gumroad](https://gumroad.com/help/article/13-getting-paid).

### التحليل
- **MoR (Merchant of Record)** أهم لك من Stripe مباشر لأنه بيتولى ضريبة المبيعات/VAT العالمية. ده بيريحك من كيان ضريبي في كل بلد.
- **الأرجح: ابدأ بـ Polar** (مصر مدرجة)، **وجرّب التسجيل فعليًا بحساب اختباري قبل ما تبني عليه**. احتفظ بـ Paddle كبديل لو ثبت دعمها.
- **هل يلزم كيان خارجي؟** الـ MoR نفسه غالبًا **لا** (فرد). لكن كيان US/UK بيفتح لك Stripe مباشر وAzure Artifact Signing. **غير مؤكد** كم تكلفة وتعقيد التأسيس؛ حدّده لاحقًا لو نجح السوق.
- **الدفع المحلي (Paymob/Fawry):** مفيد للسوق المصري بالجنيه لو الطلب المحلي كبير؛ **لم أبحث فيه.**

### ثلاثة نماذج تسعير [فرضية — الأسعار اقتراحات للاختبار مش مبنية على بيانات سوق]
| النموذج | شكله | مزايا | عيوب | الحماية من القرصنة |
|---|---|---|---|---|
| **A. مرة واحدة** | مثلًا 79–149$ lifetime للنسخة الحالية + تحديثات الستايلات سنة | سهل الشراء، مناسب للمستقلين | مفيش إيراد متكرر؛ تكلفة دعم مستمرة | مفتاح ترخيص + تفعيل على جهازين، تحقق دوري |
| **B. اشتراك** | مثلًا 9–19$/شهر أو 79–149$/سنة | إيراد متكرر، يمول تحديث الستايلات | مقاومة من فئة تكره الاشتراكات | تحقق من الحساب؛ تعطيل التفعيل عند الإلغاء |
| **C. ترخيص بالمفتاح (Seat/وكالة)** | مفتاح للمقعد، باقة وكالة (3–5 مقاعد) | مناسب للوكالات والفواتير | عبء إدارة | Keygen أو ما يعادله، ربط بالجهاز |

**توصية [استنتاج]:** عرض **هجين**: اشتراك سنوي للستايلات والتحديثات + «lifetime» بسعر أعلى للمتبنين الأوائل (presales). ضع سعر الـ Remotion Automators ($100 حد أدنى، لو انطبق) في الحسبة قبل تثبيت الأرقام.
**القرصنة:** مفيش حماية كاملة في Electron. اعمل ترخيص بسيط بمفتاح مرتبط بحساب، ووفر قيمة مستمرة (ستايلات جديدة، تحديثات، دعم) بدل الاعتماد على القفل. **Keygen** (محلي/سحابي) مصدره ثانوي: يبدأ من حوالي 49–79$/شهر في Capterra، ومفتوح المصدر وقابل للاستضافة الذاتية. ([keygen.sh/for-electron-apps](https://keygen.sh/for-electron-apps/)) — *تحقق من السعر الرسمي.*

---

# المحور 7: المواقع والخدمات المطلوبة

*(الأسعار تقريبية من معرفة عامة ما لم يُذكر مصدر؛ **كلها تحتاج تحقق** قبل الشراء.)*

| البند | الاسم المقترح | الغرض | التكلفة التقريبية | إلزامي للإطلاق؟ | بديل أرخص |
|---|---|---|---|---|---|
| دومين | Cloudflare Registrar / Namecheap | عنوان المنتج | ~10–15$/سنة | نعم | .com عادي |
| Landing page | Vercel أو Cloudflare Pages | قائمة انتظار وتسويق | مجاني | نعم (لأول خطوة) | GitHub Pages |
| قاعدة بيانات/حسابات | Supabase | حسابات، قائمة انتظار، ترخيص | مستوى مجاني | لاحقًا (قبل الإطلاق المدفوع) | Cloudflare D1 |
| نظام التراخيص | Keygen (أو ميزة license keys في Polar إن وُجدت — غير مؤكد) | تفعيل وتحقق | من 0 (self-host) إلى ~49–79$/شهر | نعم قبل البيع | نظام بسيط على Supabase |
| الدفع | Polar (أو Paddle) | استقبال الأموال | 5% + 50¢ تقريبًا | نعم | Gumroad (غير مؤكد لمصر) |
| التحديث والتوزيع | GitHub Releases / Cloudflare R2 | استضافة installer والتحديثات | مجاني (GitHub)؛ R2: لم أتحقق من الأسعار | نعم | GitHub Releases |
| التحليلات | Plausible / PostHog (opt-in داخل التطبيق) | سلوك الموقع والاستخدام | مجاني–~9$/شهر | لاحقًا | Cloudflare Web Analytics |
| الدعم والمجتمع | WhatsApp Business + Discord/Telegram | دعم وتغذية راجعة | مجاني | نعم (واتساب لسوقك) | Telegram فقط |
| البريد | Resend / Zoho Mail | إيميلات المعاملات والنشرة | مجاني–~10$ | نعم (بسيط) | Gmail مع دومين |
| التوقيع الرقمي | شهادة OV (CA/reseller) | إزالة تحذيرات Windows | ~220–440$/سنة (ثانوي) | **لاحقًا** (بعد التحقق من الطلب) | Microsoft Store (غير مؤكد) |
| تتبع الأخطاء | Sentry | تقارير crash | مستوى مجاني | لاحقًا | `crashReporter` + ملف سجل |

**ملاحظة:** أدوات Vercel وSupabase وCloudflare متاحة عندك كتكاملات في Claude، فتقدر تجهّزها سريعًا.

---

# المحور 8: خطة MVP وتحقق السوق

### أصغر نسخة قابلة للبيع
1. تثبيت NSIS + فحص بيئة أول تشغيل (Node/ffmpeg/uv) تلقائي.
2. اكتشاف `claude` الموجود + دخول المستخدم بنفسه.
3. **3 ستايلات فقط** (مثلًا whiteboard وinfographic وproduct) بدل 10، بجودة ممتازة بالعربي.
4. سير العمل: موضوع → مشاهد → فتح Remotion Studio → موافقة → رندر.
5. ترخيص بسيط بمفتاح.

### نحذف من MVP
- «إضافة ستايل من فيديو مرجعي» (خطر قانوني ومعقد؛ يأتي كنسخة ثانية).
- الوكلاء الآخرين (فقط `AgentAdapter` جاهز).
- حسابات سحابية ومزامنة وTeam features.
- أي توقيع رقمي مدفوع قبل ظهور الطلب.

### التحقق قبل البناء الكامل
1. **أسبوع 1:** landing بالعربي + فيديو demo 60 ثانية من نموذجك الأولي + قائمة انتظار. شغّل 100–200$ إعلانات صغيرة أو انشر في مجموعات صنّاع المحتوى (لو لسه مفيش ميزانية، المجموعات والمجتمعات المجانية فقط).
2. **أسبوع 1–2:** 10 مقابلات (5 صناع محتوى + 5 وكالات). اسأل عن آخر فيديو explainer عملوه، كام ساعة أخد، كام كلّف، وهل عندهم اشتراك Claude.
3. **أسبوع 2–3:** presales: 20–50$ مقدم أو lifetime مخفض للـ 20 الأوائل عبر Polar.
4. **أسبوع 3–4:** خلّي 5 مستخدمين يجربوا النموذج على أجهزتهم (جلسة screen-share) وقيس: نسبة نجاح التثبيت، ونسبة نجاح أول فيديو، والوقت.

### مؤشرات القرار [فرضية — العتبات اقتراحات لازم تعدلها حسب ثقتك]
| القرار | الإشارة |
|---|---|
| **كمّل** | ≥3 مدفوعين مقدم (أو ≥30 في الانتظار بتفاعل حقيقي)، ونجاح أول فيديو عند ≥3 من 5 مجربين، وردود Anthropic/Remotion مقبولة |
| **غيّر** | اهتمام عالي لكن لا يدفعون، أو الفائدة الحقيقية في «خدمة الوكالة» لا «البرنامج»، أو رد Remotion يفرض تكلفة تقتل التسعير (انتقل لـ HyperFrames أو لنموذج الوكالة) |
| **وقّف** | رد قانوني سلبي من Anthropic، أو <10 مهتمين فعليين بعد 10 مقابلات وحملة |

---

# المحور 9: خارطة 30/60/90 بالبوابات

### 0–30 يوم: «هل الفكرة مسموحة ومطلوبة؟»
- إيميلات Anthropic وRemotion وتواصل مع مؤلف motion-starter-kit.
- Benchmark الوكلاء (3 تكليفات × Claude/Codex/OpenCode).
- Landing + قائمة انتظار + 10 مقابلات + فيديو demo.
- **بوابة 1 (لازم كل ده):** (أ) رد مكتوب أو على الأقل صياغة واضحة من Anthropic وRemotion، (ب) ≥3 مدفوعين مقدم أو ≥30 في الانتظار، (ج) benchmark يثبت إن Claude يبني ستايل واحد بنجاح ≥70% من المحاولات. **لو فشلت (أ) أو (ب): ارجع للمحور 8 وقرر «غيّر/وقّف».**

### 31–60 يوم: «هل يشتغل على أجهزة غرباء؟»
- Electron + `AgentAdapter` + فحص بيئة + 3 ستايلات + ترخيص بسيط.
- Beta مغلق لـ 10 مستخدمين (بدون توقيع، أو بتوقيع لو اتبررت التكلفة).
- Sentry + تيليمتري opt-in.
- **بوابة 2:** ≥7 من 10 مستخدمين ينتجون فيديو كامل بدون مساعدة مباشرة في أول جلسة، وزمن أول فيديو ضمن ما يعتبرونه مقبولًا، وأقل من X% كراشات (حدّد X مع أول بيانات).

### 61–90 يوم: «هل يدفعون بتكرار؟»
- فتح البيع (Polar)، شهادة توقيع، auto-update.
- Adapter ثاني (Codex) لو اتبرر بالطلب.
- 3 ستايلات إضافية بالتدريج، وتحسين RTL.
- **بوابة 3:** ≥15–25 عميل مدفوع (العتبة فرضية)، وإيراد يغطي الأدوات والتراخيص، واحتفاظ ≥50% بعد شهر. بعدها فكر في الستايل المخصص من فيديو.

---

# المحور 10: المخاطر الكبرى (مرتبة بالأثر × الاحتمال)

| # | الخطر | الأثر | الاحتمال | الإجراء |
|---|---|---|---|---|
| 1 | **Anthropic تغيّر/تشدّد السياسة** (حصل 3 مرات في 2026) | قاتل | عالٍ | إيميل مكتوب؛ `AgentAdapter`؛ لا تجمع توكنات إطلاقًا؛ وضع API key كخيار للمستخدم؛ لا تعتمد تسويقيًا على «مجاني» |
| 2 | **ترخيص Remotion** يطبَّق عليك كـ Automators أو يتغير | عالٍ | متوسط | رد مكتوب؛ BYO License؛ خطة HyperFrames؛ ضع الحد الأدنى 100$ في الحسبة |
| 3 | **امتصاص الميزة من الشركة الأم أو منافس كبير** (Anthropic Claude Code Desktop، HeyGen HyperFrames، Canva) | عالٍ | متوسط–عالٍ | ركّز على العربي والعمودي والمجتمع والستايلات المميزة، مش على الواجهة |
| 4 | **تغيير صيغة stream-json أو سلوك CLI** | متوسط–عالٍ | متوسط | contract tests؛ تثبيت إصدارات مدعومة؛ رسالة واضحة للمستخدم؛ fallback |
| 5 | **حدود الاشتراك** (عميل وكالة ينفد رصيده بسرعة) | متوسط | عالٍ | إدارة طابور وحدود؛ توعية؛ ترقية لـ Max/Team |
| 6 | **اعتماد على مشروع صغير (16 نجمة)** | متوسط | متوسط | اتفاق مع المؤلف؛ fork داخلي؛ جرد الأصول |
| 7 | **SmartScreen/تحذيرات التوقيع** تفقد الثقة | متوسط | عالٍ | شهادة بعد التحقق؛ دليل تثبيت؛ Microsoft Store كبديل (غير مؤكد) |
| 8 | **الملكية الفكرية في «الستايل من فيديو مرجعي»** | متوسط–عالٍ | متوسط | تأجيل الميزة؛ إقرار ملكية؛ معالجة محلية؛ استشارة محامٍ |
| 9 | **الدفع/السحب من مصر** يتعطل أو يتأخر (حجز 120 يوم في Polar) | متوسط | متوسط | اختبار تسجيل مبكر؛ بديلان؛ عدم الاعتماد على الإيراد في أول 90 يوم |
| 10 | **جودة الوكلاء الأخرى ضعيفة في Remotion** | منخفض–متوسط | غير معروف | benchmark قبل الوعد |

---

# جدول قرارات تحتاج منك قرارًا

| القرار | الخيارات | توصيتي |
|---|---|---|
| هل تكمل المشروع؟ | كمّل / وقّف / غيّر | **كمّل بتجربة سوق 30 يوم** (بوابة 1) |
| هل تتواصل مع Anthropic وRemotion قبل البناء؟ | آه / لا | **آه فورًا** (النصوص أعلاه) |
| تضمين Remotion أم BYO License؟ | تضمين / BYO / HyperFrames | **BYO + خطة HyperFrames**، حتى يوضح Remotion |
| تضمين Claude Code في الـ installer؟ | آه / لا | **لا**، المستخدم يثبّته بنفسه |
| عدد الستايلات في MVP | 3 / 10 | **3** |
| الدفع | Polar / Paddle / Gumroad | **Polar بعد اختبار تسجيل فعلي**، Paddle بديل |
| التسعير | مرة / اشتراك / هجين | **هجين** (اختبره في presales) |
| التوقيع الرقمي | الآن / بعد الطلب | **بعد الطلب** (OV) |
| تأسيس كيان خارجي؟ | الآن / لاحقًا | **لاحقًا**، بعد بوابة 2 |
| ميزة الستايل من فيديو مرجعي | MVP / لاحقًا | **لاحقًا** مع حماية قانونية |
| الوكيل الثاني | Codex / OpenCode / Gemini | **Codex ثم OpenCode**، بعد benchmark |
| اسم المنتج | الحالي / بديل | **غيّر** (الاسم الحالي عام ومحتمل التعارض) |

---

# Backlog للـ MVP (مرتب)

**P0: قبل أي كود**
1. إيميل Anthropic + إيميل Remotion + تواصل مع مؤلف motion-starter-kit.
2. Landing page عربية + قائمة انتظار + فيديو demo.
3. جدولة 10 مقابلات.
4. Benchmark الوكلاء (3 تكليفات × 3 وكلاء).
5. جرد كل أصول motion-starter-kit (خطوط/صور/صوت/ترخيص).

**P1: التطبيق**
6. هيكل Electron + `electron-builder` NSIS.
7. فحص بيئة أول تشغيل (Node/ffmpeg/uv) وتحميل تلقائي.
8. اكتشاف `claude` وفحص تسجيل الدخول (من غير لمس توكن).
9. `AgentAdapter` + محلل stream-json + عقد اختبار.
10. مكتبة 3 ستايلات (whiteboard / infographic / product) مع RTL وخطوط OFL.
11. سير العمل: موضوع → سكريبت ومشاهد → Remotion Studio → موافقة → رندر.
12. ترخيص بالمفتاح (Keygen أو Supabase) + تفعيل جهازين.
13. Sentry + تيليمتري opt-in + سياسة خصوصية.

**P2: قبل البيع**
14. Polar (اختبار تسجيل ثم منتجات) + صفحة شراء.
15. electron-updater + GitHub Releases.
16. شهادة OV (بعد تأكيد الطلب).
17. شروط استخدام + إقرار ملكية.
18. دليل تثبيت عربي مصوّر + قناة دعم واتساب/Discord.

**P3: بعد الإطلاق**
19. Adapter Codex، ثم OpenCode.
20. بقية الستايلات.
21. الستايل من فيديو مرجعي (بعد استشارة قانونية).

---

# 5 أسماء بديلة وفحص التعارض

**تنبيه:** فحصي اقتصر على **بحث ويب عام**. ما استخدمتش قواعد بيانات العلامات التجارية (USPTO / EUIPO / WIPO / المكتب المصري). أي اسم تختاره لازم تفحصه رسميًا قبل الاعتماد. وللتنبيه: ما ينفعش تستخدم اسم «Claude» أو «Claude Code» أو «Anthropic» في اسم المنتج (حسب صفحة Anthropic فوق).

| الاسم | المعنى | نتيجة بحث الويب | الحالة |
|---|---|---|---|
| **Lamha — لمحة** | لقطة/ومضة | لم يظهر منتج بنفس الاسم في الفئة | محتمل، لكن الكلمة شائعة؛ افحص النطاق والعلامة |
| **Tahreek — تحريك** | animation | لم يظهر منتج بنفس الاسم | محتمل؛ النطق صعب لغير العرب |
| **Mashhad — مشهد** | scene | لم يظهر برنامج بنفس الاسم (ظهرت Al Mashhad كشركة إعلامية في الشرق الأوسط، وMashMe تطبيق كرواتي قريب لفظيًا) | **انتبه** للتشابه مع شركة Al Mashhad الإعلامية |
| **Qalam Motion — قلم موشن** | قلم + حركة | لم يظهر | محتمل؛ لكن «Qalam» اسم شائع لمنتجات كتير |
| **Rasm — رسم** | رسم/ترسيم | لم يظهر منتج في الفئة (ظهرت أدوات أخرى عامة) | محتمل؛ كلمة قصيرة وعامة، صعبة التسجيل |

اسم «Basma Motion Studio» الحالي: لم أجد منتجًا بنفس الاسم في البحث، لكن «Motion Studio» عبارة وصفية عامة (ظهرت منتجات باسم Motion Studio وStop Motion Studio)، فصعب تسجيلها كعلامة. **أنصح بعلامة مميزة + وصف**، مثل «Mashhad — Motion Studio for Claude Code users» (والعبارة الوصفية بنص عادي، مش جزء من الاسم).

---

# المصادر الرئيسية

**موثّقة (قريت الصفحة):**
- [Claude Code: Legal and compliance](https://code.claude.com/docs/en/legal-and-compliance)
- [Claude Help: Agent SDK / claude -p / third-party usage](https://support.claude.com/en/articles/15036540)
- [Anthropic Consumer Terms (Effective Oct 8, 2025)](https://www.anthropic.com/legal/consumer-terms)
- [Remotion LICENSE.md](https://github.com/remotion-dev/remotion/blob/main/LICENSE.md)
- [motalim-ai/motion-starter-kit](https://github.com/motalim-ai/motion-starter-kit)

**من نتائج بحث / مصادر ثانوية (راجعها):**
[Remotion pricing](https://www.remotion.dev/docs/license/pricing) · [Remotion terms](https://www.remotion.dev/docs/terms) · [Remotion license FAQ](https://www.remotion.dev/docs/license/faq) · [The Register 6 Apr 2026](https://www.theregister.com/2026/04/06/anthropic_closes_door_on_subscription/) · [Engadget](https://www.engadget.com/ai/its-no-longer-free-to-use-claude-through-third-party-tools-like-openclaw-160912082.html) · [winbuzzer 19 Feb 2026](https://winbuzzer.com/2026/02/19/anthropic-bans-claude-subscription-oauth-in-third-party-apps-xcxwbn/) · [multica issue #2815](https://github.com/multica-ai/multica/issues/2815) · [Conductor](https://www.conductor.build/blog) · [Claudia/opcode](https://claudelog.com/addons/claudia) · [Microsoft Artifact Signing quickstart](https://learn.microsoft.com/en-us/azure/artifact-signing/quickstart) · [Windows code signing options](https://learn.microsoft.com/en-us/windows/apps/package-and-deploy/code-signing-options) · [Polar supported countries](https://polar.sh/docs/merchant-of-record/supported-countries) · [Paddle payouts](https://www.paddle.com/help/manage/get-paid/when-and-how-do-i-get-paid) · [Gumroad payouts](https://gumroad.com/help/article/13-getting-paid) · [MoR comparison](https://www.buildmvpfast.com/blog/lemon-squeezy-vs-polar-paddle-merchant-of-record-2026) · [Gemini CLI headless](https://www.geminicli.com/docs/cli/headless) · [OpenCode CLI](https://opencode.ai/docs/en/cli) · [HyperFrames](https://github.com/heygen-com/hyperframes) · [Keygen for Electron](https://keygen.sh/for-electron-apps/) · [Motionvid.ai](https://zoftwarehub.com/products/motionvid-ai/overview?click=tab)

**ما لم يُبحث/لم يتحقق (فجوات صريحة):** رسوم Cloudflare R2، Paymob، Captions/Descript/Higgsfield/Canva، تراخيص الخطوط والموسيقى والأصول المولّدة، قانونية «تعلّم الستايل من فيديو»، دعم Paddle/Lemon Squeezy لمصر، ترخيص Codex وOpenCode وGemini CLI، جودة كود Remotion لكل وكيل، فحص العلامات التجارية الرسمي.
