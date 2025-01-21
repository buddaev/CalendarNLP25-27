# CalendarNLP25-27
import csv
from datetime import datetime, timedelta

# Функция для создания событий в формате CSV для импорта в Google Calendar
def create_calendar_csv(file_path):
    # Заголовки для CSV файла
    headers = [
        "Subject", "Start Date", "Start Time", "End Date", "End Time", 
        "All Day Event", "Description", "Location", "Private"
    ]

    # Список событий
    events = [
        # Февраль 2025
        {"Subject": "Обновить резюме и портфолио", "Start Date": "2025-02-01", "End Date": "2025-02-07", "All Day Event": "True"},
        {"Subject": "Отклики на вакансии (5–7 в день)", "Start Date": "2025-02-08", "End Date": "2025-02-28", "All Day Event": "True"},
        {"Subject": "Прохождение собеседований", "Start Date": "2025-02-08", "End Date": "2025-02-28", "All Day Event": "True"},
        
        # Март 2025
        {"Subject": "Завершение поиска работы и получение оффера", "Start Date": "2025-03-01", "End Date": "2025-03-15", "All Day Event": "True"},
        {"Subject": "Изучение основ MLOps (Git, Docker)", "Start Date": "2025-03-16", "End Date": "2025-03-31", "All Day Event": "True"},

        # Апрель–Июнь 2025
        {"Subject": "Создание проекта на базе GPT-like модели", "Start Date": "2025-04-01", "End Date": "2025-06-30", "All Day Event": "True"},
        {"Subject": "Изучение дообучения моделей (Hugging Face, PyTorch)", "Start Date": "2025-04-01", "End Date": "2025-06-30", "All Day Event": "True"},
        {"Subject": "Участие в open-source проектах", "Start Date": "2025-04-01", "End Date": "2025-06-30", "All Day Event": "True"},

        # Июль–Декабрь 2025
        {"Subject": "Освоение продвинутых техник NLP", "Start Date": "2025-07-01", "End Date": "2025-12-31", "All Day Event": "True"},
        {"Subject": "Участие в Kaggle-соревнованиях и хакатонах", "Start Date": "2025-07-01", "End Date": "2025-12-31", "All Day Event": "True"},
        {"Subject": "Развитие GitHub-портфолио", "Start Date": "2025-07-01", "End Date": "2025-12-31", "All Day Event": "True"},

        # Январь–Декабрь 2026
        {"Subject": "Применение NLP/LLM в рабочих проектах", "Start Date": "2026-01-01", "End Date": "2026-12-31", "All Day Event": "True"},
        {"Subject": "Изучение оптимизации моделей (прунинг, квантование)", "Start Date": "2026-01-01", "End Date": "2026-12-31", "All Day Event": "True"},
        {"Subject": "Ведение блога о NLP-достижениях", "Start Date": "2026-01-01", "End Date": "2026-12-31", "All Day Event": "True"},
        
        # Январь 2027
        {"Subject": "Развитие лидерских навыков", "Start Date": "2027-01-01", "End Date": "2027-01-10", "All Day Event": "True"},
        {"Subject": "Подготовка к сертификациям (AWS, Google ML Engineer)", "Start Date": "2027-01-01", "End Date": "2027-01-10", "All Day Event": "True"},
        {"Subject": "Проверка готовности к роли Senior NLP Engineer", "Start Date": "2027-01-01", "End Date": "2027-01-10", "All Day Event": "True"}
    ]

    # Создание CSV файла
    with open(file_path, mode='w', newline='', encoding='utf-8') as file:
        writer = csv.DictWriter(file, fieldnames=headers)
        writer.writeheader()
        for event in events:
            writer.writerow({
                "Subject": event["Subject"],
                "Start Date": event["Start Date"],
                "Start Time": "",
                "End Date": event["End Date"],
                "End Time": "",
                "All Day Event": event["All Day Event"],
                "Description": "",
                "Location": "",
                "Private": "True"
            })

# Создаем файл
file_path = "/mnt/data/Senior_NLP_Engineer_Calendar.csv"
create_calendar_csv(file_path)
file_path
