<div id="readme" class="Box-body readme blob js-code-block-container p-5 p-xl-6 gist-border-0" dir="rtl">
    <article class="markdown-body entry-content container-lg" itemprop="text"><table>
  <thead>
  <tr>
  <th>Demo</th>
  </tr>
  </thead>
  <tbody>
  <tr>
  <td><div><table>
  <thead>
  <tr>
  <th>title</th>
  <th>module</th>
  </tr>
  </thead>
  <tbody>
  <tr>
  <td><div>مجموعات أمان الشبكة (NSGs) في Azure</div></td>
  <td><div>الوحدة 3، الدرس 1: وصف قدرات حلول الأمان في Microsoft: وصف قدرات الأمان الأساسية في Azure.</div></td>
  </tr>
  </tbody>
</table>
</div></td>
  </tr>
  </tbody>
</table>

# العرض التوضيحي: مجموعات أمان الشبكة (NSGs) في Azure

### سيناريو العرض التوضيحي
في هذا العرض التوضيحي، ستعرض وظائف مجموعة أمان الشبكة (NSG) في Azure.  ستفعل ذلك عن طريق إنشاء جهاز ظاهري (VM) أولاً بدون أي مجموعة من مجموعات أمان الشبكة، كجزء من الإعداد المسبق للعرض التوضيحي. ستُنشئ أيضًا مجموعة أمان الشبكة بدون أي واجهة أو شبكة فرعية مرتبطة.  كجزء من العرض التوضيحي، ستعرض القواعد الافتراضية الواردة والصادرة لمجموعة أمان الشبكة. ستنتقل بعد ذلك إلى عملية تعيين واجهة الجهاز الظاهري لمجموعة أمان الشبكة.  بمجرد التكوين، ستختبر الاتصال بالجهاز الظاهري، باستخدام قواعد مجموعة أمان الشبكة الافتراضية بالإضافة إلى القواعد التي ستنشئها.
  

#### الجزء 1 من الإعداد المسبق للعرض التوضيحي
 يوصى المعلمون بإجراء ذلك **قبل** وقت الفصل الدراسي حيث يمكن أن يستغرق إنشاء جهاز ظاهري عدة دقائق. في هذا الإعداد، سننشئ جهازًا ظاهريًا يعمل بنظام Windows 10.

1. افتح علامة تبويب **الصفحة الرئيسية - Microsoft Azure** في المستعرض.  إذا كنتَ قد أغلقتَ علامة التبويب مسبقًا، فافتح صفحة في المستعرض وفي شريط العناوين، أدخل portal.azure.com وسجِّل الدخول مرة أخرى.

1. في مربع البحث، في الشريط الأزرق أعلى الصفحة بجوار المكان الذي تظهر فيه كلمة Microsoft Azure، أدخِل **الأجهزة الظاهرية**، ثم حدد **الأجهزة الظاهرية** من نتائج البحث.  

1. من أعلى يسار الصفحة، حدد **+ إضافة** ثم حدد **+ جهاز ظاهري**.

1. من علامة تبويب الأساسيات، املأ المعلومات التالية (لأي شيء غير مدرج، اترك الإعدادات الافتراضية):
    1. **الاشتراك**: تحقق من الإعداد الافتراضي ليكون Azure Pass - وصول محدود.
    1. **مجموعة الموارد**: حدد **إنشاء جديد** ثم في حقل الاسم، أدخل **LabsSC900-RG**، ثم حدد **موافق**.
    1. **اسم الأجهزة الظاهرية**:  أدخِل **SC900-WinVM**.
    1. **المنطقة**:  اترك الإعداد الافتراضي.
    1. **خيارات التوفر**: تأكد من تحديد **لا حاجة لتكرار البنية الأساسية**.  ملاحظة: من الأهمية بمكان تعيين خيارات التوفر على لا حاجة لتكرار البنية الأساسية، وإلا فلن يعمل العرض التوضيحي على النحو المنشود.  يتطلب وجود خيار التوفر إتاحة مجموعة أمان الشبكة ومن ثم نُنشئ الجهاز الظاهري عمدًا بدون مجموعة أمان الشبكة.
    1. **الصورة**:  من القائمة المنسدلة، حدد **Windows 10 Pro، الإصدار 20H2 - الجيل 1**.
    1. **الحجم**:  حدد **عرض جميع الأحجام** من القائمة المنسدلة وحدد **B2s**، ثم اضغط على **تحديد** في أسفل الصفحة.
    1. **اسم المستخدم**:  أدخِل **AzureUser**.
    1. **كلمة المرور**:  أدخِل **SC900AzureLabs**.
    1. **منافذ الوارد العامة**:  يمكنك ترك الإعدادات الافتراضية (لا يهم ما تحدده هنا لأن إعدادات الشبكة ستتجاوز ما تفعله هنا).
    1. **الترخيص**:  حدد **أؤكد أن لدي ترخيص Windows 10 مؤهلًا مع حقوق استضافة متعددة المستأجرين**، بحيث تظهر علامة الاختيار في المربع.
    1. حدد **التالي: الأقراص**.

1. أنت الآن في علامة تبويب الأقراص لتكوين الجهاز الظاهري.  اترك جميع الإعدادات على الوضع الافتراضي وحدد **التالي: الشبكات**.

1. أنت الآن في علامة تبويب الشبكات لتكوين الجهاز الظاهري.  املأ المعلومات التالية (لأي شيء غير مدرج، اترك الإعدادات الافتراضية):
    1. مجموعة أمان شبكة NIC:  حدد **لا شيء**.  ملاحظة: باختيار "لا شيء" فإنك تضمن أن NIC ليس لديها مجموعة أمان الشبكة.  في خطوة لاحقة في العرض التوضيحي، ستنشئ مجموعة أمان الشبكة وتُعيّن الجهاز الظاهري NIC إلى مجموعة أمان الشبكة التي تُنشئها.
    1. نظرًا لأنه سيتم الاحتفاظ بالإعدادات الأخرى الخاصة بالجهاز الظاهري كإعدادات افتراضية، فامضِ قدمًا وحدد التالي: **مراجعة + إنشاء**.

1. راجع التكوين للجهاز الظاهري خاصتك.  بعض النقاط التي يجب ملاحظتها: يحتوي الجهاز الظاهري هذا على عنوان IP عام ولا يحتوي على مجموعة أمان شبكة NIC.  من منظور الأمان، فإن هذا يترك الجهاز الظاهري مكشوفًا.  سنعالج هذا في مهمة لاحقة. حدد **إنشاء**.  قد يستغرق اكتمال نشر الجهاز الظاهري عدة دقائق.

1. لاحظ اسم واجهة الشبكة، **sc900-winvmXXX** (سيكون XXX خاصًا بواجهة الشبكة للجهاز الظاهري خاصتك).

1. بمجرد اكتمال توزيع الجهاز الظاهري، حدد **انتقال إلى المورد**.  أنت الآن في صفحة SC900-WinVM.  لاحظ عنوان IP العام.

1. من لوحة التنقل اليسرى، حدد **الشبكة** ولاحظ واجهة الشبكة **sc900-winvmXXX** (سيكون XXX خاصًا بواجهة الشبكة للجهاز الظاهري خاصتك).  ينبغي ألا تكون هناك قواعد واردة أو صادرة مرتبطة بالواجهة.  

1. من أعلى الصفحة، حدد **اتصال** لأنه من المهم التحقق من قدرتك على الاتصال بالجهاز الظاهري.
    1. من أعلى الصفحة، تأكد من تحديد **بروتوكول سطح المكتب البعيد** (تحته خط).
    1. تحقق من تعيين عنوان IP على عنوان IP العام، واترك رقم المنفذ على الإعداد الافتراضي وحدد **تنزيل ملف بروتوكول سطح المكتب البعيد**.
    1. **افتح** الملف الذي تم تنزيله وفي النافذة التي تظهر، حدد **اتصال**.
    1. تفتح نافذة تطلب منك ببيانات الاعتماد خاصتك. إذا طلبت النافذة الافتراضية رقم تعريف شخصي، فحدد **المزيد من الخيارات**، ثم حدد **استخدام حساب مختلف**.   سيُطلب منك بيانات الاعتماد خاصتك.  بالنسبة لاسم المستخدم، أدخل **AzureUser**.  بالنسبة لكلمة المرور، أدخل **SC900AzureLabs**.
    1. تفتح نافذة اتصال سطح المكتب البعيد تشير إلى أنه لا يمكن التحقق من هوية الكمبيوتر البعيد.  هل ترغب في الاتصال على أي حال؟  حدد **نعم**.
    1. أنت الآن متصل بجهاز Windows الظاهري الذي أنشأته للتو. أكمل إعداد Windows. رغم أنك متصل بالجهاز الظاهري عبر بروتوكول سطح المكتب البعيد ومنفذ بروتوكول سطح المكتب البعيد شائع الاستخدام، فإن جميع المنافذ مفتوحة في هذا الجهاز الظاهري ولا يوجد شيء يقوم بتصفية حركة المرور.  أغلق اتصال سطح المكتب البعيد، عن طريق تحديد **X** في أعلى منتصف الصفحة حيث يظهر عنوان IP.  تشير النوافذ المنبثقة إلى أنه سيتم فصل جلسة عملك البعيدة. حدد **موافق**.

1. لقد عُدتَ الآن إلى صفحة SC900-WinVM في مدخل Azure.  اترك علامة تبويب المستعرض مفتوحة للمهمة التالية.

#### الجزء 2 من الإعداد المسبق للعرض التوضيحي
أنشئ مجموعة أمان شبكة، ولكن تجنب تعيين واجهة شبكة الجهاز الظاهري لمجموعة أمان الشبكة تلك.  

1. افتح علامة تبويب SC900-WinVM – Microsoft Azure في المستعرض.

1. في مربع البحث، في الشريط الأزرق أعلى الصفحة بجوار المكان الذي تظهر فيه كلمة Microsoft Azure، أدخِل **مجموعة أمان الشبكة**، ثم حدد **مجموعات أمان الشبكة** من نتائج البحث.  لا تحدد مجموعات أمان الشبكة الكلاسيكية.

1. من أعلى صفحة مجموعات أمان الشبكة، حدد **+ إنشاء**.

1. في علامة تبويب الأساسيات في صفحة إنشاء مجموعة أمان الشبكة، حدد الإعدادات التالية:
    1. الاشتراك:  Azure Pass – وصول محدود
    1. مجموعة الموارد:  **LabsSC900-RG**
    1. الاسم:  **NSG-SC900**
    1. المنطقة:  اترك الإعداد الافتراضي **(الولايات المتحدة) شرق الولايات المتحدة**
    1. حدد **مراجعة + إنشاء**، ثم حدد **إنشاء**.

1. بمجرد اكتمال التوزيع، حدد **انتقال إلى المورد** وتأكد من صحة كل شيء.  ينبغي أن يكون هناك 3 قواعد افتراضية واردة و3 قواعد افتراضية صادرة مع عدم وجود شبكات فرعية وواجهات مرتبطة بمجموعة أمان الشبكة.  ارجع إلى **الصفحة الرئيسية** لمدخل Azure.  

#### العرض التوضيحي
استكشف إعدادات مجموعة أمان الشبكة.  في هذه الحالة، ستُجري معاينة لمجموعة أمان شبكة موجودة (تلك التي أنشأتها في الإعداد أعلاه) التي لم يتم تعيينها بعد لواجهة الجهاز الظاهري. ستعرض بعد ذلك عملية ربط الواجهة بمجموعة أمان الشبكة وعملية إنشاء قواعد واردة وصادرة.

1. افتح علامة تبويب **الصفحة الرئيسية - Microsoft Azure** في المستعرض.  إذا كنتَ قد أغلقتَ علامة التبويب مسبقًا، فافتح صفحة في المستعرض وفي شريط العناوين، أدخل portal.azure.com وسجِّل الدخول مرة أخرى.

1. في مربع البحث، في الشريط الأزرق أعلى الصفحة بجوار المكان الذي تظهر فيه كلمة Microsoft Azure، أدخِل **مجموعة أمان الشبكة**، ثم حدد **مجموعات أمان الشبكة** من نتائج البحث.  لا تحدد مجموعات أمان الشبكة الكلاسيكية.

1. من صفحة مجموعة أمان الشبكة، حدد مجموعة أمان الشبكة التي أنشأتها في الإعداد، **NSG-SC900**.

1. يتم تمييز علامة تبويب **نظرة عامة** في جزء التنقّل الأيسر.  لاحظ القواعد الافتراضية الواردة والصادرة في مجموعة أمان الشبكة. فرغم إنشاء مجموعة أمان الشبكة وهناك قواعد افتراضية لتصفية نسبة استخدام الشبكة، لم يتم ربط أي واجهة بمجموعة أمان الشبكة. يمكنك رؤية ذلك في الجزء العلوي الأيسر من الصفحة حيث تظهر عبارة "مقترن بـ: 0 شبكات فرعية، 0 واجهات شبكة".  لكي تؤدي مجموعة أمان الشبكة عملها، يجب تعيينها لشيءٍ ما.  في حالتنا، سنعيِّن واجهة الشبكة للجهاز الافتراضي الذي تم إنشاؤه مسبقًا.

1. من جزء التنقّل الأيسر في صفحة NSG-SC900، ضمن الإعدادات، حدد **واجهات الشبكة**.

1. حدد **+ إقران**، أعلى مربع البحث، ثم من القائمة المنسدلة، حدد **sc900-winvmXXX** (سيكون XXX خاصًا بواجهة الشبكة للجهاز الظاهري خاصتك) ثم حدد **موافق**. أثناء اقتران الواجهة، سترى مربع إخطار في الزاوية العلوية اليمنى من الشاشة. بمجرد ربط الواجهة بمجموعة أمان الشبكة، ستظهر في القائمة.

1. ارجع إلى علامة تبويب **نظرة عامة**.  لاحظ أنه في الجزء العلوي الأيسر من الصفحة سترى "مقترن بـ: 0 شبكات فرعية، 1 واجهة شبكة" - تم الآن تعيين الواجهة لمجموعة أمان الشبكة. بالإضافة إلى ذلك، مَيّز القواعد الافتراضية للمتعلمين. بالنسبة للوارد، لن يُسمح إلا بنسبة استخدام الشبكة من شبكات Azure الظاهرية الأخرى وموازن تحميل Azure. سيتم رفض نسبة استخدام الشبكة الواردة الأخرى إلى الجهاز الظاهري بالكامل. التزم أيضًا بالقواعد الصادرة الافتراضية.  يُسمح فقط بنسبة استخدام الشبكة الصادرة إلى شبكات VNets الأخرى ونسبة استخدام شبكة الإنترنت الصادرة.  كجزء من العرض التوضيحي، يُوصى بقضاء دقيقة واحدة لاستعراض رفض حركة المرور الواردة.
    1. في شريط البحث، في الجزء العلوي من الصفحة، أدخل **الأجهزة الظاهرية** وحددها.
    1. من صفحة الأجهزة الظاهرية، حدد **SC900-WinVM**.
    1. من أعلى صفحة SC900-WinVM، حدد **اتصال** ثم حدد **بروتوكول سطح المكتب البعيد**.
    1. تحقق من تعيين عنوان IP على عنوان IP العام، واترك رقم المنفذ على الإعداد الافتراضي وحدد **تنزيل ملف بروتوكول سطح المكتب البعيد**.
    1. **افتح** الملف الذي تم تنزيله وحدد **اتصال**.
    1. بعد بضع ثوانٍ من محاولة الاتصال، سترى رسالة الفشل، تشير إلى أن سطح المكتب البعيد لا يمكنه الاتصال بالكمبيوتر البعيد. حدد **موافق**.

1. الآن بعد أن عرضتَ تأثير القواعد الواردة الافتراضية لمجموعة أمان الشبكة، ستحتاج إلى إنشاء قاعدة جديدة للسماح بنسبة استخدام الشبكة الواردة لبروتوكول سطح المكتب البعيد.  تذكر أنه لا يمكنك حذف القواعد الافتراضية الحالية، ولكن يمكنك فقط إنشاء قواعد جديدة ذات أولوية أعلى.
    1. من جزء التنقّل الأيسر، ضمن الإعدادات، حدد **الشبكة**.  أنت في صفحة الشبكات الخاصة بالجهاز الافتراضي ورغم أنه يمكنك إنشاء قاعدة واردة وقاعدة صادرة من هنا، ارجع إلى صفحة مجموعة أمان الشبكة، بعد استعراض هذا العرض التوضيحي بشأن مجموعة أمان الشبكة.  **حدد NSG-SC900**، إنه الارتباط الموجود في منتصف النافذة.

1. أنت الآن في صفحة نظرة عامة على مجموعة أمان الشبكة.  لاحظ المعلومات المتعلقة بمجموعة أمان الشبكة. من لوحة التنقل اليسرى لصفحة مجموعة أمان الشبكة، ضمن الإعدادات، حدد **قواعد الأمان الواردة**، ثم حدد **+ إضافة** من أعلى الصفحة. في صفحة إضافة قاعدة الأمان الواردة، تحدث إلى الإعدادات المختلفة. يوصى بإنشاء القاعدة بالفعل للسماح بنسبة استخدام الشبكة الواردة لبروتوكول سطح المكتب البعيد، بالإعدادات التالية:
    1. المصدر: **أي**
    1. نطاقات منفذ المصدر: **\***
    1. الوجهة: **أي**
    1. الخدمة: **RDP**
    1. الإجراء: **السماح**
    1. الأولوية: **300**؛ ملاحظة: القواعد ذات الأرقام الأقل لها أولوية أعلى وتتم معالجتها أولاً. لذا يجب أن تكون أولوية هذه القاعدة الجديدة أعلى من أولوية القاعدة الحالية التي ترفض جميع نسب استخدام الشبكة الواردة.
    1. الاسم: **AllowRDP**
    1. حدد **إضافة**
    1. بمجرد توفير القاعدة، ستظهر في قائمة قواعد الوارد.

1. الآن تحقق من **قواعد الأمان الصادرة**.  حدد **+ إضافة** من أعلى الصفحة وتحدث إلى الإعدادات المختلفة.  أُوصي بإنشاء القاعدة - تُنشئ الإعدادات الموضحة أدناه قاعدة لرفض نسبة استخدام شبكة الإنترنت الصادرة:
    1. المصدر: **أي**
    1. نطاقات منفذ المصدر: **\***
    1. الوجهة: **علامة الخدمة**
    1. علامة خدمة الوجهة: **الإنترنت**
    1. الخدمة: **مخصص** (اترك الإعداد الافتراضي)
    1. نطاقات منفذ الوجهة: **\*** (تأكد من وضع علامة النجمة في حقل نطاقات منفذ الوجهة).
    1. البروتوكول: **أي**
    1. الإجراء: **الرفض**
    1. الأولوية: **4000** (النقطة التي يجب ذكرها هي أن الأولوية يجب أن تكون أعلى من الأولوية الخاصة بالقاعدة الحالية التي تسمح بنسبة استخدام شبكة الإنترنت الصادرة)
    1. الاسم: **DenyInternet**
    1. حدد **إضافة**
    1. بمجرد توفير القاعدة، ستظهر في قائمة قواعد الوارد.

1. عُد الآن إلى الجهاز الافتراضي واختبر القواعد.  من أعلى الصفحة، حدد **SC900-VM**، أعلاه حيث يشير إلى قواعد الأمان الصادرة.

1. اختبر القاعدة الواردة عن طريق التحقق من أنه يمكنك الاتصال بالجهاز الظاهري باستخدام بروتوكول سطح المكتب البعيد.
    1. حدد **اتصال** من لوحة التنقل اليسرى.
    1. تحقق من تعيين عنوان IP على عنوان IP العام، واترك رقم المنفذ على الإعداد الافتراضي وحدد **تنزيل ملف بروتوكول سطح المكتب البعيد**.
    1. **افتح** الملف الذي تم تنزيله وحدد **اتصال**.
    1. سيُطلب منك بيانات الاعتماد خاصتك. بالنسبة لاسم المستخدم، أدخل **AzureUser**. بالنسبة لكلمة المرور، أدخل **SC900AzureLabs**.  إذا كانت النافذة التي تطالب ببيانات الاعتماد خاصتك تطلب رقم تعريف شخصي، فحدد **المزيد من الخيارات**، ثم حدد **استخدام حساب مختلف**.
    1. تفتح نافذة اتصال سطح المكتب البعيد تشير إلى أنه لا يمكن التحقق من هوية الكمبيوتر البعيد. هل ترغب في الاتصال على أي حال؟ حدد **نعم**.
    1. أنت الآن متصل بالجهاز الافتراضي، وضّح للمتعلم أنه في هذه الحالة كان بإمكانك الاتصال بالجهاز الافتراضي لأن قاعدة نسبة استخدام الشبكة الواردة التي أنشأتها تسمح بنسبة استخدام الشبكة الواردة إلى الجهاز الظاهري عبر بروتوكول سطح المكتب البعيد.

1. اختبر الآن قاعدة مجموعة أمان الشبكة الصادرة
    1. افتح مستعرض Edge في الجهاز الظاهري.
    1. أدخِل **https://www.bing.com**. لا ينبغي عرض الصفحة. ملاحظة: إذا كنتَ قادرًا على الاتصال بالإنترنت وتحققتَ من تعيين جميع معلمات القاعدة الصادرة بشكلٍ صحيح، فمن المحتمل أن يستغرق الأمر بضع دقائق حتى تصبح القاعدة سارية المفعول. انتظر بضع دقائق وحاول مرة أخرى.

1. أغلق اتصال سطح المكتب البعيد، عن طريق تحديد **X** في أعلى منتصف الصفحة حيث يظهر عنوان IP. تشير النوافذ المنبثقة إلى أنه سيتم فصل جلسة عملك البعيدة. حدد **موافق**.

1. ارجع إلى الصفحة الرئيسية لمدخل Azure، عن طريق تحديد **Microsoft Azure** على الشريط الأزرق أعلى الصفحة.

#### إنهاء
**هام**: في هذه المهمة ستحذف مجموعة الموارد وجميع الموارد التي تحتوي عليها.   هذه خطوة مهمة لتجنب الرسوم الإضافية.

1. افتح علامة تبويب SC900-WinVM – Microsoft Azure في المستعرض.

1. من الزاوية العلوية اليسرى من الصفحة، حدد **كل الخدمات**.

1. في مربع تصفية الخدمات بجوار مكان وجود عبارة جميع الخدمات، أدخل **مجموعات الموارد** ثم من النتائج، حدد **مجموعات الموارد**.

1. حدد **LabsSC900-RG**.

1. من أعلى منتصف صفحة LabsSC900-RG، حدد **حذف مجموعة الموارد**.

1. في النافذة التي تفتح، أدخل اسم مجموعة الموارد، **LabsSC900-RG**، لتأكيد حذف مجموعة الموارد وجميع مواردها، ثم حدد **حذف** من أسفل الصفحة.

1. قد يستغرق حذف جميع الموارد ومجموعة الموارد بضع دقائق.

#### المراجعة

في هذا العرض التوضيحي، استعرضتَ المعلومات والإعدادات المرتبطة بمجموعة أمان الشبكة، بما في ذلك عملية ربط واجهة بمجموعة أمان الشبكة، واستعرضتَ القواعد الافتراضية الواردة والصادرة وأخيرًا خطوات إنشاء قاعدة جديدة.
