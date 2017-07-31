---
layout: post
title:  "Project;픽시왕"
date:   2014-06-24
excerpt: "bicycle sensorometer"
tag:
- ATmega128
- Android application
- Sensor test
---
# Project; 픽시왕
<hr />
ATmega128, Android application, Sensor test<br />
Joon-hyuk Sim, Dae-jung Kim, Sang-hoon Jung<br />
Bicycle, Atmega128, LED, Android smartphone, Reed switch, Magnetic, Servo motor...<br />
30x170x120cm / 2014.06<br />

<a href="{{ site.url }}/images/fixiewang.jpg"><img src="{{ site.url }}/images/fixiewang.jpg"></a> 

<h2> Description</h2>
 <픽시왕>은 자전거 통합 센서 모듈로써 속도를 숫자가 아닌 자동차의 계기판처럼 시각적으로 보여주는 속도측정계와 자전거의 좌우 방향 전환을 스마트폰 내부의 가속센서를 이용하여 방향지시등을 하나의 모듈로써 제작하였다. 이 작품은 학부 3학년 1학기 실험과목인 로봇학 실험의 프로젝트 결과물로써 Atmel사의 펌웨어 개발 능력 향상과 실험시간에 다뤘던 다양한 센서 활용을 목표로 하였다.

<h2> System architecture</h2>

<a href="{{ site.url }}/images/fixiewang_sys.png"><img src="{{ site.url }}/images/fixiewang_sys.png"></a> 

 <픽시왕>의 시스템 구조는 위 구조도와 같이 <b>리드스위치를 활용한 서보모터 제어 부분(Speedometer)</b>과 <b>스마트폰의 가속도 센서와 블루투스를 활용한 LED 제어 부분(Turn signal lamp)</b> 으로 나뉘어진다.
 	<h3> Speedometer</h3>
 		속도 측정계는 리드스위치를 외부인터럽트에 연결하여 리드 스위치가 자석에 근접하여 작동될 때 마다 다음과 같이 속도를 계산하였다.
 		{% highlight yaml %}
 		속도=거리∕시간=(바퀴 반경(34cm)×2π)∕한바퀴 도는데 걸린 시간(lab_time(ms))
 		단위변환 (cm∕ms→km∕h)
 		213/lab_time*0.00001*3600000=213*36/lab_time(km∕h)
 		{% endhighlight %}


<h2> Additional info</h2>
<ul>
	<li>개발 기간		:     2014.04-2014.06</li>
	<li>참여 인원		:     3명</li>
	<li>담당 분야		:     안드로이드 애플리케이션 제작, 리드스위치를 이용한 서보 모터 제어</li>
	<li>개발 언어		:     C, Java</li>
	<li>주최 기관		:     광운대학교</li>
	<li>진행 사유		:     로봇학실험3 실험 프로젝트</li>
</ul>