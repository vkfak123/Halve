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

<iframe width="640" height="360" src="https://www.youtube.com/watch?v=KKfwBAmzpp8" frameborder="0" allowfullscreen></iframe>

<h2> Description</h2>
 <픽시왕>은 자전거 통합 센서 모듈로써 속도를 숫자가 아닌 자동차의 계기판처럼 시각적으로 보여주는 속도측정계와 자전거의 좌우 방향 전환을 스마트폰 내부의 가속센서를 이용하여 방향지시등을 하나의 모듈로써 제작하였다. 이 작품은 학부 3학년 1학기 실험과목인 로봇학 실험의 프로젝트 결과물로써 Atmel사의 펌웨어 개발 능력 향상과 실험시간에 다뤘던 다양한 센서 활용을 목표로 하였다.

<h2> System architecture</h2>

<a href="{{ site.url }}/images/fixiewang_sys.png"><img src="{{ site.url }}/images/fixiewang_sys.png"></a> 

 <픽시왕>의 시스템 구조는 위 구조도와 같이 <b>리드스위치를 활용한 서보모터 제어 부분(Speedometer)</b>과 <b>스마트폰의 가속도 센서와 블루투스를 활용한 LED 제어 부분(Turn signal lamp)</b> 으로 나뉘어진다.
 	<h3> [Speedometer]</h3>
 		속도 측정계는 리드스위치를 외부인터럽트에 연결하여 리드 스위치가 자석에 근접하여 작동될 때 마다 다음과 같이 속도를 계산하였다.
{% highlight yaml %}
속도=거리∕시간=(바퀴 반경(34cm)×2π)∕한바퀴 도는데 걸린 시간(lab_time(ms))
단위변환 (cm∕ms→km∕h)
213/lab_timex0.00001x3600000=213x36/lab_time(km∕h)
{% endhighlight %}
		Timer/Counter 0번을 이용해 20ms마다 서보모터를 동작을, Timer/Counter 1번으로 1ms마다 시간을 재서 한바퀴 돌았을 때 걸린 시간을 측정하였고 Timer/Counter 2번으로 40ms마다 외부인터럽트에서 계산한 속도를 가지고 시간을 계산하는 함수를 수행하도록 하였다. 속도에 6을 곱해 6° 당 1km/h로 계산하여 속도의 범위를 0~30km/h로 설정해 주었습니다. 서보모터의 시간폭을 계산하고(PWM) 받아온 속도에 따라 서보모터의 각을 정해주도록 하였다.
	<h3> [Turn signal lamp]</h3>
		 방향지시등 부분으로는 내부인터럽트를 사용하여 블루투스 통신을 하였다. 안드로이드 스마트폰 내부의 가속센서 값을 받아와 지정한 character 값을 전송하여 해당 값에 맵핑된 값에 따라 좌/우 방향지시등이 켜지도록 펌웨어를 프로그래밍 하였다


<h2> Additional info</h2>
<ul>
	<li>개발 기간		:     2014.04-2014.06</li>
	<li>참여 인원		:     3명</li>
	<li>담당 분야		:     안드로이드 애플리케이션 제작, 리드스위치를 이용한 서보 모터 제어</li>
	<li>개발 언어		:     C, Java</li>
	<li>주최 기관		:     광운대학교</li>
	<li>진행 사유		:     로봇학실험3 실험 프로젝트</li>
</ul>