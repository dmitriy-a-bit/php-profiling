# Используем образ php:fpm
FROM php:fpm

# URI тестового файла
ENV TEST_FILE https://gist.githubusercontent.com/atastycookie/ddc27d77f84f9fbe0b469b0b204b89e5/raw/6613b032ce23e2f682592f58c36d5cf98a34d2f2/test.php

# Директория приложения
ENV APP_HOME /app

# Обновляем репозитории и устанавливаем strace и procps
RUN apt-get update && apt-get install strace procps -y

# Создаем директорию с приложением
RUN mkdir $APP_HOME

# Делаем ее рабочей директорией
WORKDIR $APP_HOME

# Загружаем тестовый файл
RUN curl -LJO $TEST_FILE

# Запускаем php-fpm
CMD ["php-fpm"]
