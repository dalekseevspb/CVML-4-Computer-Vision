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


HW #2_Cats vs Dogs (with Kaggle submission)

HW #3_The Nature Conservancy Fisheries Monitoring (with Kaggle submission)
