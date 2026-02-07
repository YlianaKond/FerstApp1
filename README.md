Приложение где при на жатии на кнопку "Нажми меня" пользователю показывается рандомное число от 1 до 6
Выполнили студентки Кондусова Ульяна и Клынкина Ольга
<img width="522" height="462" alt="image" src="https://github.com/user-attachments/assets/0ae928a9-4e6c-43f3-8162-cd33449e3312" />
<?xml version="1.0" encoding="utf-8"?>

class MainActivity : AppCompatActivity() {
class - объявление класса.
MainActivity - имя класса (главная активность приложения).
: AppCompatActivity() - наследование от базового класса активности.

private lateinit var binding: ActivityMainBinding
private - модификатор доступа (только внутри класса).
lateinit - инициализация переменной произойдет позже (гарантируем, что не будет null).
var - изменяемая переменная.
binding - имя переменной.
: ActivityMainBinding - тип (класс ViewBinding).

override fun onCreate(savedInstanceState: Bundle?) {
override - переопределение метода родительского класса.
fun - объявление функции.
onCreate - системный метод Android, вызывается при создании активности.
savedInstanceState: Bundle? - параметр с сохраненным состоянием (может быть null).

super.onCreate(savedInstanceState)
super - обращение к родительскому классу.
onCreate(savedInstanceState) - вызов родительской реализации для правильной инициализации.

enableEdgeToEdge()
Включает режим edge-to-edge - контент уходит под статус-бар и навигацию.

binding = ActivityMainBinding.inflate(layoutInflater)
binding = - присваивание ViewBinding.
ActivityMainBinding.inflate() - создает экземпляр binding из XML.
layoutInflater - системный объект для "надувания" XML в view.

setContentView(binding.root)
setContentView() - устанавливает содержимое активности.
binding.root - корневой view из activity_main.xml.

ViewCompat.setOnApplyWindowInsetsListener(binding.main) { v, insets ->
ViewCompat.setOnApplyWindowInsetsListener - устанавливает слушатель системных отступов.
binding.main - корневой layout из XML (id="main").
{ v, insets -> - лямбда-функция (анонимная функция) с параметрами:
v - View, к которому применяются отступы
insets - объект с информацией об отступах системы

val systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars())
val - неизменяемая переменная.
systemBars - отступы системных панелей.
insets.getInsets() - получает конкретные отступы.
WindowInsetsCompat.Type.systemBars() - тип отступов (статус-бар + навигация).

v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom)
v.setPadding() - устанавливает внутренние отступы для view.
systemBars.left/top/right/bottom - отступы слева/сверху/справа/снизу.

insets - возвращаемое значение лямбды (передаем отступы дальше по цепочке).

binding.button.setOnClickListener {
binding.button - кнопка из XML (id="button").
setOnClickListener - устанавливает обработчик нажатий.

val number = (0..6).random()
val number - локальная неизменяемая переменная.
(0..6) - диапазон чисел от 0 до 6 включительно (.. - rangeTo).
.random() - расширение Kotlin, возвращает случайное число из диапазона.

binding.result.text = number.toString()
binding.result - TextView из XML (id="result").
.text - свойство текста.
number.toString() - преобразует число в строку.
