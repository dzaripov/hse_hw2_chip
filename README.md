# hse_hw2_chip

[Ссылка на Colab](https://colab.research.google.com/drive/1sYPLw-8OGkCdNhdY7EEOP4NON5TrW-cB?usp=sharing)


|   |   |
|---|---|
Клеточная линия | GM12878 
Гистоновая метка | H3K36me3
ID эксперимента | [ENCSR000DRW](https://www.encodeproject.org/experiments/ENCSR000DRW/)
ID Реплики 1 | ENCFF001EXY
ID Реплики 2 | ENCFF001EXW
ID контроля | ENCFF001HID
Хромосома выравнивания | chr21
ID bed Peak | ENCFF268HMO
Версия | ENCODE3 GRCh38


## Анализ FastQC
HTML-репорты представлены ниже
Первая реплика | Вторая реплика | Контроль
--- | --- | ---
[ENCFF001EXY](https://github.com/dzaripov/hse_hw2_chip/blob/main/data/ENCFF001EXY_fastqc.html) | [ENCFF001EXW](https://github.com/dzaripov/hse_hw2_chip/blob/main/data/ENCFF001EXW_fastqc.html) | [ENCFF001HID](https://github.com/dzaripov/hse_hw2_chip/blob/main/data/ENCFF001HID_fastqc.html)

### FastQC

ENCFF001EXY | ENCFF001EXW | ENCFF001HID
--- | --- | ---
![image](https://github.com/dzaripov/hse_hw2_chip/raw/main/data/ChipSeq_ENCFF001EXY.png) | ![image](https://github.com/dzaripov/hse_hw2_chip/raw/main/data/ChipSeq_ENCFF001EXW.png) | ![image](https://github.com/dzaripov/hse_hw2_chip/raw/main/data/ChipSeq_ENCFF001HID.png)
![image](https://github.com/dzaripov/hse_hw2_chip/raw/main/data/Pbsq_ENCFF001EXY.png) | ![image](https://github.com/dzaripov/hse_hw2_chip/raw/main/data/Pbsq_ENCFF001EXW.png) | ![image](https://github.com/dzaripov/hse_hw2_chip/raw/main/data/Pbsq_ENCFF001HID.png)
![image](https://github.com/dzaripov/hse_hw2_chip/raw/main/data/Psqs_ENCFF001EXY.png) | ![image](https://github.com/dzaripov/hse_hw2_chip/raw/main/data/Psqs_ENCFF001EXW.png) | ![image](https://github.com/dzaripov/hse_hw2_chip/raw/main/data/Psqs_ENCFF001HID.png)
![image](https://github.com/dzaripov/hse_hw2_chip/raw/main/data/Pbsc_ENCFF001EXY.png) | ![image](https://github.com/dzaripov/hse_hw2_chip/raw/main/data/Pbsc_ENCFF001EXW.png) | ![image](https://github.com/dzaripov/hse_hw2_chip/raw/main/data/Pbsc_ENCFF001HID.png)
![image](https://github.com/dzaripov/hse_hw2_chip/raw/main/data/PsGCc_ENCFF001EXY.png) | ![image](https://github.com/dzaripov/hse_hw2_chip/raw/main/data/PsGCc_ENCFF001EXW.png) | ![image](https://github.com/dzaripov/hse_hw2_chip/raw/main/data/PsGCc_ENCFF001HID.png)
![image](https://github.com/dzaripov/hse_hw2_chip/raw/main/data/PbNc_ENCFF001EXY.png) | ![image](https://github.com/dzaripov/hse_hw2_chip/raw/main/data/PbNc_ENCFF001EXW.png) | ![image](https://github.com/dzaripov/hse_hw2_chip/raw/main/data/PbNc_ENCFF001HID.png)

Подрезание чтений и фильтрация не требуется, так как качество ридов довольно хорошее.


## Таблица со статистикой по выравниванию на 21 хромосому

|    | ChIP-seq    |   Количество ридов всего | Количество ридов, которые выравнились уникально   | Количество ридов, которые выравнились неуникально   | Количество ридов, которые не выравнились   |
|---:|:------------|-------------------------:|:--------------------------------------------------|:----------------------------------------------------|:-------------------------------------------|
|  0 | ENCFF001EXY |                 17706267 | 552318 (3.12%)                                    | 2621449 (14.81%)                                    | 14532500 (82.08%)                          |
|  1 | ENCFF001EXW |                 17829133 | 561950 (3.15%)                                    | 2720037 (15.26%)                                    | 14547146 (81.59%)                          |
|  2 | ENCFF001HID |                 16990693 | 556833 (3.28%)                                    | 2276730 (13.40%)                                    | 14157130 (83.32%)                          |

Процент несовпадений чтений значительно превышает 80% для всех образцов, потому что выравнивание проводилось только на одной хромосоме (а еще 21 хромосома - одна из самых маленьких по размеру), в результате чего было ограничено небольшой частью генома.

## Диаграммы Эйлера-Венна

### Пересечение пиков 1 реплики и ENCODE

1 реплика с ENCODE | ENCODE с 1 репликой
--- | ---
![image](https://github.com/dzaripov/hse_hw2_chip/raw/main/venn_results/venn1/Intervene_venn.png) | ![image](https://github.com/dzaripov/hse_hw2_chip/raw/main/venn_results/venn2/Intervene_venn.png)

### Пересечение пиков 2 реплики и ENCODE

2 реплика с ENCODE | ENCODE и 2 репликой
--- | ---
![image](https://github.com/dzaripov/hse_hw2_chip/raw/main/venn_results/venn3/Intervene_venn.png) | ![image](https://github.com/dzaripov/hse_hw2_chip/raw/main/venn_results/venn4/Intervene_venn.png)


Из-за выравнивания на одну хромосому количество пиков небольшое, что приводит к небольшому количеству пересечений. Количество пересечений, полученных при сравнении наших пиков с пиками в базе данных ENCODE, и при обратном сравнении, различается, так как порядок сравнения влияет на результат. Диаграмма Венна показывает, что наши пики составляют меньшую долю от общего количества пиков, поскольку выравнивание производилось только на одну хромосому, в то время как в базе данных ENCODE выравнивание было проведено на всех хромосомах.