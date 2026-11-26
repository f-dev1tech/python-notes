📘 ملخص أساسيات بايثون — مرجعكِ السريع (مترجم ومُنظَّم)

احفظي هذا الملف. كل ما تحتاجينه من الكورس موجود هنا. كل مصطلح إنجليزي بجانبه ترجمته.

---

1️⃣ المتغيرات وأنواع البيانات — Variables & Data Types

المصطلح الترجمة مثال
Variable متغير name = "Sara"
Integer (int) عدد صحيح age = 25
Float عدد عشري price = 9.99
String (str) نص city = "Khartoum"
Boolean (bool) قيمة منطقية is_active = True
None لا قيمة result = None

```python
name = "Sara"        # str
age = 25             # int
height = 1.65        # float
is_student = True    # bool
```

قاعدة: بايثون لا تحتاج تعريف النوع (dynamically typed) — هو يُستنتج تلقائيًا.

لمعرفة النوع: type(age) → <class 'int'>

---

2️⃣ المعاملات — Operators

الحسابية (Arithmetic)

المعامل المعنى
+ جمع
- طرح
* ضرب
/ قسمة (ناتج عشري)
// قسمة صحيحة (Integer Division)
% باقي القسمة (Modulo)
** أس (Power)

```python
10 / 3   # 3.333...
10 // 3  # 3
10 % 3   # 1
2 ** 3   # 8
```

المقارنة (Comparison)

== يساوي | != لا يساوي | > أكبر | < أصغر | >= | <=
الناتج دائمًا True أو False.

المنطقية (Logical)

المعامل المعنى
and و (كلا الشرطين)
or أو (أحدهما)
not نفي

---

3️⃣ النصوص — Strings

```python
s = "Hello World"

len(s)              # 11 — length (الطول)
s.upper()           # "HELLO WORLD" — تحويل لأحرف كبيرة
s.lower()           # "hello world"
s.replace("World", "Python")  # استبدال
s.split(" ")        # ['Hello', 'World'] — تقسيم
s.strip()           # إزالة الفراغات من الطرفين
s[0]                # 'H' — indexing (فهرسة)
s[-1]               # 'd' — آخر حرف
s[0:5]              # 'Hello' — slicing (تقطيع)
```

f-strings (أفضل طريقة للتنسيق)

```python
name = "Sara"
age = 25
print(f"My name is {name} and I am {age}")
```

---

4️⃣ الإدخال والإخراج — Input & Output

```python
name = input("Enter your name: ")     # input = إدخال (نص دائمًا)
age = int(input("Enter your age: "))  # تحويل لنوع رقم
print("Hello", name)                  # print = طباعة
```

تنبيه: input() ترجع نصًا دائمًا (str). لازم تحوّليها بـ int() أو float() إذا احتجتِ رقمًا.

---

5️⃣ الشروط — Conditionals

```python
if score >= 90:
    print("A")
elif score >= 80:
    print("B")
else:
    print("C")
```

المصطلح الترجمة
if إذا
elif وإلا إذا
else وإلا

قواعد مهمة:

· بعد الشرط لازم : (نقطتان).
· الإزاحة (Indentation) بـ 4 مسافات — ليست اختيارية.

Ternary (شرط مختصر)

```python
status = "adult" if age >= 18 else "minor"
```

---

6️⃣ الحلقات — Loops

for loop (حلقة تكرار)

```python
for i in range(5):        # 0,1,2,3,4
    print(i)

for name in ["Ali", "Sara", "Omar"]:
    print(name)
```

الدالة المعنى
range(5) من 0 إلى 4
range(1, 6) من 1 إلى 5
range(0, 10, 2) 0,2,4,6,8 (خطوة 2)

while loop

```python
count = 0
while count < 5:
    print(count)
    count += 1
```

كلمات التحكم — Control Keywords

الكلمة المعنى
break كسر الحلقة (خروج فوري)
continue تخطي الدورة الحالية

---

7️⃣ هياكل البيانات — Data Structures

List (قائمة) — قابلة للتعديل، مرتبة، تسمح بالتكرار

```python
nums = [1, 2, 3, 4]
nums.append(5)        # إضافة في النهاية
nums.insert(0, 0)     # إدراج في موقع
nums.remove(3)        # حذف أول 3
nums.pop()            # حذف الأخير
nums.sort()           # ترتيب
len(nums)             # الطول
```

Tuple (صف) — غير قابل للتعديل

```python
point = (10, 20)
# point[0] = 5 ❌ خطأ
```

Dictionary (قاموس) — أزواج مفتاح:قيمة

```python
person = {"name": "Sara", "age": 25}
person["name"]           # "Sara" — وصول
person["city"] = "Khartoum"  # إضافة
person.get("job", "None")    # وصول آمن بقيمة افتراضية
person.keys()            # كل المفاتيح
person.values()          # كل القيم
person.items()           # أزواج (مفتاح، قيمة)
```

Set (مجموعة) — بدون تكرار، غير مرتبة

```python
unique = {1, 2, 3, 3, 3}   # {1, 2, 3}
```

متى أستخدم كل واحدة؟

النوع متى تستخدمينه
List عندما تحتاجين ترتيبًا وتعديلًا
Tuple عندما تكون البيانات ثابتة (إحداثيات، ثوابت)
Dictionary عندما تربطين قيمة بمفتاح (بحث سريع)
Set عندما تريدين إزالة التكرار

---

8️⃣ الدوال — Functions

```python
def greet(name, greeting="Hello"):
    """Return a greeting message."""
    return f"{greeting}, {name}!"

print(greet("Sara"))              # Hello, Sara!
print(greet("Sara", "Hi"))        # Hi, Sara!
```

المصطلح الترجمة
def تعريف دالة
parameter معامل (في التعريف)
argument وسيط (عند الاستدعاء)
return إرجاع قيمة
default value قيمة افتراضية
docstring وصف الدالة (بين """)

قاعدة ذهبية: الدالة تؤدي مهمة واحدة فقط، وتكون قصيرة.

---

9️⃣ معالجة الأخطاء — Error Handling

```python
try:
    num = int(input("Enter number: "))
    result = 10 / num
except ValueError:
    print("Not a valid number")
except ZeroDivisionError:
    print("Cannot divide by zero")
finally:
    print("Done")
```

المصطلح الترجمة
try جرّب
except التقط الخطأ
finally دائمًا ينفذ
raise ارفع خطأ

أنواع أخطاء شائعة:

· ValueError — قيمة غير صحيحة
· TypeError — نوع غير متوافق
· ZeroDivisionError — قسمة على صفر
· IndexError — فهرس خارج النطاق
· KeyError — مفتاح غير موجود

---

🔟 الملفات — Files

```python
# الكتابة (w = overwrite, a = append)
with open("data.txt", "w", encoding="utf-8") as f:
    f.write("Hello\n")

# القراءة
with open("data.txt", "r", encoding="utf-8") as f:
    content = f.read()
```

الوضع المعنى
"r" قراءة (read)
"w" كتابة (يمسح القديم)
"a" إضافة (append)

with تضمن إغلاق الملف تلقائيًا.

JSON (تنسيق شائع لحفظ البيانات)

```python
import json

data = {"name": "Sara", "age": 25}

# حفظ
with open("data.json", "w") as f:
    json.dump(data, f)

# قراءة
with open("data.json", "r") as f:
    data = json.load(f)
```

---

1️⃣1️⃣ الوحدات — Modules

```python
import math
print(math.sqrt(16))    # 4.0

from random import randint
print(randint(1, 10))   # عدد عشوائي بين 1 و10

import datetime
print(datetime.datetime.now())
```

المصطلح الترجمة
module وحدة/ملف مكتبة
import استيراد
from ... import استيراد جزء محدد

---

1️⃣2️⃣ أساسيات OOP — البرمجة الكائنية

```python
class Student:
    def __init__(self, name, age):    # constructor (باني)
        self.name = name              # attribute (خصيصة)
        self.age = age

    def introduce(self):              # method (دالة داخلية)
        return f"I am {self.name}, {self.age} years old"

s = Student("Sara", 25)               # object (كائن)
print(s.introduce())
```

المصطلح الترجمة
class صنف/فئة
object كائن
attribute خاصية
method دالة الكائن
__init__ الباني (Constructor)
self الكائن نفسه
inheritance الوراثة
class Child(Parent): الوراثة من صنف

---

1️⃣3️⃣ دوال مدمجة مهمة — Built-in Functions

الدالة المعنى مثال
len() الطول len([1,2,3]) → 3
sum() مجموع sum([1,2,3]) → 6
max() / min() أكبر/أصغر max(1, 5, 3) → 5
abs() القيمة المطلقة abs(-5) → 5
round() تقريب round(3.7) → 4
sorted() إرجاع نسخة مرتبة sorted([3,1,2])
enumerate() فهرسة مع القيمة for i, v in enumerate(items):
zip() دمج قوائم zip([1,2],["a","b"])
type() نوع type(5)
int(), str(), float() تحويل النوع int("5")

---

1️⃣4️⃣ قواعد ذهبية لا تنسيها 🚨

1. الإزاحة (Indentation) = 4 مسافات — ليست تجميلًا، هي صياغة.
2. بعد if / for / while / def / class لازم :
3. input() ترجع نصًا — حوّليها لرقم إذا احتجتِ.
4. = إسناد، == مقارنة — لا تخلطي بينهما.
5. الأقواس تُغلق دائمًا: (, ), [, ], {, }
6. print دالة — بأقواس دائمًا.
7. أسماء المتغيرات snake_case: user_name, total_price.
8. الأسماء الواضحة أهم من التعليقات.

---

1️⃣5️⃣ أخطاء شائعة تفحصينها أولًا عند أي خطأ ⚠️

الخطأ السبب الشائع
SyntaxError سطر سابق ناقص قوس أو نقطتين
IndentationError إزاحة غير متساوية
NameError اسم متغير لم يُعرَّف أو خطأ إملائي
TypeError خلط أنواع مثل "5" + 5
IndexError فهرس أكبر من القائمة
KeyError مفتاح غير موجود في Dictionary

---


 ا
