# 스마트팩토리 MES 구축(Smart-factory-MES-program)


<br/>

## 프로젝트 소개

![image](https://user-images.githubusercontent.com/57824945/236276192-f89f9061-f41e-4dbf-b845-72a2d8b9a64c.png)

 이 프로젝트는 시설 내 설비와 기계에 센서들이 설치되어 데이터가 실시간으로 수집, 분석되어 공장 내 모든 상황들이 일목요연하게 보여지고고, 이를 분석해 목적된 바에 따라 스스로 제어될 수 있게 하는 스마트팩토리 프로젝트 입니다.
자동차 부품을 만들기 위한 모든 공정들을 작업자가 없이 자동화 하여 제어자 한명만 있으면 많은 라인의 큰 공정을 생산 해 내는 것이 목표입니다.

<br/>

<br/>

## 프로젝트 구조

제품은 두가지의 제품이 연동 생산 됩니다. 그 두 제품은 바코드로 구분되어지며 바코드 출력 기계와 VISION 프로그램이 TCP/IP 통신으로 연결이 되어
프로그램에서 구분지어 출력을 하고 바코드를 INDEX로 두어 데이터베이스에 생성을 합니다.

각 공정마다 **COGNEX** 사의 바코드 리더기로 제품을 확인하고 여러 공정들(밸런스검사, 성능검사, 배출검사, 압입검사, 저항검사 등등) 의 컬럼을 미리 데이터베이스에
만들어 둡니다.

Mitsubishi PLC와 VISION 프로그램이 MELSEC 통신을 통해 통신을 하고, PLC에서 각 공정마다의 값을 VISION 프로그램으로 번지값들을 정해 송출하면, VISION 프로그램에서
그 값을 확인후 알맞은 컬럼의 데이터베이스에 저장을 합니다.

<br/>

위와 별개로 자동차 부품의 밸런스 검사를 위해 밸런스 검사 VISION 장비를 통해 밸런싱 테스트를 진행합니다.

<br/>



<br/>


## 사용기술

<br/>
- C#
  <br/>
- Mitsubishi PLC와 MELSEC 통신
  <br/>
- 제브라사의 라벨 프린트와 TCP/IP 통신
  <br/>
- 생산현황 모니터와, 두대의 DATAPC와 TCP/IP 통신
  <br/>
- MYSQL 데이터 베이스


  <br/>


## 리뷰

처음으로 혼자서 자동화 라인의 통신 및 MES를 구축 해 보았습니다.
제일 처음으로는 여러가지 디바이스, 장비들과의 통신에서 어려움이 있었습니다.
각각 프로토콜이 다르고 통신 형식이 다르고 주고받는 단위들이 달라서 그것을 맞추는데 힘이 들었지만 그만큼 통신의 중요성과
배움에 있어서 좋은 프로젝트 였습니다.
그리고 직접 DB를 구축하여 원하는 곳의 측정치 등을 DB에 쌓고, 그 쌓은 데이터를 활용하여 최종적으로 모니터에 띄워줌으로써 PC, 센서간의 DB에 대해서도
배움이 있었습니다.
