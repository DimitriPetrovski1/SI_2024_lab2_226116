# SI_2024_lab2_226116
Димитри Петровски 226116

*Control Flow Graph*
![code2flow_XGjKt8](https://github.com/DimitriPetrovski1/SI_2024_lab2_226116/assets/167122611/b38897c3-b655-4092-a941-99e53aba707c)

*Цикломатска комплексност*
Бидејќи кодот има 6 предикатни јазли а формулата е Бројот на предикатни јазли + 1, Значи цикломатската комплескност е 7

*Тест случаи според критериумот Every statement*
1.
Input: allItems = null, payment = 100
Очекуван Output: Throws RuntimeException "allItems list can't be null!"

2.
Input: allItems = [new Item(null, "12345", 100, 0.1f)], payment = 200
Очекуван Output: True
Објаснување: Името е наместено "unknown", barcode е valid, нема discount, total sum е помал payment.

3.
Input: allItems = [new Item("item1", null, 100, 0.1f)], payment = 200
Очекуван Output: Throws RuntimeException "No barcode!"
Објаснување: Barcode е null.

4.
Input: allItems = [new Item("item1", "12a45", 100, 0.1f)], payment = 200
Очекуван Output: Throws RuntimeException "Invalid character in item barcode!"
Објаснување: Barcode има невалиден карактер 'a'.

5.
Input: allItems = [new Item("item1", "12345", 100, 0.1f)], payment = 9
Очекуван Output: False
Објаснување: Total sum е над payment.

6.
Input: allItems = [new Item("item1", "012345", 400, 0.1f)], payment = 500
Очекуван Output: True
Објаснување: discount applies, total sum е помал од payment.

*Тест случаи според критериумот Every path*
1.
Condition: price > 300, discount > 0, barcode.charAt(0) == '0'
Input: allItems = [new Item("item1", "012345", 400, 0.1f)], payment = 500
Очекуван Output: True
Објаснување: Сите услови се true, discount applies.

2.
Condition: price > 300, discount > 0, barcode.charAt(0) != '0'
Input: allItems = [new Item("item1", "112345", 400, 0.1f)], payment = 500
Очекуван Output: True
Објаснување: Само третиот услов е false, нема discount.

3.
Condition: price > 300, discount <= 0, barcode.charAt(0) == '0'
Input: allItems = [new Item("item1", "012345", 400, 0.0f)], payment = 500
Очекуван Output: True
Објаснување: Само вториот услов е false, нема discount.

4.
Condition: price <= 300, discount > 0, barcode.charAt(0) == '0'
Input: allItems = [new Item("item1", "012345", 300, 0.1f)], payment = 500
Очекуван Output: True
Објаснување: Само првиот услов е false, нема discount.

5.
Condition: price <= 300, discount <= 0, barcode.charAt(0) == '0'
Input: allItems = [new Item("item1", "012345", 300, 0.0f)], payment = 500
Очекуван Output: True
Објаснување: Првиот и вториот услов се false, нема discount.

6.
Condition: price > 300, discount <= 0, barcode.charAt(0) != '0'
Input: allItems = [new Item("item1", "112345", 400, 0.0f)], payment = 500
Очекуван Output: True
Explanation: Вториот и третиот услов се false, нема discount.
