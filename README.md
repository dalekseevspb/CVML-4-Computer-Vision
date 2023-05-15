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
Финальный вариант для Kaggle, без хода выполнения/картинок: dsu-4-cvml-4-hw-2-corr-7-kaggle-cats-vs-dogs.ipynb
Промежуточный (Colab), с ходом выполнения/картинками: AlekseevDP(DSU_4,CVML_4)_HW_2(corr)_Colab_Cats_vs_Dogs.ipynb

Датасет https://www.kaggle.com/c/dogs-vs-cats-redux-kernels-edition

- Реализовано на предобученной сети VGG16(weights='imagenet');
- Фиксируем веса предобученной НС и добавляем слои, дроп-аут для дообучения модели 
- Обучаем
- Готовим данные для отправки на Kaggle

# (#3) The Nature Conservancy Fisheries Monitoring (with Kaggle submission)
