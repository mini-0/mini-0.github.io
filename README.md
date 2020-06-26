# 유전 알고리즘
: Holland에 의해 처음 개발된 알고리즘으로 자연의 진화 원리를 알고리즘 형태로 모방하였다.
기본적으로 선택 및 재생산, 교배, 돌연변이로 이루어 진다.
유전 알고리즘에는 순차적 주밍 유전자 알고리즘이란 것이 있는데, 이는 유전 알고리즘의 안정성을 완화한 알고리즘으로
탐색 공간을 줄여 탐색 효율을 향상 시켜준다.  
  
Fig. 1은 이 알고리즘의 대략적인 순서도를 나타낸다. 여기서 X<sub>1opt</sub>는 100세대 후의 최적 개체, 
X<sub>10kopt</sub>는 100*k세대 후의 최적 개체, α는 주밍 인자, N<sub>zoom</sub>은 주밍 횟수이다. 
먼저, 초기 집단을 생성 후 마이크로 유전 알고리즘을 실행한다.(마이크로 유전 알고리즘을 예시로 들었다.)
100세대로 가정하고 본 세대가 진행된 후, 최적의 적합도를 나타내는 개체 X<sub>1opt</sub>를 선정한다. 
엘리트 전략을 사용하여 최적의 개체는 다음 세대에도 유지된다.
또한 이 개체를 중심으로 탐색 영역을 X<sub>kopt</sub> - α<sup>k</sup>/2 , X<sub>kopt</sub> + α<sup>k</sup>/2 로 좁힌다.
위 과정을 해가 수렵할 때까지 반복 진행한다.  



최종신뢰도(P<sup>GA</sup><sub>final</sub>)는 주밍 인자와 주밍 구간에 떨어지는 개체수를 설계 변수로 한다.  
(1) P<sup>GA</sup><sub>final</sub> = [1 - (1 - α<sup>N<sub>uar</sub></sup> * β<sub>avg</sub>)<sup>N<sub>sp</sub></sup>  
이 식에 포함된 약어 설명을 덧붙이겠다.  
P<sup>GA</sup><sub>final</sub> : reliability (0.0 ~ 1.0)  
α : zooming factor  
N<sub>uar</sub></sup> : maximum number of variables  
β<sub>avg</sub> : improvement factor  
N<sub>sp</sub> : number of function evaluations of sub -generations in a zooming  
  
먼저, 개체수가 등비급수적으로 감소한다고 가정, 주밍 구간에 떨어지는 총 개체수(a<sub>0</sub>)는 식 (2)와 같다. a<sub>1</sub>은
주밍 전 떨어지는 개체수, a<sub>1</sub>r은 한번 주밍 후 떨어지는 개체수이다.  
(2) a<sub>0</sub> = Σ a<sub>1</sub> + a<sub>1</sub>r + a<sub>1</sub>r<sup>2</sup> + ...  
(3) F(α , r) = [1 - (1 - α<sup>N<sub>uar</sub></sup> * β<sub>avg</sub>) <sup>a<sub>0</sub>/(1+r+...)</sup>][1 - (1 - α<sup>N<sub>uar</sub></sup> * β<sub>avg</sub>) <sup>a<sub>0</sub>/(1+r+...) * r</sup>]  
위의 식은 정밀한 해를 찾을 때까지 주밍 횟수만큼 나열한다. 따라서 목적함수는 다음과 같이 정식화된다.  
(4) Maximize F(α , r)  

설계변수가 2개인 경우에 적용해보자.  

Shubert  




파라미터 최적화를 수행하면, N<sub>zoom</sub> = 6일 경우, α = 0.047이고, r = 0.95이다. 
Fig. 3은 위 함수에 대해서 주밍 인자 α의 변화에 따른 목적 함수의 추이이다. 최적치를 나타낸 α의 범위는 0.02~0.08 사이이며, 
최적화 후 α의 값이 이 범위에 포함된다.
