실습을 잘 따라왓더라면 조금만 응용하면 할 수 있을만한 수준 (교수님기준에서 쪼끔)

rendering pipeline
Application -draw call->Vertex Specification -Vertex->Vertex shader(shader) -> Tessellation,Geometry(shader)->primitive assembly -triangle->resterization-fragment->fragment shader(shader)->fradment processing -pixel->pixel processing->back buffer

transformation
렌더링 파이프라인을 거치다보면 많은 transformation을 거치게된다.
object space -modeling transformation->world space-viewing transformation->view space(camera space)-projection transformation->canonical view volume ☆NDC가 중요합니당(NDC:Normalized Device Coordinate)-viewport transformation->screen space(image space)

Perspective projection(P)
Orthographic projection(O)

frustum
절두체, 입체(보통 원뿔이나 각뿔)를 절단하는 하나나 두 평행면 사이의 부분
-> view volume으로 사용 -> 이 view volume을 viewing frustum이라 함

Perspective projection은 viewing frustum 을 acnonical(규범적인->정육면체=NDC)view volume으로 매핑하는 것

view volume 이 frustum이기 때문에 이를 정육면체(canonical view voulme) 로 변환하면 먼 부분은 작아지게 됨. (원근효과가 나타남)
원래의 3D model ->Perspective projection결과 -> 카메라시점(on screen)

transformation과정은 전부 행렬 합과 차로 표현이된다
로테이션은 Matrix(행렬)들의 곱으로 표현이 된다


메트리스모드를바꾸는 명령어가 잇다그랫져
모델링할때는 모델링으로 카메라할때는 카메라..
glMAtrixWindow.... 전에 배운거,,,

modelview Matrix : 모델링 메트리스와 뷰잉 메트리스를 합친것
- 카메라를 움직이는 것과 world를 움직이는 것은 같은 행위이기 때문에 가능하다
- Camera space를 움직이는 대신 반대 방향으로 world space를 움직이면 됨 ->이게 연관이 잇나?
1단계 model space 
- 어떤 큐브의 로컬원점이 오브젝트 스페이스에서 (0,0,0)(0,0,0)(0,0,0)라고하자
- 모델 변환으로 이 큐브를 world에서 (10,0,0)(10,0,0)(10,0,0) 위치시킴
2단계 카메라 스페이스
- 다음으로 카메라가 world에서 +3만큼 x축으로 간 위치에 잇다고 하면, 뷰 변환은 월드전체를 -3 만큼 옮기는 것과 같음
- 결국 물제는 (7,0,0)에 있게 됨

직교투영
void glOrtho(GLdouble left, GLdouble right,
		GLdouble  , GLdouble  ,
		GLdouble  , GLdouble  );
원근투영
void gluPerspective(GLdouble fovy, GLdouble aspect,
				GLdouble near, GLdouble far);

ㅡㅡㅡㅡㅡ

컨투어를 그렷어. 컨투어가뭐져 폐곡선이라고 합니다. 막힌곡선,
컨투어가 어케하면 이 오브젝트 두개랑 배경이랑 나눌수잇을까
(내가 이해한 바로는 누끼따는법) (배경에 스탑? 싸인모양 있고 약간 발톱;깎은거 모양이 잇음)
이런 알고리즘이 잇습니다. 한 40년된 오래된 알고리즘이 잇어요
계속리버브 시키면서....
최종적으로 배경은 빨간색 두 개의 오브젝트는 파란색으로 나눠지게 됨.
이미지를 로드해서 한겁니다. 이미지를 로드해서 한겁니다.
이때사용한 프로젝션모드는뭘까여 프로젝션은 무슨모드로해서 이걸 만들엇을까 프로젝션은 두개잇져. 오소그래피 하나는 펄스팩티브. 이거는 오소그래피로 한겁니다. 이미지는 깊이가 없음 그래서 원근법으로 할 필요가 없죠
클리핑,,, 오소그래피,,,
이랗게 오픈지엘로 이미지 처리도 할수잇다!
근데 할거면 오픈 씨엘로하세요 하하하








