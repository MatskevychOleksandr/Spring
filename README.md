# Spring
Функціональні вимоги:

1. Як адміністратор системи, я хочу мати можливість додавати нові курси до бази даних, щоб розширити навчальну програму.
2. Як адміністратор системи, я хочу мати можливість керувати списком викладачів та їхніми даними, щоб забезпечити актуальність інформації про кадри.
3. Як адміністратор системи, я хочу мати можливість створювати розклад занять для кожного курсу, щоб студенти та викладачі могли планувати свій час.
4. Як викладач, я хочу мати можливість завантажувати матеріали для навчання (лекції, презентації, завдання), щоб студенти могли мати до них доступ.
5. Як викладач, я хочу мати можливість створювати тести та завдання для оцінювання знань студентів.
6. Як студент, я хочу мати можливість переглядати список доступних курсів, щоб обрати ті, що мене цікавлять.
7. Як студент, я хочу мати можливість переглядати матеріали для навчання та завдання, щоб готуватися до занять.
8. Як студент, я хочу мати можливість проходити тести та завдання для перевірки своїх знань.
9. Як адміністратор системи, я хочу мати можливість відстежувати академічний прогрес студентів, щоб аналізувати ефективність навчальної програми.
10. Як адміністратор системи, я хочу мати можливість надсилати повідомлення студентам та викладачам щодо важливих подій та оновлень на платформі.
   
Системні поведінки:

1. Додавання нового курсу:
- Користувач може додати новий курс, вказавши його назву та опис.
- Система перевіряє, чи немає вже такого курсу в базі даних.
- Якщо курс є унікальним, він додається до бази даних.
2. Надання доступу до курсу:
- Адміністратор може надати доступ до курсу викладачеві.
- Система перевіряє, чи існує в базі даних вказаний викладач.
- Якщо викладач знайдений, йому надається доступ до курсу.
3. Створення завдання для курсу:
- Викладач може створити завдання для студентів курсу.
- Система зберігає завдання в базі даних та повідомляє студентів про їх наявність.
4. Завершення курсу студентом:
- Студент може позначити курс як завершений після виконання всіх завдань.
- Система відображає статус завершення курсу для студента.
5. Створення відгуку про курс:
- Студент може залишити відгук про курс після його завершення.
- Система зберігає відгук в базі даних та відображає його на сторінці курсу.
6. Створення ролей користувачів:
- Адміністратор може створювати нові ролі користувачів (адміністратор, викладач, студент) та призначати їх користувачам.
- Система зберігає інформацію про ролі користувачів та їх права доступу.
7. Авторизація та аутентифікація користувачів:
- Користувачі можуть увійти до системи, використовуючи логін та пароль.
- Система перевіряє введені дані та надає доступ до функціоналу відповідно до ролі користувача.
8. Відслідковування активності користувачів:
- Система відстежує дії користувачів (створення, редагування, видалення об'єктів) для забезпечення безпеки та відновлення даних у разі потреби.
- Користувачі можуть переглядати власну активність та зміни, зроблені іншими користувачами.
9. Налаштування повідомлень та сповіщень:
- Користувачі можуть налаштовувати сповіщення про події на платформі (нові курси, оновлення, нагадування про завдання).
- Система надсилає сповіщення користувачам відповідно до їхніх налаштувань.
10. Інтеграція з системами оцінювання:
- Система може інтегруватися з системами оцінювання для автоматичного оновлення оцінок студентів за завершення завдань та курсів.
- Користувачі можуть переглядати свої актуальні оцінки безпосередньо в системі навчання.

REST API:

1. Додавання нового курсу
- Метод: POST
- URL: /api/courses
- Параметри: course_name (назва курсу), course_description (опис курсу)
- Відповідь: Підтвердження додавання нового курсу.
2. Надання доступу до курсу
- Метод: POST
- URL: /api/courses/access
- Параметри: course_id (ідентифікатор курсу), teacher_id (ідентифікатор викладача)
- Відповідь: Підтвердження надання доступу викладачу до курсу.
3. Створення завдання для курсу
- Метод: POST
- URL: /api/courses/tasks
- Параметри: course_id (ідентифікатор курсу), task_description (опис завдання)
- Відповідь: Підтвердження створення нового завдання для курсу.
4. Завершення курсу студентом
- Метод: PUT
- URL: /api/courses/complete
- Параметри: course_id (ідентифікатор курсу), student_id (ідентифікатор студента)
- Відповідь: Підтвердження завершення студентом курсу.
5. Створення відгуку про курс
- Метод: POST
- URL: /api/courses/reviews
- Параметри: course_id (ідентифікатор курсу), student_id (ідентифікатор студента), review_text (текст відгуку)
- Відповідь: Підтвердження створення відгуку про курс.
6. Інтеграція з системами оцінювання
- Метод: POST
- URL: /api/courses/grades
- Параметри: course_id (ідентифікатор курсу), student_id (ідентифікатор студента), grade (оцінка)
- Відповідь: Підтвердження оновлення оцінки студента за курс.
7. Налаштування повідомлень та сповіщень
- Метод: PUT
- URL: /api/notifications/settings
- Параметри: user_id (ідентифікатор користувача), notification_settings (налаштування повідомлень)
- Відповідь: Підтвердження збереження налаштувань повідомлень користувача.
8. Відслідковування активності користувачів
- Метод: GET
- URL: /api/users/activity
- Параметри: user_id (ідентифікатор користувача)
- Відповідь: Список активностей користувача на платформі.
9. Забезпечення авторизації та аутентифікації користувачів:
- Метод: POST
- URL: /api/auth/login
- Параметри: username (ім'я користувача), password (пароль)
- Відповідь: Токен доступу, який може бути використаний для аутентифікації в інших запитах.
10. Перевірка прав доступу користувача:
- Метод: GET
- URL: /api/auth/verify
- Параметри: token (токен доступу)
- Відповідь: Підтвердження валідності токену та інформація про користувача (роль, ідентифікатор тощо).
