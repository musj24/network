LAB2-Vlan_interRouting

목표: ROAS와 L3 스위치를 이용해 vlan이 나뉘어져 있는 내부 pc들간의 통신을 가능하게 한다.

사용할 기술

OSPF
NAT
DHCP
ROAS


고려할 점
1. 구역은 HQ와 Branch로 나누되, 내부 PC들도 단일 네트워크가 아닌, 다중 네트워크로 분할한다.
2. 내부 PC들은 서로 통신 가능해야 하며, 외부 인터넷 (8.8.8.8)과 통신도 가능해야 한다.
3. Router와 SW간 링크는 트렁크로 구성해야 정상적인 동작이 가능함.


검증할 점
1. 내부 PC간 통신이 가능한가?
2. PC와 외부 인터넷(8.8.8.8)이 통신 가능한가?
   

트러블슈팅
1. ROAS의 가상 인터페이스에 encapsulation dot1q가 빠진다면?

[증상]
- VLAN10 PC에서 Default Gateway로 ping 실패
- VLAN20/30 정상

[확인]
- show interfaces trunk
- show ip interface brief
- show run interface g0/0.10

[원인]
- Sub-interface에 dot1q encapsulation 설정 누락

[조치]
- encapsulation dot1q 10 추가

[결과]
- VLAN10 PC 정상 통신 확인

2. L3 스위치의 ip routing이 빠진다면?


