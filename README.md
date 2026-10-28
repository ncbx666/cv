# Распознавание автомобильных номеров (ANPR)

Ноутбук для Google Colab: поиск номерных знаков на изображениях с помощью
YOLOv9. Чтение номера через EasyOCR задумано, но пока не сделано: пакет
устанавливается, а распознавание текста в ноутбуке не вызывается.

- Ноутбук: [`Automatic_number_plate_recognition_(ANPR)_with_Yolov9_and_EasyOCR.ipynb`](Automatic_number_plate_recognition_(ANPR)_with_Yolov9_and_EasyOCR.ipynb)
  (кнопка «Open in Colab» в первой ячейке)
- Данные: [ANPR2 на Roboflow Universe](https://universe.roboflow.com/arvind-kumar-wjygd/anpr2-syxl7)

## Как устроено

1. Клонируется форк YOLOv9 ([SkalskiP/yolov9](https://github.com/SkalskiP/yolov9)),
   в котором исправлен инференс, и скачиваются предобученные веса
   (`yolov9-c/e`, `gelan-c/e`).
2. Датасет загружается из Roboflow; при запуске `roboflow.login()` попросит
   войти в аккаунт Roboflow.
3. YOLOv9 дообучается на номерных знаках.
4. Обученная модель (`detect.py`) находит номера на тестовых изображениях.

Нужен GPU: в Colab выберите `Runtime → Change runtime type → GPU`.

## Резюме

В репозитории также лежит моё резюме:
[uglov_vladislav_cv (5) (2).pdf](<uglov_vladislav_cv (5) (2).pdf>).
