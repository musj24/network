5. 트러블슈팅
- HQ_router에서 default route를 전파하지 않으면?
문제 발생 : Branch 내부의 호스트는 외부 인터넷과 접속이 불가능하다
  
- passive-interface를 잘못된 인터페이스에 적용한다면?
문제 발생 : OSPF 인접성 형성이 불가능해지고, 통신이 끊긴다.
  
- DHCP relay를 누락한다면?
문제 발생 : 해당 라우터의 내부 PC는 주소를 받을수 없다
  
- static NAT와 PAT 주소가 충돌한다면?
문제 발생 : 당장 inside에서 outside로 향하는 트래픽은 여전히 PAT되어 인터넷 연결이 가능할수도 있다.
            하지만 static nat가 PAT 주소를 단일장비 (내부 서버 등)에 매핑해버리면, 외부에서 들어오는 트래픽 다수가 static 매핑된 장비에 들어갈수 있음.
