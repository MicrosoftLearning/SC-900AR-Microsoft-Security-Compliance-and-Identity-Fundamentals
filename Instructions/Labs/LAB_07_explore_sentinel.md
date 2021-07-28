---
lab:
    title: 'استكشاف Azure Sentinel'
    module: 'الوحدة 3، الدرس 3: وصف قدرات حلول الأمان في Microsoft: وصف قدرات الأمان في Azure Sentinel'
---


# النشاط المعملي: استكشاف Azure Sentinel 

## سيناريو النشاط المعملي
في هذا النشاط المعملي، ستتعرف على عملية إنشاء مثيل Azure Sentinel.  ستقوم أيضًا بإعداد الأذونات لضمان الوصول إلى الموارد التي سيتم توزيعها لدعم Azure Sentinel.  بمجرد الانتهاء من هذا الإعداد الأساسي، ستتعرف على خطوات توصيل Sentinel بمصادر البيانات خاصتك، باستخدام التحليلات المضمنة للحصول على إخطار بأي شيء مريب، وستستكشف أخيرًا إمكانية الأتمتة.  

  

**الزمن المقدر**: 30-45 دقائق

#### المهمة 1:  إنشاء مثيل Azure Sentinel.

1. افتح مستعرض Microsoft Edge. في شريط العناوين، أدخل **portal.azure.com.**

2. سجل الدخول باستخدام بيانات اعتماد المسؤول خاصتك.
    1. في نافذة تسجيل الدخول، أدخل **admin@WWLxZZZZZZ.onmicrosoft.com** (حيث ZZZZZZ هو معرف المستأجر الفريد الذي يوفره موفر استضافة النشاط المعملي خاصتك) ثم حدد **التالي**.
    
    1. أدخل كلمة مرور المسؤول التي يجب أن يوفرها موفر استضافة النشاط المعملي خاصتك. حدد **تسجيل الدخول**.
    1. عند مطالبتك بالبقاء مسجلاً للدخول، حدد **نعم**.

3. في الزاوية العلوية اليسرى من الشاشة، بجوار المكان الذي تظهر فيع عبارة Microsoft Azure، حدد إظهار أيقونة قائمة المدخل (يُشار إلى الخطوط الأفقية الثلاثة أيضًا باسم أيقونة الهامبرغر) ثم حدد **كل الخدمات**.  

4. في مربع خدمات التصفية، أدخل **Sentinel**، ثم حدد **Azure Sentinel** من القائمة.

5. من صفحة Azure Sentinel، حدد **إنشاء Azure Sentinel**.

6. من صفحة إضافة Azure Sentinel إلى مساحة عمل، حدد **إنشاء مساحة عمل جديدة**.

7. من علامة تبويب الأساسيات في مساحة عمل إنشاء تحليلات السجل، أدخل ما يلي:
    1. الاشتراك:  **Azure Pass – وصول محدود**
   
    1. مجموعة الموارد: حدد **إنشاء جديد** ثم أدخل الاسم **SC900-ResourceGroup** ثم حدد **موافق**.
    1. الاسم: **SC900-LogAnalytics-workspace**.
    1. المنطقة: **شرق الولايات المتحدة** (اترك الإعداد الافتراضي)
    1. حدد **التالي: مستوى التسعير >**

8. بالنسبة لمستوى التسعير، اترك الإعدادات الافتراضية: **الدفع حسب الاستخدام (لكل جيجابايت 2018)**، ثم حدد **التالي: العلامات >**.

9. بالنسبة للعلامات، يمكنك تركها فارغة، ثم حدد **مراجعة + إنشاء**.

10. تحقق من المعلومات التي أدخلتها ثم حدد **إنشاء**.

11. إذا كنت لا ترى مساحة العمل الجديدة مدرجة، فحدد **تحديث**، ثم حدد **إضافة**.

12. بمجرد إضافة مساحة العمل الجديدة، سيعمل Azure Sentinel | سيتم عرض صفحة الأخبار والأدلة.  لاحظ الخطوات الثلاث المدرجة في صفحة بدء الاستخدام.

13. اترك هذه الصفحة مفتوحة، لأننا ستستخدمها في المهمة التالية.

#### المهمة 2:  مع إنشاء مثيل Azure Sentinel، ستحتاج إلى التأكد من حصولك على حق الوصول الضروري إلى الموارد التي يتم توزيعها لدعم Azure Sentinel.  في هذه المهمة، ستنتقل إلى صفحة التحكم في الوصول (IAM) بالنسبة لمجموعة الموارد التي أنشأتها باستخدام مثيل Azure Sentinel وعرض الأدوار المتاحة وإسناد الدور المطلوب (مسؤول MOD) إليك. سيضمن تعيين الدور على مستوى مجموعة الموارد تطبيق الدور على جميع الموارد التي تم نشرها لدعم Azure Sentinel.

1. من صفحة Azure Sentinel، في الزاوية العلوية اليسرى من الصفحة، أعلى المكان الذي تظهر فيه عبارة Azure Sentinel، حدد **كل الخدمات**.

2. في مربع خدمات التصفية، أدخل مجموعات الموارد، ثم حدد **مجموعات الموارد** من القائمة المتاحة.

3. من صفحة مجموعات الموارد، حدد مجموعة الموارد التي أنشأتها باستخدام Azure Sentinel، **SC900-ResourceGroup**.

4. من صفحة SC900-ResourceGroup، حدد **التحكم في الوصول (IAM)** من جزء التنقّل الأيسر.

5. من صفحة التحكم في الوصول، حدد **عرض الوصول الخاص بي**.  لاحظ أن الدور الحالي هو مسؤول الأمان.  أغلق نافذة تعيينات مسؤول MOD عن طريق تحديد **X** في الزاوية العلوية اليمنى من النافذة.

6. من صفحة التحكم في الوصول، حدد **+ إضافة**، ثم حدد **إضافة تعيين دور**.

7. تفتح نافذة إضافة تعيين دور.  حدد سهم القائمة المنسدلة في حقل تحديد دور لعرض الأدوار المتاحة.  بالنسبة لهذا النشاط المعملي، حدد **المالك**.  ملاحظة:  كأفضل ممارسة، ينبغي لك تعيين الامتياز الأقل طلبًا بالنسبة للوظيفة.  كمرجع، راجع الأذونات في Azure Sentinel.  https://docs.microsoft.com/ar-sa/azure/sentinel/roles

8. من قائمة المستخدمين المعروضة، حدد **مسؤول MOD**.

9. حدد **حفظ** في أسفل الصفحة.

10. من صفحة التحكم في الوصول، حدد **عرض الوصول الخاص بي** لتأكيد الدور المضاف، ثم أغلق النافذة عن طريق تحديد **X** في الزاوية العلوية اليمنى من النافذة.

11. ارجع إلى صفحة جميع الخدمات في Azure، بتحديد **كل الخدمات** من الزاوية العلوية اليسرى من الصفحة، في الأعلى حيث تظهر مجموعات الموارد.

#### المهمة 3:  في هذه المهمة، ستتعرف على عملية توصيل Azure Sentinel بمصدر بياناتك لتبدأ في جمع البيانات. ملاحظة: قد يستغرق الأمر بعض الوقت لعرض حالة الاتصال للموصل (نحو 30 دقيقة، حسب المستأجر).

1. في مربع تصفية الخدمات في صفحة كل الخدمات، أدخل **Azure Sentinel**، ثم حدد **Azure Sentinel** من قائمة النتائج. 

2. من صفحة Azure Sentinel، حدد مساحة العمل التي أنشأتها باستخدام مثيل Azure Sentinel، **SC900-LogAnalytics-workspace**.

3. تتمثل الخطوة الأولى مع Azure Sentinel في القدرة على جمع البيانات. من جزء التنقّل الأيسر، حدد **موصلات البيانات** المدرجة ضمن التكوين.

4. من صفحة موصلات البيانات، مرر لأسفل على النافذة الرئيسية لعرض قائمة شاملة بالموصلات المتاحة. في مربع البحث بصفحة موصلات البيانات، أدخل **Azure** ثم حدد **Azure Active Directory** من القائمة.

5. تفتح نافذة موصل Azure Active Directory.  حدد **فتح صفحة الموصل**.

6. من صفحة موصل Azure Active Directory، راجع الوصف ولاحظ المحتوى ذي الصلة الذي يتضمن المصنفات والاستعلامات وقوالب القواعد التحليلية.  

7. توفر علامة تبويب الإرشادات في النافذة الرئيسية مزايا Azure Sentinel للتكامل مع Azure Active Directory.   ضمن التكوين، حدد **سجلات تسجيل الدخول** ثم حدد تطبيق التغييرات (يمكن اختيار موصلات متعددة).

8. من علامة تبويب الخطوات التالية، لاحظ قائمة المصنفات الموصى بها.   ضمن المصنفات الموصى بها، حدد **سجلات تسجيل الدخول إلى Azure** (يمكن اختيار مصنفات إضافية).

9. من صفحة المصنفات ومع تحديد علامة تبويب القوالب (وضع تحتها خط)، حدد **سجلات تسجيل الدخول إلى Azure**. 

10. من نافذة سجلات تسجيل الدخول إلى Azure AD التي تفتح أمامك، راجع الوصف وحدد **عرض القالب**.  أغلق القالب، عن طريق تحديد **X** في الزاوية العلوية اليمنى من الشاشة.  حدد **حفظ** من أسفل الصفحة، ثم حدد **موافق** لحفظ المصنف في الموقع الافتراضي.

11. من الزاوية العلوية اليسرى من صفحة المصنفات، في الأعلى حيث تظهر عبارة المصنفات، حدد **Azure Sentinel**. حيث يُعيدك هذا إلى صفحة موصلات بيانات Azure Sentinel.

12. ينبغي أن يعرض الجزء العلوي من صفحة موصلات البيانات 1 متصل، ليعكس أنك متصل الآن بـ Azure Active Directory.

13. من جزء التنقّل الأيسر، حدد **المصنفات**.

14. من صفحة المصنفات، حدد علامة تبويب **مصنفاتي** الموجودة أعلى مربع البحث.  يتم سرد المصنف الذي حفظته للتو ويُتاح لك لعرض بياناتك ومراقبتها.

15. اترك هذه الصفحة مفتوحة، لأننا ستستخدمها في المهمة التالية.

#### المهمة 4:  في هذه المهمة، ستتعرف على عملية استخدام قالب قاعدة تحليلات مضمّن لإنشاء قاعدة ليتم إخطارك عند حدوث شيء مريب.

1. من جزء التنقّل الأيسر، حدد **التحليلات**.

2. ستعرض صفحة التحليلات القواعد النشطة (يتم تمكين الكشف المتقدم عن هجوم متعدد المراحل افتراضيًا) كما توفر الوصول إلى قوالب القواعد.  حدد علامة تبويب **قوالب القواعد**.  لاحظ قائمة القوالب المتاحة ومختلف الطرق لتصفية القائمة.  باستخدام تنبيهات التحليلات المضمنة في مساحة عمل Azure Sentinel، سيتم إخطارك عند حدوث أي شيء مريب.

3. في شريط البحث، أدخل **مدخل Azure**.  حدد **محاولات تسجيل الدخول الفاشلة إلى مدخل Azure**.  

4. من النافذة التي تفتح أمامك، اقرأ الوصف وراجع المعلومات المرتبطة بالقالب.  حدد **إنشاء قاعدة** في أسفل الصفحة.

5. من معالج قاعدة Analytics، راجع المعلومات، ثم حدد **التالي: تعيين منطق القاعدة >**.

6. صفحة تعيين منطق القاعدة، هي المكان الذي تحدد فيه منطق قاعدة التحليلات الجديدة. يوفر النموذج بالفعل بعض الإعدادات المنطقية والمحددة مسبقًا.  مرر خلال الصفحة لمشاهدة الإعدادات المتاحة.  اترك الإعدادات الافتراضية. حدد **التالي: إعدادات الحادث (معاينة) >**.

7. باستخدام إعدادات الحادث، يمكن تجميع تنبيهات Azure Sentinel معًا في حادث ينبغي النظر فيه. يمكنك تعيين ما إذا كانت التنبيهات التي يتم تشغيلها من قِبل قاعدة التحليلات هذه ينبغي أن تؤدي إلى حوادث أم لا.  اترك الإعدادات الافتراضية وحدد **التالي: الرد المؤتمت >**.

8. في علامة تبويب "الرد المؤتمت"، لاحظ كيف يمكنك إضافة دليل مبادئ لأتمتة الرد.  وبالمثل، يمكنك إنشاء قاعدة أتمتة الحوادث.  حدد **+ إضافة** جديد ضمن أتمتة الحوادث.  تفتح نافذة لإنشاء قاعدة أتمتة جديدة.  يتم تشغيل أي قاعدة أتمتة تُنشئها في هذه الصفحة من خلال قاعدة التحليلات. لاحظ أنه يمكنك إضافة شروط وتعيين إجراءات للقاعدة.   حدد **إلغاء** للخروج من النافذة.

9. حدد **التالي: مراجعة>** لمراجعة جميع التفاصيل المرتبطة بالقاعدة والاستناد إلى النموذج المختار. في هذه المرحلة، يمكنك اختيار إنشاء القاعدة، عن طريق تحديد **إنشاء** أو الخروج دون إنشاء القاعدة عن طريق تحديد **X** في الزاوية العلوية اليمنى من الصفحة.

10. اترك هذه الصفحة مفتوحة، لأننا ستستخدمها في المهمة التالية.

#### المهمة 5:  في المهمة السابقة، أنشأتَ قاعدة تحليلات ليتم تنبيهك بالأنشطة المشبوهة.  يتضمن هذا المعالج خيار لأتمتة الاستجابة لحادث بناءً على القاعدة المحددة.  ولكن يمكنك أيضًا إنشاء قواعد الأتمتة عن طريق الانتقال مباشرةً إلى خيار تكوين الأتمتة.

1. من جزء التنقّل الأيسر، حدد **الأتمتة**.  

2. حدد **+ إنشاء**. من القائمة المنسدلة، لاحظ كيف يمكنك تحديد إما إضافة دليل مبادئ جديد أو إضافة قاعدة جديدة.  حدد **إضافة قاعدة جديدة**.  

3. تفتح نافذة لإنشاء قاعدة أتمتة جديدة.  لاحظ أنه يمكنك إضافة شروط وتعيين إجراءات للقاعدة.  يتمثل الاختلاف الوحيد في أن الشرط الأول هو إقران قاعدة (قواعد) التحليلات التي تريد تطبيق قاعدة الأتمتة هذه عليها.  تم تعطيل هذا في المهمة السابقة لأنه تم تكوين الأتمتة للقاعدة المحددة.  حدد **إلغاء** للخروج من نافذة إنشاء قاعدة أتمتة جديدة.

4. اترك هذه الصفحة مفتوحة، لأننا ستستخدمها في المهمة التالية.


#### المهمة 6:  حذف مجموعة موارد Azure Sentinel.  تتم محاسبة Azure Sentinel استنادًا إلى حجم البيانات التي يتم استيعابها للتحليل في Azure Sentinel. فرغم أن كمية البيانات التي يتم استيعابها نتيجة لهذا التمرين المعملي ضئيلة، فمن المستحسن حذف مجموعة موارد Azure Sentinel عند الانتهاء من استكشاف ميزات قدرات Azure Sentinel.

1. من صفحة Azure Sentinel، في الزاوية العلوية اليسرى من الصفحة، أعلى المكان الذي تظهر فيه عبارة Azure Sentinel، حدد **كل الخدمات**.

2. في مربع خدمات التصفية، أدخل مجموعات الموارد، ثم حدد **مجموعات الموارد** من القائمة المتاحة.

3. من صفحة مجموعات الموارد، حدد مجموعة الموارد التي أنشأتها باستخدام Azure Sentinel، **SC900-ResourceGroup**.

4. من أعلى منتصف الصفحة، حدد **حذف مجموعة الموارد**.  راجع التحذير.  أدخل اسم مجموعة الموارد، **SC900-ResourceGroup**، ثم حدد **حذف** من أسفل الصفحة.  سيستغرق حذف مجموعة الموارد عدة دقائق.

5. بمجرد التحقق من حذف مجموعة الموارد، أغلق صفحة المستعرض. 


#### المراجعة

في هذا النشاط المعملي، تعرفت على عملية إنشاء مثيل Azure Sentinel.  وأعددت أيضًا الأذونات لضمان الوصول إلى الموارد المرتبطة بمثيل Azure Sentinel خاصتك.  باستخدام مثيل Azure Sentinel الذي تم إنشاؤه، تعرفتَ على خطوات توصيل Sentinel بمصادر البيانات وكيفية استخدام قواعد التحليلات المضمنة للحصول على إخطار بأي شيء مريب، وأخيرًا استكشفتَ إمكانية الأتمتة. لقد أنهيت النشاط المعملي بحذف مجموعة الموارد المرتبطة بمثيل Azure Sentinel الذي أنشأته.