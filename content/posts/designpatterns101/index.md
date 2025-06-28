+++
date = '2025-06-27T02:43:35+01:00'
draft = false
title = 'Design Patterns و فاش كينفعو؟ '
tags= ["Design Patterns", "Software Design", "Code"]
categories= ["blog"]
[cover] 
    image = "cover.png"
    relative = true
+++
----------------------------------------------------------
سلام شباب 👋
هدا أول Blog ليا فهد newsletter 📬
أنقدم لكم راسي بش ندوز لمفيد
أنا سميتي Mohammed مهندس معلوميات 💻 دكشي ديال طبرمجيت

منطولش عليكم بزاف ⏱️
أول حاجة بغيت ندوي فيها، او من شحال هادي كنتناقش فيها مع دراري،
**لي هي: Design Patterns 🤔
و فاش كينفعو؟ 🔧**

من l'experience ديالي 🎓 و دكشي لي كنعرف (الله إزيدنا) 🤲
بزاف ديال دراري كيخلعهم موضوع Design Patterns
دكشي علاش قررت ندير series ندوي فيهم غير على هاد lConcepts 🎯

### شنهما هاد Design Patterns؟

Design Patterns راه واحد Templates ديال Solutions لي واجدين ✅
و كيحلو لينا مشاكل كيتعاودو بزاف.

تخيل بلي عندك واحد Lbox فيه Tools 🧰
و فاش كطيح فشي Problem كتخدم بواحد Tool لي واجد،
و Devs فكروا فيه قبل منك، بلا ما تعاود تخترعو.

مثال: بغيت يكون عندك غير Object واحد فـ Project كامل؟
ساهلة: Singleton 🧱

## 🔧 Singleton كود:

```java 
    public class SingleObject {

        //create an object of SingleObject
        private static SingleObject instance = new SingleObject();

        //make the constructor private so that this class cannot be
        //instantiated
        private SingleObject(){}

        //Get the only object available
        public static SingleObject getInstance(){
            return instance;
        }

    }
} 
```


**Design Patterns** عندهم واحد المفهوم لي غادي تلقاه عند قاع Devs 🌍
و كيخلي الcode يكون مفهُوم بين الناس،
بلا ما يكون خاص بلغة برمجة معينة.

هاد lConcept كيعاونك تكتب code لي هو:

-✅ clean

-✅ readable

-✅ ساهل فـ maintenance

-✅ و أي واحد غيخدم به، غيكون فرحان ويدعي معك 🙌

⚠️ **مهم تعرف:**
 
Design Patterns كنستعملوهم غير فاش كيلزم الأمر.
ماتستعملهمش غير باش تبان fancy.
إلا ماكانش المشكل كيدعي ليهم، راك غادي تطيح فـ Over Engineering 🚫

ماغاديش ندخل دابا فـ details حيت غادي ندوي على كل واحد بوحدو فـ بوست خاص 🔄
ولكن خلاصة القول:
Design Patterns = Toolbox لي كيعاون فالكتابة ديال Code منظم
و ماشي بش إخلعك 😎

ماتستعملهمش إلا فـ الحالة المناسبة لي تستاهلهم
باش الكود ديالك يبقى خفيف و مافيهش تعقيد زايد 🔥