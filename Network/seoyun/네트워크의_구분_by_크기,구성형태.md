## 네트워크란?
**네트워크**란 **노드(node)와 링크(link)가 서로 연결되어 있거나 연결되어 있지 않은 집합체**를 의미한다.  
여기서 **노드**란 **서버, 라우터, 스위치 등 네트워크 장치**를 의미하고 **링크**는 **유선 또는 무선**을 의미한다.  
네트워크는 규모에 따라 LAN, MAN, WAN으로 나눌 수 있고, 구성 형태에 따라 다양한 토폴로지로 나눌 수 있다.  
</br>
## 처리량과 지연시간
좋은 네트워크의 조건
- 많은 처리량을 처리
- 지연 시간이 짧음
- 장애 빈도가 적음
- 좋은 보안을 갖춤

### 처리량
**처리량(throughput)**: 링크를 통해 전달되는 단위 시간당 데이터양(단위: bps(bit per second)) 
<img src="https://user-images.githubusercontent.com/91110192/197130510-3a527ba3-a22e-4289-90fe-eaead56ca97c.png" width="30%">  
_대역폭: 주어진 시간 동안 네트워크 연결을 통해 흐를 수 있는 최대 비트 수  
트래픽: 네트워크 장치에 일정시간 내에 흐르는 데이터 양_

### 지연 시간
**지연 시간(latency)**: 요청이 처리되는 시간 즉, 어떤 메시지가 두 장치 사이를 왕복하는 데 걸린 시간
</br>
## 네트워크 토폴로지와 병목현상
### 네트워크 토폴로지 <- 네트워크를 구성형태에 따라
**네트워크 토폴로지(network topology)**: 노드와 링크가 어떻게 배치되어 있는지에 대한 방식이자 연결 형태로, 네트워크를 설계할 때 고려됨.
1. 트리(tree) 토폴로지(계층형 트폴로지): 트리 형태로 배치된 네트워크 구성
<img src = "https://s3.us-west-2.amazonaws.com/secure.notion-static.com/3cad75dd-9406-4847-a273-10fa9a46f8aa/KakaoTalk_Photo_2022-10-21-15-58-23_001.jpeg?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20221021%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20221021T070123Z&X-Amz-Expires=86400&X-Amz-Signature=3fc4ae6b23ca9d5a5a2c2c4834741afdce79af5ed65132e46f4889eeab9ea5da&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22KakaoTalk_Photo_2022-10-21-15-58-23%2520001.jpeg%22&x-id=GetObject" width="60%">  
장점: 노드의 추가, 삭제가 용이  </br> 
단점: 특정 노드에 트래픽이 집중될 때 하위 노드에 영향을 끼칠 수 있음  </br>
</br>  
2. 버스(bus) 토폴로지: 중앙 통신 회선 하나에 여러 개의 노드가 연결되어 공유하는 네트워크 구성.</br>
허브나 스위치 같은 중간 매체를 사용하지 않고 케이블들로만 열결한 형태로, 요즘은 거의 사용되지 않지만 현재 사용되는 LAN의 효시.  
 <img src = "https://s3.us-west-2.amazonaws.com/secure.notion-static.com/1fad6647-6fec-4120-861a-071c409911e4/KakaoTalk_Photo_2022-10-21-15-58-25_005.jpeg?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20221021%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20221021T071011Z&X-Amz-Expires=86400&X-Amz-Signature=2fabc90f62221b22b0bae6c78ce93b7cc7fb177d29b37a0f5810cfa37ad8da5a&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22KakaoTalk_Photo_2022-10-21-15-58-25%2520005.jpeg%22&x-id=GetObject" width="60%">  
장점: 설치 비용이 적음 / 신뢰성이 우수함 / 중앙 통신 회선에 노트 추가 삭제가 용이함</br>
단점: 스푸핑이 가능함 / 중간이 단절될 경우 끊어진 시점부터는 통신이 불가능함</br>
</br>

_스푸핑: LAN 상에서 송신부의 패킷을 송신과 관련 없는 다른 호스트에 가지 않도록 하는 스위치 기능을 마비시키거나 속여서 특정 노드에 해당 패킷이 오도록 처리하는 것 즉, 스푸핑을 적용하면 올바르게 수신부로 가야 할 패킷이 악의적인 노드에 전달된다._</br>

</br>  
3. 스타(star) 토폴로지: 중앙에 있는 노드에 모두 연결된 네트워크 구성</br>   
현재 대부분의 네트워크에서는 스타형 또는 스타형을 변형한 형태가 사용된다.</br>
가장 큰 특징은 허브/스위치 같은 '중간 매체'를 통해서 통신을 한다는 것이다.  
<img src = "https://s3.us-west-2.amazonaws.com/secure.notion-static.com/6ddbe874-6a2c-44c6-a2be-5bd2151b329b/KakaoTalk_Photo_2022-10-21-15-58-25_002.jpeg?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20221021%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20221021T073246Z&X-Amz-Expires=86400&X-Amz-Signature=33544a37a015106e2e8cfbb61d8e70e8ba88acbd9e2876766c4f61607c0328db&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22KakaoTalk_Photo_2022-10-21-15-58-25%2520002.jpeg%22&x-id=GetObject" width="60%">  
장점: 노드 추가 용이 / 에러 탐지 용이 / 패킷의 충돌 발생 가능성이 적음 / 어느 노드에 장애가 발생해도 쉽게 에러 발견 가능 / 장애 노드가 중앙 노드(중간매체)가 아닐 경우 다른 노드에 영향을 끼치는 것이 적음</br>
단점: 중간 매체에 장애가 발생하면 전체 네트워크 마비 / 설치 비용이 고가</br>
</br>
4. 링형(ring) 토폴로지: 각각의 노드가 양 옆의 두 노드와 연결하여 전체적으로 고리처럼 하나의 연속된 길을 통해 통신을 하는 망 구성 방식</br>
<img src = "https://s3.us-west-2.amazonaws.com/secure.notion-static.com/deebbe44-c5b1-452f-ad32-e25cb1f35720/KakaoTalk_Photo_2022-10-21-15-58-25_004.jpeg?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20221021%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20221021T070930Z&X-Amz-Expires=86400&X-Amz-Signature=f9f9f8565183964307798d9f74835231f58ee22da786dd823b6b11cb319f240b&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22KakaoTalk_Photo_2022-10-21-15-58-25%2520004.jpeg%22&x-id=GetObject" width="60%"> 
장점: 노드의 수가 증가되어도 네트워크 상의 손실이 거의 없음 / 충돌이 발생되는 가능성이 적음 / 노드의 고장 발견을 쉽게 찾을 수 있음</br>
단점: 네트워크 구성 변경이 어려움 / 중간이 단절될 경우  전체 네트워크가 마비</br>
</br>
링형의 데이터 전달 방식: 실제 패킷을 전송하기 위해 '내가 주인이다'라는 것을 알려주는 토큰(Token)을 사용하고, 데이터는 빙글빙글 원을 타고 돌며 전달됨.
<img src = "https://s3.us-west-2.amazonaws.com/secure.notion-static.com/2a3e7795-1548-45ad-a03c-f420d5085ab3/KakaoTalk_Photo_2022-10-21-15-58-25_003.jpeg?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20221021%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20221021T074243Z&X-Amz-Expires=86400&X-Amz-Signature=54206bfb3d72c04a7d186307e5e7f0c6993aca2e29ea3bf16bf189cd364f3db5&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22KakaoTalk_Photo_2022-10-21-15-58-25%2520003.jpeg%22&x-id=GetObject" width="80%">  
5. 메시(mesh) 토폴로지(망형 토폴로지): 그물망처럼 연결되어 있는 구조  
</br>
<img src = "https://velog.velcdn.com/images/rlaghdtlr012/post/c342afbb-37a9-4bc3-bc5d-9f57ce4820f2/image.png" width="50%">  
장점: 한 단말 장치에 장애가 발생해도 여러 개의 경로가 존재하므로 네트워크를 계속 사용할 수 있음 / 트래픽 분산 처리 가능</br>
단점: 노드의 추가가 어려움 / 구축 비용과 운용 비용이 고가</br>

### 병목 현상
병목 현상(bottlenect): 전체 시스템의 성능이나 용량이 하나의 구성 요소로 인해 제한을 받는 형상. </br>예로, 서비스에서 이벤트를 열었을 때 트래픽이 많이 생기고 그 트랙픽을 잘 관리하지 못하면 병목 현상이 생겨 사용자 웹 사이트로 들어가지 못한다.</br>
_네트워크의 구조인 토폴로지가 중요한 이유 → 병목 현상을 찾을 때 중요한 기준이 되기 때문이다._
</br>
## 네트워크 분류 <- 네트워크를 규모에 따라
네트워크는 규모를 기반으로 근거리 통신망 **LAN**, 도시권 통신망 **MAN**. 광역 통신망 **WAN**으로 나뉜다.

### LAN (Local Area Network)
근거리 통신망을 의미하며, 사무실, 빌딩, 또는 작은 빌딩 몇 개 정도의 네트워크를 말한다.</br>
전송 속도가 빠르고 혼잡하지 않다.</br>
<img src = "https://s3.us-west-2.amazonaws.com/secure.notion-static.com/3fa8f817-7083-42a8-b6ee-821a0345ae93/KakaoTalk_Photo_2022-10-21-18-08-38_003.jpeg?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20221021%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20221021T091153Z&X-Amz-Expires=86400&X-Amz-Signature=760b2d5e2bf54ed91c18dd9bbe330b3a4cb6c34acf4744740394a5a534d79309&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22KakaoTalk_Photo_2022-10-21-18-08-38%2520003.jpeg%22&x-id=GetObject" width="50%">  

### MAN (Metropolitan Area Network)
대도시 지역 네트워크를 의미하며, 도시 같은 넓은 지역에서 운영된다.</br>
전송 속도는 평균이며 LAN보다는 더 많이 혼잡하다.</br>
<img src = "https://s3.us-west-2.amazonaws.com/secure.notion-static.com/3f354f8a-f6e2-4892-b0f0-6de8d138b951/KakaoTalk_Photo_2022-10-21-18-08-37_002.jpeg?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20221021%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20221021T091201Z&X-Amz-Expires=86400&X-Amz-Signature=d5d1af329cb94b217fc727835c038a52bca40989a6b936f316b05d41308ad9f3&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22KakaoTalk_Photo_2022-10-21-18-08-37%2520002.jpeg%22&x-id=GetObject" width="50%">

### WAN (Wide Area Network)
광역 네트워크를 의미하며, 국가 또는 대륙 같은 더 넓은 지역에서 운영된다.</br>
전송 속도는 낮으며 MAN보다 더 혼잡하다.</br>
<img src = "https://s3.us-west-2.amazonaws.com/secure.notion-static.com/f0ad87a6-7ce9-4fe1-8feb-2a295e8ceed4/KakaoTalk_Photo_2022-10-21-18-08-37_001.jpeg?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20221021%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20221021T091211Z&X-Amz-Expires=86400&X-Amz-Signature=4e26fecedd4962c7109612c29c75697bf4e6fea11505deeae75beb3c3f33e5a1&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22KakaoTalk_Photo_2022-10-21-18-08-37%2520001.jpeg%22&x-id=GetObject" width="50%">  
