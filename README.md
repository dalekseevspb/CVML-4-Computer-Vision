# CVML-4 (Computer Vision @ TensorFlow, Компьютерное зрение с использованием фреймворка TensorFlow)

# (#1) Digit Recognizer_MNIST 
Обязательное условие: Без использования нейронных сетей!
Поэтому было реализовано через OpenCV (расчет гистограмм градиентов с помощью оператора Собеля) и классификатор ExtraTreesClassifier

Датасет MNIST https://www.kaggle.com/c/digit-recognizer

- Вычисляем X и Y составляющие градиента с помощью оператора Собеля
- Вычисляем угол и длину вектора градиента
- Вычисляем гистограммы градиентов
- Нормируем вектор гистограммы
- В качестве модели для классификации используем усовершенствованный алогоритм случайного леса ExtraTreesClassifier
- Вычисляем центроиды каждого из 10 классов
- Визуализируем предсказания


# (#2) Cats vs Dogs (with Kaggle submission): 
# Классификация "Cats vs Dogs" (на kaggle-датасете) на предобученной VGG16(ImageNet) с файн-тюнингом; 
Финальный вариант для Kaggle, без хода выполнения/картинок: dsu-4-cvml-4-hw-2-corr-7-kaggle-cats-vs-dogs.ipynb

Промежуточный (Colab), с ходом выполнения/картинками: AlekseevDP(DSU_4,CVML_4)_HW_2(corr)_Colab_Cats_vs_Dogs.ipynb

Датасет https://www.kaggle.com/c/dogs-vs-cats-redux-kernels-edition

- Реализовано на предобученной сети VGG16(weights='imagenet');
- Фиксируем веса предобученной НС и добавляем слои, дроп-аут для дообучения модели 
- Дообучаем
- Готовим данные для отправки на Kaggle (submission)

# (#3) The Nature Conservancy Fisheries Monitoring (with Kaggle submission) 
# Детекция и многоклассовая классификация рыб на аэрофотографиях рыболовецких/браконьерских судов (на kaggle-датасете "The Nature Conservancy Fisheries Monitoring") на предобученной VGG16(ImageNet) с файн-тюнингом.
Финальный вариант для Kaggle, без хода выполнения/картинок: FINAL_alekseevdp-dsu-4-cvml-4-hw-3-fisheries-kaggle (3).ipynb

Промежуточный (Colab), с ходом выполнения/картинками: AlekseevDP(DSU_4,CVML_4)_HW_3_fisheries_monitoring_ver17.ipynb

Датасет https://www.kaggle.com/c/the-nature-conservancy-fisheries-monitoring

- предварительно файлы с описанием разметки (*_labels.json) должны быть загружены в каталог /boxes
- зафиксируем перечень классов, чтобы при загрузке разметки (json) нумерация классов была всегда одинакова (не сбивалась)
- Легенда классификации рыб будет выглядеть так:
    - class 0: alb - Albacore tuna 
    - class 1: yft - Yellowfin tuna
    - class 2: bet - Bigeye tuna
    - class 3: shark - Sharks
    - class 4: dol - Dolphinfish (Mahi Mahi)
    - class 5: lag - Opah, Moonfish (Lamprus Guttatus)

    Остальные классы - без разметки:
    - nof - No Fishes (на фото нет никаких рыб)
    - oth - Other Fishes (на фото другие рыбы, не относящиеся ни к одному из вышеперечисленных классов)

- загружаем предобученную vgg16.VGG16(weights='imagenet'), дообучаем последние 5 слоев
  
  Добавлено 6 выходов для классификации детекции 6-и классов (alb, bet, dol, lag, shark, yft).
  
  Вероятности классов 'Other Fishes' и 'No Fishes' возьмем из примера (sample_submission), они будут константами (не входят в выходы НС):
  - Oth: 0.079142
  - NoF: 0.123081

  Итого получилось 11 выходов: 
  - 6 классов (вероятности каждого из классов, рассчитанные по функции sоftmax)
  - 2 координаты x,y верхнего левого угла распознанного изображения
  - 2 величины смещения (высота, ширина) от координат верхнего левого угла распознанного изображения
  - 1 вероятность наличия распознанного изображения на картинке (по функции сигмоиды)

- Готовим данные для отправки на Kaggle (submission).
