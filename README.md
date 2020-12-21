201602534 중국언어문화전공 이윤호

# 무한도전 데이터 분석 프로젝트
## 선 한줄요약
친구 놀려먹는게 세상에서 제일 재미있다.

# 1. 프로젝트 소개
## 1.1 배경 및 목적
무한도전은 2018.03.31에 이미 종영한 프로그램임에도 불구하고 무한도전의 기존 방송본을 업로드한 유투브 동영상들이 기록적인 조회수를 기록하고 있으며 여전히 많은 이들에게 좋은 반응을 이끌어내고 있습니다.

![1](https://user-images.githubusercontent.com/74258352/101723485-b862a780-3aef-11eb-8cfd-9ad170ca421f.png)

무한도전 출연진들의 대화가 어떠한 부분에서 많은 시청자들에게 웃음과 재미를 주었는지를 언어적으로 분석 함으로서, 한 때 한국의 국민 예능이었던 무한도전을 통해 한국에서 예능방송으로 대성하기 위해 알아야 할 시청자들의 웃음 코드 혹은 재미있는 말하기 그 자체에 대해 깊이있는 이해를 하는 것이 프로젝트의 목적입니다.

## 1.2 분석대상 선정
본 프로젝트는 언어분석을 메인으로 하는 프로젝트입니다.
무한도전도 여러 사람이 모여 진행하는 예능방송인 만큼 대화를 통한 의사소통으로 극적인 상황을 이끌어내고 재미를 유발하지만, 무한도전 대부분의 에피소드가 언어와 함께 비언어적인 요소(몸개그, 추격전, 몰래카메라 등 시각적인 요소나 상황을 이용)도 같이 활용하여 재미를 유발하는 경우가 잦았습니다. 

![2](https://user-images.githubusercontent.com/74258352/101724229-6cb0fd80-3af1-11eb-9406-656ad1a9ea6c.png)

이 경우 언어분석을 진행하기엔 부적절하기에 무한도전의 여러 회차들을 비교분석하기 보다는 대화 위주로만 진행되는 에피소드를 따로 선정하여 분석하기로 하였습니다.

1. “법정공방 죄와 길” 에피소드와 2. “국민의원특집” 에피소드가 이에 해당합니다. 죄와 길 에피소드의 경우 법정재판이라는 상황을 가정하고 있기에 에피소드 전체가 변론이나 증언 등의 대화로 이루어져 있으며 무한도전의 역대 방송분들 중에서도 가장 호평인 것들 중 하나입니다. 국민의원특집의 경우도 무한도전 시청자들과 국회의원간의 청문회와 비슷한 형식이며 마찬가지로 대화 위주로 진행되지만 상대적으로 시청률이 낮고 혹평인 에피소드들 중 하나입니다. 아래는 두 에피소드의 시청률이며 방영기간상의 차이가 길기 때문에 단순비교하기 어려우나 이를 감안하더라도 시청률 차이가 크다는 사실을 알 수 있다. 왼쪽부터 전국 시청률, 수도권 시청률 순이다.

![image](https://user-images.githubusercontent.com/74258352/102775181-b510cb00-43cf-11eb-834c-2aee20093a99.png)
![image](https://user-images.githubusercontent.com/74258352/102775241-c9ed5e80-43cf-11eb-818c-91546f6894f2.png)

# 2. 데이터 수집 및 분석
## 2.1 데이터 수집 과정
본 프로젝트의 바탕이 되는 데이터스키마는 무한도전 방영분 내 등장하는 모든 발화자들의 발화 대사 전체를 대상으로 합니다. 데이터 수집은 방영분 전체를 시청하고 대사를 직접 받아적는 방식으로 진행되었다. 아래는 죄와 길 에피소드의 데이터스키마이다.

![image](https://user-images.githubusercontent.com/74258352/102775261-d40f5d00-43cf-11eb-8601-d06ed8dc649e.png)

본 프로젝트의 핵심이라고 할 수 있는 "재미있는 방영분"인 죄와 길 에피소드데의 경우, 시각화와 추가 분석을 진행하기 위한 항목을 추가하여 데이터를 수집하였습니다. 발화자와 대사 본문, 그리고 그 대상이 되는 대상자를 분류하였으며 각 본문마다 발화의 상황을 분류하여 제시하였습니다. 상황은 논박, 대화, 말다툼, 말실수, 모함, 발뺌, 변론, 비난, 인신공격, 장난, 재판, 조롱, 진술, 진행, 취재, 판결, 폭로의 총 16가지이며 본 프로젝트에서는 결국 쓰이지 않았지만 화면상에 출력되는 자막이나 해당 발화가 어떻게 이루어졌는지 이해를 돕기 위한 설명 항목도 작성하였다.
이와 달리 국민의원 에피소드의 경우 상대적으로 "재미없는 방영분"이며 죄와 길 에피소드와의 언어분석 비교를 위해 진행하는 것이기 때문에 발화자와 그 본문  이외는 따로 데이터 수집하지 않았습니다. 아래는 국민의원 에피소드의 데이터 스키마이다.

![image](https://user-images.githubusercontent.com/74258352/102775279-df628880-43cf-11eb-9529-66df6b978884.png)

그리하여 죄와 길 1743건, 국민의원 1172건을 합쳐서 총 2915건의 데이터를 수집하였다.

## 2.2 데이터 정제 과정
이렇게 엑셀로 수집완료한 데이터를 Colab의 알고리즘을 이용하여 형태소별로 품사를 분류하였고, 분류가 완료된 상태의 csv파일을 다운로드하였습니다. 알고리즘의 경우 해당 강의에서 제공된 것이며 아래는 그 캡처화면입니다.

![image](https://user-images.githubusercontent.com/74258352/102775303-ed180e00-43cf-11eb-9427-98bfd9eaf444.png)

알고리즘의 경우 Colab과 연동하여 Github에 업로드 되어있으며 알고리즘 작동 절차는 이를 통해 확인할 수 있습니다. 그렇게 얻은 csv파일을 텍스트파일로 열어 엑셀에 복사한 뒤 각 형태소별 등장 빈도를 셀에 추가하여 피벗테이블로 빈도분석을 진행하였습니다.

## 2.3 언어분석
발화 횟수 자체가 적은 발화자의 경우 상대빈도가 높아져서 내림차순 분석에 방해가 됐기에 본 분석에서는 제외합니다. 아래는 이해를 돕기 위한 캡처본이며 안내인의 상대빈도가 과하게 높다는 사실을 알 수 있습니다.

![image](https://user-images.githubusercontent.com/74258352/102776576-4ed97780-43d2-11eb-9f9d-523404f9a2b4.png)

먼저 아래는 죄와 길 에피소드에서 사용된 명사이다.

![image](https://user-images.githubusercontent.com/74258352/102776608-5ef15700-43d2-11eb-9252-762fe97b44c8.png)

명사분석을 통해 대화가 어떤 주제로 이루어졌는지 대략적으로 파악할 수 있습니다. 죄와 길 에피소드의 경우 길성준의 소변방뇨 사건에 대해 변호사를 대동하여 법정 재판을 벌이는 중이라는 사실을 알 수 있습니다. 아래는 국민의원 에피소드에 사용된 명사입니다.

![image](https://user-images.githubusercontent.com/74258352/102776651-77617180-43d2-11eb-8bdf-3ac7115ef107.png)

국민의원의 경우 국민(정확히는 그러한 역할을 맡은 무한도전의 시청자들)이 원하는 법안의 발의에 대하여 국회의원과 함께 의견을 나누고 있음을 알 수 있습니다. 이를 통해 알 수 있는 사실은 두 에피소드가 모두 공통적으로 “법”과 관련한 주제를 다루고 있다는 것이며 동시에 두 에피소드는 모두 근본적으로 예능“방송”의 방송분에 해당합니다. 여기서 두 명사 “법”과 “방송”의 빈도수를 찾아보고 비교하기로 하였습니다. 아래는 그 캡처입니다.

![image](https://user-images.githubusercontent.com/74258352/102776702-92cc7c80-43d2-11eb-9fcc-0384aff19e09.png)
![image](https://user-images.githubusercontent.com/74258352/102776725-9cee7b00-43d2-11eb-9df3-639446498a7d.png)

죄와 길 에피소드의 경우 “방송”이라는 명사가 상당히 높은 빈도로 합계 6%가 사용되었습니다. 반면 “법”이라는 명사는 0.18%의 사용에 그쳤습니다. 다음은 국민의원 에피소드에서 사용된 명사 “법”과 “방송”입니다.

![image](https://user-images.githubusercontent.com/74258352/102776754-ad9ef100-43d2-11eb-8e64-4faba8cb5e8c.png)
![image](https://user-images.githubusercontent.com/74258352/102776811-c0b1c100-43d2-11eb-93b8-f1b0de580c1b.png)

국민의원 에피소드에서는 반대로 “법”단어의 빈도수가 4.5%로 높고 “방송”단어의 빈도수가 0.17%로 낮음을 알 수 있습니다. 뿐만 아니라 본 에피소드에서는 법안, 금지법, 법률 등 관련한 단어의 사용이 많았기에 법 자체에 대한 언급은 4.5% 이상일 것입니다.

이러한 차이는 두 에피소드가 각자 어디에 집중하였는지를 단적으로 보여줍니다. 죄와 길에서는 그것이 법정공방 상황일지언정 시청자에게 재미를 목적으로 송출되는 “방송”임을 멤버들이 강하게 의식하고 있었던 반면 국민의원에서는 모두가 “법”이라는 주제 자체에 더욱 집중했음을 알 수 있습니다. 무한도전은 법 지식을 알기 위한 다큐가 아닌 예능 방송이며 시청자들은 결국 재미를 위해 무한도전을 시청합니다. 시청률을 통해 수익을 창출하는 무한도전으로서는 그러한 본분에 충실해야 할 것이며, 그러한 본분에 더욱 충실했던 것은 죄와 길 에피소드라는 사실을 알 수 있었습니다.

다음은 각 에피소드에서 사용된 언어부호이다. 위가 국민의원 에피소드, 아래가 죄와 길 에피소드이다.

![image](https://user-images.githubusercontent.com/74258352/102776941-f9519a80-43d2-11eb-99e8-7f240e3310cd.png)
![image](https://user-images.githubusercontent.com/74258352/102776962-01a9d580-43d3-11eb-9af0-2b65cb891d16.png)

죄와 길 에피소드에서는 “?”가 주로 쓰여 상대방에게 질문을 던져 대답을 유도하는 형식으로 발화를 끝마친 경우가 많았습니다. 이는 서로 오고가는 대화가 끊김이 없이 계속해서 이어짐을 의미합니다. 반면 국민의원 에피소드에서는 “.”이 주로 쓰여 자신의 말을 완결된 하나의 문장으로 끝내는 경우가 많았습니다.

또한 공통적으로 “…”가 많이 사용되었습니다. 특히 죄와길 에피소드에서는 빈도가 약 37%에 달합니다. 아래는 실제 발화문입니다.

![image](https://user-images.githubusercontent.com/74258352/102776991-11291e80-43d3-11eb-8417-da847462ab55.png)
![image](https://user-images.githubusercontent.com/74258352/102777010-19815980-43d3-11eb-98d7-ef497a0b4ba8.png)
![image](https://user-images.githubusercontent.com/74258352/102777021-200fd100-43d3-11eb-97c4-56f08cdcb5aa.png)
![image](https://user-images.githubusercontent.com/74258352/102777035-269e4880-43d3-11eb-9263-6cbdfdbf2f17.png)

죄와 길에서 “…”의 비율이 높은 이유는 발화자가 말을 하는 도중에 제3자가 자꾸만 끼어들어 말이 도중에 끊겼기 때문입니다. 여러 명의 발화자가 동시다발적으로 자기 할 말만 하고 듣지는 않는, 다소 난장판스러운 분위기에서 방송이 촬영되었기 때문에 말이 여러 번 끊기게 되어 “…”의 비율이 굉장히 높아졌습니다. 다음은 국민의원 에피소드의 발화문입니다.

![image](https://user-images.githubusercontent.com/74258352/102777056-3027b080-43d3-11eb-8371-1193589ceafe.png)

국민의원에서 “…”은 발화자가 말의 맺음을 확실치 않게 하는 경우가 대부분이었으며 발화 중간에 누군가가 끼어드는 경우는 거의 없었습니다.
이를 통해 도출해낸 결론은 다음과 같습니다. 죄와 길 에피소드에서는 멤버들 모두가 끊임없이 서로에게 질문을 던짐으로서 반응과 대답을 이끌어내고 여러 명의 발화자들이 서로 뒤엉켜 소란을 피우는 등 비교적 활발한 의사소통이 이뤄졌습니다. 반면 국민의원 에피소드에서는 비교적 일방적인 의사소통 형태가 자주 등장했고 한명의 발화가 끝나기 전까지 누군가가 따로 끼어들지 않는 정적이고 정돈된 대화가 이뤄졌습니다.

추가로 2.1 데이터 수집 과정에서 설명하였듯 죄와 길 에피소드의 경우 어떤 대화에서 모두가 크게 웃었는지, 발화별 발화상황은 어떠한지를 추가적으로 기록하였기에 이를 바탕으로 분석한 내용을 설명하겠습니다. 다음은 발화자별 웃음의 상대빈도입니다.

![image](https://user-images.githubusercontent.com/74258352/102777125-564d5080-43d3-11eb-8cdc-9740371cd401.png)

상대빈도를 기준으로 내림차순 정리한 것이며, 전체 셀은 전체 발화수와 같습니다. 발화자 중에서도 박명수는 유재석 다음으로 가장 발화수가 많으면서 동시에 가장 많은 웃음을 준 발화자입니다. 다음은 이를 바탕으로 박명수의 발화 유형을 시각화한 그래프이다.

![image](https://user-images.githubusercontent.com/74258352/102777161-649b6c80-43d3-11eb-8068-b4ed7f653f30.png)

변론이나 진술, 재판상황에서의 발화보다는 비난, 장난, 모함, 말다툼, 조롱하는 발화의 수가 압도적으로 많다는 것을 확인하였습니다. 가장 많은 웃음을 준 발화자가 내뱉은 말이 대부분 공격적인 말하기라는 사실을 알 수 있었습니다.

다시 상황별로 웃음의 상대빈도를 피벗테이블하여 나타내 보았습니다.

![image](https://user-images.githubusercontent.com/74258352/102777185-6d8c3e00-43d3-11eb-93cf-6e9cf513321a.png)

마찬가지로 상대빈도를 기준으로 내림차순한 것이며, 빨간색 글씨는 공격적인 말하기이고 파란색 글씨는 일반적인 상황에서의 말하기입니다. 색깔별로 위 아래로 구분됨을 알 수 있습니다. 아래는 해당 피벗테이블을 버블과 다이어그램으로 시각화한 것입니다.

![image](https://user-images.githubusercontent.com/74258352/102777213-7ed54a80-43d3-11eb-9238-601048f7b0df.png)
![image](https://user-images.githubusercontent.com/74258352/102777248-8bf23980-43d3-11eb-8e7a-646a092a13ac.png)

극단적으로 말해서 무한도전에서 나온 웃음은 거의 모두 공격적인 말하기 상황 하에서 발생하였다고 볼 수 있습니다.

# 3. 프로젝트 결론

## 3.1 선 4줄요약
무한도전을 통해 알아본, 재미있는 말하기를 위한 4가지 조건
1.	편안한 분위기에서 대화할 것. 
2.	서로간에 대화를 끊임없이 활발하게 주고받을 것. (이를 유도하기 위해 질문을 던진다)
3.	예의차리기 보다는 공격적으로 말할 것.
4.	너무 진지해지지 않고 장난스러운 태도로 임할 것.

## 3.2 결론 설명
죄와 길 에피소드는 국민의원 에피소드와 달리 예능이라는 프로그램 특성에 굉장히 잘 부합하였습니다. 주제 자체는 명예훼손에 관한 길성준의 유재석 고소재판이며 분위기가 진지해진다면 굉장히 무거울 수 있는 주제이나 멤버들은 법보다는 방송이라는 키워드에 집중하였습니다. 실제로도 죄와 길 에피소드에서는 모두가 장난스러운 태도로 일관하며 웃음과 재미에 집중하는 반면 국민의원 에피소드에서는 모두가 주제에 대해 굉장히 진지하게 이야기합니다. 서로 각자 자기 할 말만 하는 난장판스러운 분위기도 의사소통 자체에는 굉장히 큰 장애물이었겠지만 보는 시청자에게 웃음을 주는데는 효과적이었습니다. 
여기서 중요한 것은 언어분석을 두고 보았을 때 웃음을 주는 것은 ‘공격적인 말하기’라는 것입니다. 다만 단순히 공격적으로 말한다고 해서 전부 재미있는 것은 아니며 이를 뒷받침하는 것이 바로 장난스러운 태도와 난장판스러운 분위기입니다. 앞선 분석 결과에서 보았듯 박명수와 유재석이 국민의원 에피소드의 진지한 분위기에서 공격적으로 발화하지 않은 것은 그렇게 해도 재미가 없기 때문에, 오히려 역효과이기 때문이라고 이해하는 것이 합리적입니다. 실제로도 누군가로부터 진지한 비난이나 모함, 인신공격을 들으면 그것은 더 이상 재미가 아니라 언어폭력입니다. 편안한 분위기가 뒷받침되는 상황 하에서 장난치듯 내뱉는 공격적인 말하기가 가장 큰 재미를 줄 수 있다는 것입니다.
이는 비단 무한도전 뿐만이 아니라 대화 전반에 적용되는 것이기도 합니다. 당연히 엄숙한 분위기에서 진행되는 청문회보다는 친구끼리 편안하게 웃고 떠드는 것이 더 재미있습니다. 앞에서 제시한 선 4줄요약은 이러한 분석 결과를 바탕으로 제시하였습니다.

그리고 이러한 원칙들은 무한도전이 재밌기 위한 것에서 그치지 않고 일상생활에도 적용할 수 있다.

## 마치며
대략적인 핵심들은 모두 설명하였으나 일부 간추린 것이 있기에 이를 확인하고 싶으신 분은 본 Github 상에 업로드 되어있는 보고서를 확인하여 주시면 감사하겠습니다. 프로젝트에 사용된 모든 자료와 결과물은 Github 상에 업로드 하였습니다. 읽어주셔서 감사합니다.
