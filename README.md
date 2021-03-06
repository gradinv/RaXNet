# RaXNet
Automated X-ray images analysis and rheumatoid arthritis diagnosis with deep convolutional neural networks

Система диагностики ревматоидного артрита RaXNet на основе глубоких CNN
Ревматоидный артрит (РА) – это хроническая болезнь, которая имеет аутоиммунный характер. Ее природа состоит в системном воспалении соединительной ткани, при котором 
преимущественно поражаются суставы по типу прогрессирующего эрозивно-деструктивного полиартрита. Этиология болезни неясна. Среди населения данное заболевание наблюдается
примерно у 0.5 – 1% людей. Если воспаление сохраняется на протяжение продолжительного периода времени, происходят необратимые структурные деформации суставов и костей. 
Диагностика заболевания и его стадии производится, как правило, путем анализа рентгенограмм и классификации, основанной на делении РА на стадии с использованием одной из 
скоринговых систем . Рентгенологические скоринговые методы играют важную роль в обнаружении оценки стадии развития РА, но требуют высокой квалификации врачей-ревматологов 
для определения мельчайших патологий на рентгенограммах. Указанное определяет актуальность разработки автоматизированной системы анализа рентгенологических снимков и 
диагностики РА. Известные методы автоматического рентгенологического скоринга пациентов с РА осуществляют измерения расстояния между суставами (Computer‐based measurements 
of joint space analysis using metacarpal morphometry in hand radiograph for evaluation of rheumatoid arthritis , Automatic Quantification of Joint Space Narrowing and Erosions
in Rheumatoid Arthritis ), используя такие классические методы распознавания образов, как, например, алгоритм сегментации по водоразделам. В то же время известны успешно 
проведенные научные исследования по автоматической диагностике остеоартрита с помощью глубоких сверточных нейронных сетей, показывающие точность от 66,71% до 92,8% . 
В настоящем проекте планируется разработать программный комплекс автоматизированного анализа рентгенологических снимков и диагностики РА с использованием глубоких сверточных 
нейронных сетей (Deep CNN). Общая схема разработки системы состоит из следующих этапов:
- предобработка данных (нормализация);
- сегментация изображений и выделение зон интереса (regions of interest – ROI);
- экспертная разметка данных;
- разбиение размеченных данных на тренировочные и проверочные;
- расширение (augmentation) тренировочных данных;
- обучение и оценка точности глубоких сверточных нейронных сетей, выбор лучшей архитектуры;
- комбинирование нейросетевой и классической моделей диагностики;
- получение выводов по неразмеченным (новым) данным.
В настоящей разработке имеются следующие элементы новизны и существенного отличия от ранее известных способов:
1) для определения и оценки стадии РА будет использована скоринговая система Рейтингжена. Для этого в каждой рентгенограмме кисти руки будут сегментированы 10 областей (ROI), 
по которым с помощью глубокой нейронной сети произведены оценки по шкале Рейтингжена и их свертка в интегральный критерий RAU-score; 
2) для сегментации зон интереса (ROI) будет разработана система локализации контрольных точек (landmarks) на рентгенограммах кистей рук, 
с использованием архитектуры глубоких сверточных сетей HOURGLASS, успешно примененной ранее для локализации контрольных точек коленного сустава;
3) обучение нейронных сетей будет осуществляться на собственной базе данных размеченных сегментированных снимков, с тегированием по стадии РА;
4) для анализа сегментированных областей и прогноза интегрированного показателя RAU-score будут использованы модели классификации и регрессии на основе глубоких сверточных 
нейронных сетей (в т.ч. с нуля, а также transfer learning и fine tuning предобу-ченных сверточных нейронных сетей VGG16, VGG19, ResNet50, Inception V3);
5) визуализация обнаруженных на рентгенограмме патологий и приоритизация ре-зультатов диагностики с помощью тепловых карт активации классов в глубоких сверточных 
нейронных сетях.

RaXNet
 
