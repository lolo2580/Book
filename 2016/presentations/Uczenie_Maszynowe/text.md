#Uczenie maszynowe - czyli jak rozwiązywać nietrywialne problemy #

##Streszczenie##

Techniki uczenia maszynowego są szeroko wykorzystywane w różnych obszarach codziennego życia. Problemy takie jak klasyfikacja czy predykcja, przy rozwiązywaniu których nie sprawdzają się tradycyjne algorytmy, mogą być z powodzeniem implementowane metodami pozwalającymi nauczyć program podejmować trafne decyzje. Python idealnie nadaje się do wykorzystania tych technik, w czym pomaga bez mała kilkadziesiąt mniej lub bardziej wyspecjalizowanych bibliotek.

##Rozwój znaczenia i metod uczenia maszynowego##

Gdy w roku 1965 na Uniwersytecie Stanforda powstawał system Dendral, nikt pewnie nie przypuszczał, że ledwie 50 lat później uczenie maszynowe (machine learning, ML) będzie techniką wszechobecną, z której korzystamy codziennie, niemal na każdym kroku.

Dendral był specjalistycznym oprogramowaniem naukowym, służącym do analizy, grupowania oraz rozpoznawania, nieznanych do tej pory człowiekowi, molekuł związków chemicznych. Uzyskane przez program rezultaty zostały opublikowane w literaturze naukowej. Było to pierwsze w historii odkrycie dokonane bezpośrednio przez komputer, a Dendral uważany jest za prekursora systemów wykorzystujących uczenie maszynowe.

Motorem napędowym dynamicznego rozwoju technik sztucznej inteligencji oraz uczenia maszynowego był wzrost ilości gromadzonych danych. Widać to dobrze na przykład w dziedzinie biologii, gdzie pod koniec XX wieku intensywnie badano sposoby pozyskiwania informacji o sekwencjach nukleotydowych genów. W roku 2003 głośno było o zakończeniu wielkiego projektu sekwencjonowania ludzkiego genomu (HGP, human genom project). Uzyskanie pierwszej sekwencji całego genomu człowieka zajęło naukowcom 13 lat i kosztowało aż 3 mld dolarów. Dziś jesteśmy w stanie zsekwencjonować cały genom w ciągu zaledwie kilku godzin, za kwotę rzędu jedynie tysiąca dolarów. Czyste, surowe dane niewiele jednak nam dają. Nie jest dla nas przecież ważna sekwencja sama w sobie, ale wynikające z niej wnioski, takie jak określenie skłonności i ryzyka zachorowania na poszczególne choroby, zidentyfikowanie oporności na niektóre leki (ważne przy planowaniu skutecznego leczenia) itp. 

Nawiasem mówiąc, koszt długotrwałego przechowywania danych sekwencyjnych bywa na tyle duży, że często bardziej opłaca się zachować próbkę DNA i w razie potrzeby ponownie przeprowadzić sekwencjonowanie  To kolejny ważny aspekt związany z „erą danych”, który, jako wykraczający poza tematykę artykułu, pominę w dalszych rozważaniach.
Duża ilość gromadzonych danych nie jest domeną jedynie biologii. Mamy obrazy medyczne, dane meteorologiczne, dane gospodarcze, dane o ruchu w sieci i szereg innych. I podobnie – bazując na tych pozornie bezużytecznych surowych danych, chcemy wyciągnąć konkretne, praktyczne wnioski.

Zastosowania algorytmów uczenia maszynowego widzimy na co dzień. Kto z nas wpisując hasło do popularnej wyszukiwarki nie zwrócił uwagi na pojawiające się sugestie? Mamy podpowiedzi w pasku przeglądarki, po witrynach oprowadzają nas wirtualni asystenci, w pisaniu tekstów pomaga autokorekta, porządek w poczcie zapewniają wykrywacze spamu, dostajemy propozycje artykułów podobnych do aktualnie czytanego, sugestie podobnych tematycznie filmów, wyselekcjonowane reklamy. Uczenie maszynowe pozwala na stworzenie szybkich i wiarygodnych prognoz pogody, wspomaga ocenę zdolności kredytowej, prognozy ekonomiczne, obecne jest w nawigacji samochodowej, grach komputerowych i wielu, wielu innych aspektach naszego życia. Do bardziej zaawansowanych problemów należą rozpoznawanie mowy, pisma odręcznego, interpretacja obrazów medycznych.

Uczenie maszynowe rozumiemy jako zdolność programu do uczenia się, do generalizacji. Algorytm konstruuje się zwykle w ten sposób, że uruchamia się program na niewielkim wycinku dostępnych danych, na podstawie których dokonuje on parametryzacji, czyli inaczej mówiąc – uczy się. Jeżeli uczenie przebiegło pomyślnie, wówczas program będzie w stanie podjąć właściwą decyzję nawet, jeżeli okażemy mu dane, z którymi nigdy wcześniej nie miał do czynienia.
Istotą problemów które rozwiązujemy metodami uczenia maszynowego są klasyfikacja oraz predykcja. Nie jest moim celem omówienie tutaj konkretnych technik, do których zaliczyć możemy m.in. sztuczne sieci neuronowe (ANN, *artificial neural networks*) będące (mocno uproszczoną) imitacją procesu uczenia zachodzącego w mózgu, maszyny wektorów nośnych (SVM, *support vector machines*), których idea polega na optymalizacji granicy decyzyjnej, ukryte modele markowa (HMM, *hidden markov models*) mające zastosowanie w analizie procesów stochastycznych czy drzewa decyzyjne (DT, *decision trees*), które dokonują klasyfikacji na podstawie odpowiednio wygenerowaniej struktury drzewiastej. W ostatnich latach furorę robi uczenie głębokie (*deep learning*), które jest swego rodzaju rozszerzeniem i udoskonaleniem trochę już odchodzącej na boczny tor idei sieci neuronowych. Do popularnych technik zaliczymy również algorytm k-średnich. Czytelników zainteresowanych głębszym wyjaśnieniem poszczególnych algorytmów odsyłam do jakże bogatej literatury, np. [3].

##Najpopularniejsze biblioteki ML##

Inspiracją do napisania tego artykułu było dla mnie znalezione w sieci zestawienie 20 bibliotek ML dla Pythona [6] uporządkowanych według dość oryginalnego kryterium popularności – wyrażało się ono liczbą commitów na githubie oraz osób biorących udział w tworzeniu biblioteki (contributors). Liczba dostępnych bibliotek jest jednak znacznie większa. Joseph Misiti w swoim repozytorium zgromadził zestawienie listujące grubo ponad 150 różnych bibliotek dla Pythona, które w jakimś stopniu są wykorzystywane w uczeniu maszynowym [5].*
Niewątpliwie najpopularniejszą biblioteką oraz de facto standardem jest **scikit-learn** (https://github.com/scikit-learn/scikit-learn) . Biblioteka ta, oparta na popularnych pakietach numerycznych i naukowych NumPy oraz SciPy, cieszy się też dużym wsparciem społeczności. Jest biblioteką ogólnego zastosowania – zawiera wiele modułów implementujących różne algorytmy oraz techniki ML. Biblioteka jest bardzo łatwa w użyciu i wydajna. Jednak za tą łatwość i mnogość zastosowań płaci się elastycznością. Trudno w scikit-learn zmodyfikować szczegółowe parametry algorytmu, dopasowując go do konkretnego problemu. Dlatego, gdy chcemy wykonywać operacje bardziej niskopoziomowe, warto sięgnąć po dedykowaną, bardziej elastyczną bibliotekę, jak np. **PyBrain** (https://github.com/pybrain/pybrain), pozwalającą skonstruować praktycznie dowolną sieć neuronową, modyfikując np. funkcje aktywacji itp. PyBrain również wykorzystuje SciPy.

Istnieją też biblioteki, które rozszerzają funkcjonalność pakietu scikit-learn, np. **Nilearn** (https://github.com/nilearn/nilearn), zawierająca funkcje szczególnie przydatne w analizie obrazów aktywności mózgu.

Ponieważ metody uczenia maszynowego wymagają zwykle obliczeń na macierzach i innych złożonych strukturach matematycznych, wiele bibliotek bazuje na specjalistycznych bibliotekach numerycznych. Wspomniany wyżej scikit-learn wymaga SciPy i NumPy. Inną biblioteką implementującą zaawansowane obliczenia numeryczne jest **Theano** (https://github.com/Theano/Theano). Theano może również być samodzielnie wykorzystywana do ML, szczególnie w implementacji sieci neuronowych oraz uczenia głębokiego. Theano implementuje również rozwiązania pozwalające efektywnie wykonywać obliczenia na procesorach graficznych (GPU). 

Wśród bibliotek bazujących na Theano warto wskazać **Pylearn2** (https://github.com/lisa-lab/pylearn2) oraz **Block** (https://github.com/mila-udem/blocks), **Keras** (https://github.com/fchollet/keras) i **Lasagne** (https://github.com/Lasagne/Lasagne).

Ciekawym pakietem jest również **Tensorflow** (https://github.com/tensorflow/tensorflow), stworzony w ramach projektu Google Brain. Implementuje wysokopoziomowy dostęp do sieci neuronowych. Do niewątpliwych zalet zaliczyć tu należy obsługę obliczeń równoległych oraz na procesorach graficznych. Biblioteka napisana jest w większości w C++, ale posiada niezbędne wiązania do Pythona.

Wśród bibliotek najłatwiej znajdziemy te wspierające sieci neuronowe czy uczenie głębokie. Nie brakuje jednak też modułów pozwalających na użycie mniej popularnych metod, np. **Pyevolve** (https://github.com/perone/Pyevolve) jest przykładem biblioteki implementującej algorytmy genetyczne. Z kolei **NuPIC** (https://github.com/numenta/nupic) implementuje metodę hierarchical temporal memory (HTM). Technika HTM architekturą przypomina sieci neuronowe, ma jednak inne podłoże biologiczne i zasadę działania.

**Nltk** (http://www.nltk.org/) jest biblioteką dedykowaną dla problemów przetwarzania języka naturalnego.

Biblioteką ogólnego przeznaczenia, bez zależności od SciPy i Theano jest **Pattern** (https://github.com/clips/pattern), dedykowana w szczególności do eksploracji witryn internetowych. Wspomnieć należy również biblioteki **H2O** (https://github.com/h2oai/h2o-3)  i **caffe** (https://github.com/BVLC/caffe).

Zwieńczeniem tej niezwykle skrótowej prezentacji niech będzie **fuel** (https://github.com/mila-udem/fuel), biblioteka zapewniająca łatwy dostęp do popularnych zbiorów danych takich jak MNIST (baza danych pisma odręcznego). CIFAR-10 (baza obrazów) czy Google's One Billion Words (beza tekstowa). Z kolei **Python Machine Learning Samples** (https://github.com/awslabs/machine-learning-samples) zawiera zbiór przykładowych aplikacji wykorzystujących ML.
 
Tabela 1. Wybrane biblioteki ML dla pythona uporządkowane wg liczby współautorów (contributors) [dane liczbowe wg stanu z 31.08.2016].
|    Biblioteka                  |    commits    |    contributors    |    github                                                 |
|--------------------------------|---------------|--------------------|-----------------------------------------------------------|
|    scikit-learn                |    21148      |    661             |    https://github.com/scikit-learn/scikit-learn           |
|    tensorflow                  |    7339       |    372             |    https://github.com/tensorflow/tensorflow               |
|    Theano                      |    23286      |    250             |    https://github.com/Theano/Theano                       |
|    keras                       |    2592       |    250             |    https://github.com/fchollet/keras                      |
|    caffe                       |    3766       |    208             |    https://github.com/BVLC/caffe                          |
|    pylearn2                    |    7100       |    116             | https://github.com/lisa-lab/pylearn2                      |
|    NuPIC                       |    5986       |    73              | https://github.com/numenta/nupic                          |
|    H2O                         |    19092      |    62              | https://github.com/h2oai/h2o-3                            |
|    lasagne                     |    1050       |    51              |    https://github.com/Lasagne/Lasagne                     |
|    blocks                      |    3175       |    48              |    https://github.com/mila-udem/blocks                    |
|    nilearn                     |    5145       |    45              |    https://github.com/nilearn/nilearn                     |
|    pybrain                     |    984        |    31              | https://github.com/pybrain/pybrain                        |
|    fuel                        |    1035       |    28              |    https://github.com/mila-udem/fuel                      |
|    pattern                     |    943        |    20              | https://github.com/clips/pattern                          |
|    fann                        |    156        |    19              |    https://github.com/libfann/fann                        |
|    machine-learning-samples    |    29         |    13              |    https://github.com/awslabs/machine-learning-samples    |
|    Pyevolve                    |    168        |    12              |    https://github.com/perone/Pyevolve                     |


##Bibliografia##

1.	Britz D., Implementing a Neural Network from Scratch in Python – An Introduction, http://www.wildml.com/2015/09/implementing-a-neural-network-from-scratch/
2.	Górecki P., Uczenie maszynowe, sztuczna inteligencja i (samo)świadomość, 2014,  http://www.tabletowo.pl/2014/11/23/uczenie-maszynowe-sztuczna-inteligencja-i-samoswiadomosc/
3.	Holehouse AS., Stanford Machine Learning , http://www.holehouse.org/mlclass/
4.	Mayo M., 7 Steps to Mastering Machine Learning With Python, 2015, http://www.kdnuggets.com/2015/11/seven-steps-machine-learning-python.html
5.	Misiti J., Awesome Machine Learning, https://github.com/josephmisiti/awesome-machine-learning#python-cv
6.	Peddibhotla G.B., Top 20 Python Machine Learning Open Source Projects, 2015, http://www.kdnuggets.com/2015/06/top-20-python-machine-learning-open-source-projects.html
7.	Python Tools for Machine Learning, 2014, https://www.cbinsights.com/blog/python-tools-machine-learning/ 
8.	Robinson S., The Best Machine Learning Libraries in Python, 2015, http://stackabuse.com/the-best-machine-learning-libraries-in-python/ 
9.	Rosebrock A., My Top 9 Favorite Python Deep Learning Libraries, 2016, https://www.pyimagesearch.com/2016/06/27/my-top-9-favorite-python-deep-learning-libraries/ 
10.	Scikit-learn. Machine Learning in Python, http://scikit-learn.org/
