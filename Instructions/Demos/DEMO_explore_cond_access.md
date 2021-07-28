---
Demo:
    title: 'الوصول المشروط في Azure Active Directory'
    module: 'الوحدة 2، الدرس 3: وصف قدرات حلول إدارة الوصول والهوية في Microsoft: استكشاف قدرات إدارة الوصول في Azure AD'
---


# العرض التوضيحي: الوصول المشروط في Azure Active Directory

### سيناريو العرض التوضيحي
في هذا العرض التوضيحي، ستتعرف على الخيارات المختلفة المتاحة لنهج الوصول المشروط.

1. انتقل إلى علامة تبويب **Contoso - Microsoft Azure** المفتوحة في المستعرض. إذا كنتَ قد أغلقتَ علامة التبويب مسبقًا، فافتح صفحة في المستعرض وفي شريط العناوين، أدخل portal.azure.com وحدد Azure Active Directory. يجب أن تكون قد سجلت دخولك كمسؤول، في مدخل Azure، إذا لم تكن قد فعلت، قم بتسجيل الدخول مرة أخرى.

1. من لوحة التنقل اليسرى، حدد **الأمان**.

1. من لوحة التنقل اليسرى، حدد **الوصول المشروط**.

1. يتم عرض شاشة نهُج الوصول المشروط. يتم سرد أي نهُج وصول مشروط موجودة هنا. لإظهار الإعدادات المرتبطة بالوصول المشروط، حدد **+ نهج جديد**.

1. في حقل **الاسم**، يمكنك ببساطة إدخال اسم للنهج.

1. لاحظ أن لديك عدة خيارات ضمن **التعيينات**.  نظرًا لأن نهُج الوصول المشروط تشبه عبارات إذا/حينئذ، فإن إعدادات التعيينات تشبه عبارات "إذا".
    1. **المستخدمون والمجموعة** -  حرك مؤشر الماوس فوق أيقونة المعلومات بجوار المكان الذي تظهر فيه عبارة "المستخدمون والمجموعات" ووضِّح أن هذا هو المكان الذي تحدد فيه المستخدمين والمجموعات في الدليل الذي ينطبق عليه النهج. حدد **0 مستخدم ومجموعة محددة**.  سترى الآن خيار تضمين أو استبعاد المستخدمين أو المجموعات. حدد ووضِّح الإعدادات المتاحة لعلامة التبويب **تضمين** ثم حدد واشرح الإعدادات المتاحة لعلامة التبويب **استبعاد**.
    1. **تطبيقات أو إجراءات السحابة** -  حرك الماوس فوق أيقونة المعلومات بجوار المكان حيث تظهر عبارة "تطبيقات أو إجراءات السحابة" ووضِّح أن هذا هو المكان الذي تحدد فيه التطبيقات المستخدمة أو الإجراءات المنفذة من قبل المستخدم، لنهج الوصول المشروط.  حدد **لا توجد تطبيقات أو إجراءات سحابة محددة**.
        1. حدد سهم القائمة المنسدلة في المربع أدناه حيث تظهر عبارة **حدد ما ينطبق عليه هذا النهج** ولاحظ الخيارات.  اترك الإعداد الافتراضي - تطبيقات السحابة.
        1. حدد ووضِّح الإعدادات المتاحة لعلامة التبويب تضمين. ضمن علامة التبويب **تضمين**، اختر **تحديد التطبيقات**.  لاحظ النافذة التي تفتح حيث يمكنك تحديد نموذج من قائمة التطبيقات.  لا تحدد أي شيء، أغلق هذه النافذة عن طريق تحديد **X** في الزاوية العلوية اليمنى من النافذة. ارجع إلى اختيار **بلا** لإزالة الخطأ.
        1. ثم حدد واشرح الإعدادات المتاحة لعلامة التبويب **استبعاد**.  ومن هنا، يمكنك تحديد تطبيقات معينة لاستبعادها.
    1. **الشروط** -  حرِّك مؤشر الماوس فوق أيقونة المعلومات بجوار المكان حيث تظهر عبارة "الشروط" ووضِّح أن هذا يحدد وقت تطبيق النهج. حدد **تم تحديد 0 شرط**. اشرح "الإشارات" المختلفة المدرجة.   حدد عددًا قليلاً من الخيارات عن طريق تحديد أيقونة المعلومات أولاً للوقوف على ماهيتها ثم حدد **غير مكوَّن** لعنصر معين لإظهار الخيارات المختلفة.
        1. **مخاطر المستخدم** -  تمثل مخاطر المستخدم احتمال تعرض هوية أو حساب معين للخطر. يتم حساب هذه المخاطر في وضع عدم الاتصال باستخدام مصادر معلومات التهديدات الداخلية والخارجية من Microsoft.
        1. **مخاطر تسجيل الدخول** -  تمثل مخاطر تسجيل الدخول احتمال أن طلب مصادقة معين غير مصرح به من قبل مالك الهوية. قد تشمل الأمثلة تسجيل الدخول من عنوان IP مجهول أو سفر غير نمطي، وما إلى ذلك.
        1. **النظام الأساسي للجهاز** -  النظام الأساسي الذي يقوم المستخدم بتسجيل الدخول منه. على سبيل المثال، "iOS".
        1. **الموقع** -  المكان (يتم تحديده باستخدام نطاق عناوين IP) الذي يقوم المستخدم بتسجيل الدخول منه
        1. **تطبيقات العميل** -  البرامج التي يستخدمها المستخدم للوصول إلى تطبيق السحابة. على سبيل المثال، "المستعرض"

1. **عناصر التحكم بالوصول** - بالعودة إلى القياس القائل بأن نهج الوصول المشروط تشبه عبارات "إذا/حينئذ"، فإن عناصر التحكم في الوصول مماثلة لعبارة "حينئذ".
    1. **المنح** -  حرك مؤشر الماوس فوق أيقونة المعلومات بجوار المكان الذي تظهر فيه عبارة "منح" للوصف.  حدد **تم تحديد 0 من عناصر التحكم** لإظهار الخيارات المختلفة.  اشرح بعضًا من هذه الخيارات.  وضِّح على وجه التحديد خيار **طلب المصادقة متعددة العوامل**، ضمن منح الوصول وكيف يمكن استخدام ذلك لتوفير تحكم دقيق للغاية فيما يتعلق بوقت اشتراط MFA.   وضح أيضًا أنه يمكنك تعيين عناصر تحكم متعددة والمطالبة بكل عناصر التحكم المحددة أو واحدة منها فقط.
    1. **الجلسة** -  حرك مؤشر الماوس فوق أيقونة المعلومات بجوار المكان الذي تظهر فيه عبارة "الجلسة" للوصف.  وضِّح أن عناصر التحكم في الجلسة تتيح تجربة محدودة داخل تطبيق سحابي.  على سبيل المثال، قد يتمكن المستخدم من الوصول إلى التطبيق السحابي ولكن سيتم حظره من تنزيل أي محتوى أو الطباعة، على سبيل المثال.  وهذا موضوع أكثر تعقيدًا، لذا حافظ على بساطة الشرح.

1. بمجرد تكوين النهج، يمكنك تمكين النهج عن طريق تحديد **تشغيل**، ثم الضغط على زر **إنشاء** لإنشاء نهج.

1. حدد **X** في الزاوية العلوية اليمنى من الصفحة لإغلاق النهج، ثم حدد Microsoft Azure على الشريط الأزرق أعلى الصفحة للعودة إلى الصفحة الرئيسية لمدخل Azure.

1. اترك صفحة المستعرض مفتوحة للعرض التوضيحي التالي.

### المراجعة

في هذا العرض التوضيحي، تعرفت على الخيارات المختلفة المتاحة لنهج الوصول المشروط.