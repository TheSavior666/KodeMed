+++
date = '2026-03-29T00:00:00+01:00'
draft = false
title = 'Java Design: علاش Interfaces أحسن من Abstract Classes؟'
tags = ["Java", "Interfaces", "Abstract Classes", "OOP", "Design Patterns"]
categories = ["blog"]

[cover] 
    image = "Interfaces vs Abstract Classes comparison.png"
    relative = true
+++
----------------------------------------------------------
3علاش خاصنا نفضّلو interfaces على abstract classes فـ Java؟ حيت كيعطيو واحد flexibility كبيرة فـ design ديال applications. فـ Java كاين single inheritance، يعني class تقدر غير تورث من abstract class وحدة، ولكن تقدر تطبّق بزاف ديال interfaces فـ نفس الوقت. هادشي كيخلّي interfaces حسن باش نبنيو systems scalable و flexible.

Interfaces كيخلّيو لينا نزيدو behavior ل classes بلا ما نبدّلو الhierarchy ديالهم. هادا كيتسمّى mixin، بحال Comparable لي كيخلّي objects يقدرو يتقارنو. Abstract classes ما يقدروش يديرو هادشي حيث خاصهم يكونو parent مباشر، وهادشي كيقيّد الdesign وكيخلّيه rigid.

زيد على هادشي، interfaces ساهلين باش نطبّقوهم على classes قدام (legacy code). غير كتزيد implements وكتكتب methods لي خاصين. بالعكس، abstract classes صعيب تدخلهم إلا ما كانوش من اللول فـ design ديال المشروع.

من بعد Java 8، interfaces وْلاو فيهم default methods، يعني تقدر تكتب implementation مباشرة فـ interface. هادي كتنقص duplication وكتسهّل الخدمة على developers. ولكن كاينين restrictions: ما تقدرش تدير default methods ديال equals و hashCode و toString، وما كايناش instance fields.

🧠 Skeletal Implementation (شرح + كود)

باش نجمعو بين interfaces و abstract classes، كاين واحد pattern سميتو skeletal implementation.

الفكرة:

كنعرّفو interface فيها العقد (contract)
ومن بعد كنديرو abstract class كتطبّق داك interface وكتعطي implementation جزئية
developer غير كيكمّل methods البسيطة (primitive methods)

هادشي كيعاون بزاف وكيقصّر الخدمة.

👇 مثال
1. Interface
public interface MyList<E> {
    int size();
    E get(int index);

    default boolean isEmpty() {
        return size() == 0;
    }
}
2. Skeletal Implementation (Abstract Class)
public abstract class AbstractMyList<E> implements MyList<E> {

    @Override
    public boolean isEmpty() {
        return size() == 0;
    }

    public boolean contains(E element) {
        for (int i = 0; i < size(); i++) {
            if (get(i).equals(element)) {
                return true;
            }
        }
        return false;
    }
}

👉 هنا عطينا logic عام، ولكن خلّينا size() و get() بلا implementation.

3. Concrete Class (الاستعمال)
import java.util.ArrayList;
import java.util.List;

public class MyArrayList<E> extends AbstractMyList<E> {

    private List<E> internal = new ArrayList<>();

    @Override
    public int size() {
        return internal.size();
    }

    @Override
    public E get(int index) {
        return internal.get(index);
    }

    public void add(E element) {
        internal.add(element);
    }
}
4. Usage
public class Main {
    public static void main(String[] args) {
        MyArrayList<String> list = new MyArrayList<>();

        list.add("Java");
        list.add("Spring");

        System.out.println(list.contains("Java")); // true
        System.out.println(list.isEmpty());        // false
    }
}
🔥 Template Method Pattern

هاد الطريقة كتدخل حتى فـ Template Method Pattern:

abstract class فيها logic عام
والclasses لي كيرثو منها كيكمّلو التفاصيل
⚙️ Composition بدل Inheritance

إلا ما قدرتيش تورث من abstract class (حيت كاين inheritance آخر)، تقدر تستعمل composition:

كتدير object داخل class ديالك
وكتستافد من logic ديالو بلا inheritance

هادشي كيتسمّى simulated multiple inheritance

✅ الخلاصة
interfaces هما أحسن اختيار باش تعرّف types
كيعطيو flexibility و scalability
abstract classes خاصهم يتستعملو غير باش يعاونو فـ implementation
skeletal implementation pattern كيسهّل الخدمة بزاف

📚 المصدر:
Effective Java (3rd Edition) - Joshua Bloch (Item 20)
