# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #5 выполнил(а):
- Темербаев Константин Валерьевич
- РИ230949

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | * | 20 |
| Задание 3 | * | 20 |

Работу проверили:



Структура отчета

- Данные о работе: название работы, фио, группа, выполненные задания.
- Цель работы.
- Задание 1.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 2.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 3.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).

## Цель работы
познакомиться с программными средствами для создания системы машинного обучения и ее интеграции в Unity.

## Задание 1
### Найдите внутри C# скрипта “коэффициент корреляции ” и сделать выводы о том, как он влияет на обучение модели.

forceMultiplier = 10 - коэфициент кореляции. Благодаря нему расчитывается сила передвижения сферы

```c#
///forceMultiplier = 10 - коэфициент кореляции
public float forceMultiplier = 10;
public override void OnActionReceived(ActionBuffers actionBuffers)
{
    Vector3 controlSignal = Vector3.zero;
    controlSignal.x = actionBuffers.ContinuousActions[0];
    controlSignal.z = actionBuffers.ContinuousActions[1];
    rBody.AddForce(controlSignal * forceMultiplier);

    float distanceToTarget = Vector3.Distance(this.transform.localPosition, Target.localPosition);

    if(distanceToTarget < 1.42f)
    {
        SetReward(1.0f);
        EndEpisode();
    }
    else if (this.transform.localPosition.y < 0)
    {
        EndEpisode();
    }
}
```

## Задание 2
### Изменить параметры файла yaml-агента и определить какие параметры и как влияют на обучение модели. Привести описание не менее трех параметров.

![image](https://github.com/user-attachments/assets/9fc7cc01-cf18-4263-bb7d-dd85ee0c2290)

## Задание 3
### Приведите примеры, для каких игровых задачи и ситуаций могут использоваться примеры 1 и 2 с ML-Agent’ом. В каких случаях проще использовать ML-агент, а не писать программную реализацию решения?

Превый пример можно использовать в рандомном спавне энитити(которые могут быть полезными)/ врагов в определённой области/ нпс на локациях
Второй пример может использоваться для оптимизированного передвижения юнитов (лучше использовать ML-агент)
