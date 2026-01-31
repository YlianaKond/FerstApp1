Приложение где при на жатии на кнопку "Нажми меня" пользователю показывается рандомное число от 1 до 6
Выполнил студент Кондусова Ульяна
<img width="522" height="462" alt="image" src="https://github.com/user-attachments/assets/0ae928a9-4e6c-43f3-8162-cd33449e3312" />
<?xml version="1.0" encoding="utf-8"?>

private lateinit var binding: ActivityMainBinding - приватная поздняя инициализация с типом переменных ActivityMainBinding
override fun onCreate(savedInstanceState: Bundle?) - переопределение функции при создании
super.onCreate(savedInstanceState) - вызов родителя при создании 
enableEdgeToEdge() - Включает современный стиль
binding = ActivityMainBinding.inflate(layoutInflater) - сгенерированный класс, который превращает XML в живые объекты Kotlin/Java, системный сервис Android для создания View из XML


