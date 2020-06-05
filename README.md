# Створення сокет-клієнта
![](socket.png)

Ця робота доповнює основний цикл лабораторних робіт #1-8 (проект **Banking**, [Netbeans](https://netbeans.org/)) з ООП на третьому курсі [ППК НТУ "ХПІ](http://polytechnic.poltava.ua)". Основна мета роботи - познайомитись з мережевими можливостями Java на прикладі сокетних комунікацій. Згадувані 'базові' роботи розміщено в [окремому репозиторії](https://github.com/liketaurus/OOP-JAVA).

##  Архітектура системи
В цій роботі ви напишете код для під'єднання чат-клієнта до сервера (код сервера надається). Чат-сервер відповідає за надсилання повідомлень, отриманих від одного клієнта, усім підключеним клієнтам (включаючи оригінального відправника). На рисунку показано діаграму архітектури системи, в якій кілька клієнтів приєднані до одного чат-сервера. У цьому сценарії Саймона пише This is cool! у текстовому полі, призначеному для тексту повідомлення, та вказує своє ім'я (Саймон) у відповідному текстовому полі клієнта і надсилає  його на сервер через вихідний потік (крок 1). Сервер отримує повідомлення, а потім пересилає повідомлення кожному приєднаному клієнту (кроки 2–4). При цьому порядок переданих повідомлень не є важливим.

![](https://github.com/ppc-ntu-khpi/Sockets-Starter/blob/master/Client-Server.png)

Клієнт чату (наданий вам [код](https://github.com/ppc-ntu-khpi/Sockets-Starter/blob/master/classes/ChatClient.java)) має бути змінений, аби додати дві важливі функції: 
* надсилання повідомлення користувача до сервера
* відображення всіх отриманих від сервера повідомлень

На рисунку показано детальну будову програми ChatClient. Вам потрібно додати метод **doConnect** до класу **ChatClient** для ініціації сокетного під'єднання до чат-сервера.

![](https://github.com/ppc-ntu-khpi/Sockets-Starter/blob/master/ChatClient.png)

## Хід роботи

1. створіть новий проект у середовищі розробки за вашим вибором
2. додайте в проект файл [ChatClient](https://github.com/ppc-ntu-khpi/Sockets-Starter/blob/master/classes/ChatClient.java) і відкрийте його
3. імпортуйте потрібні пакети:
````java
import java.net.*;
import java.io.*;
````
4. додайте до класу змінні для вхідного та вихідного потоків:
````java 
public class ChatClient {
  //решта коду
  private Socket connection = null;
  private BufferedReader serverIn = null;
  private PrintStream serverOut = null;
  //решта коду
}
````


**Додаткові завдання** (для тих хто зробив все і прагне більшого):
Всі необхідні бібліотеки містяться у теці [jars](https://github.com/liketaurus/TUI-Labs/tree/master/jars). В тому числі - всі необхідні класи з робіт 1-8 - файл [MyBank.jar](https://github.com/liketaurus/TUI-Labs/blob/master/jars/MyBank.jar). Файл даних лежить у теці [data](https://github.com/liketaurus/TUI-Labs/tree/master/data).

---
**УВАГА! Не забувайте завантажувати результати виконання робіт до своїх репозиторіїв!**

![](https://img.shields.io/badge/Made%20with-JAVA-red.svg)
![](https://img.shields.io/badge/Made%20with-%20Netbeans-brightgreen.svg)
![](https://img.shields.io/badge/Made%20at-PPC%20NTU%20%22KhPI%22-blue.svg) 
