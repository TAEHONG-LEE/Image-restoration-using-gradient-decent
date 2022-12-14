# Image restoration using gradient decent

경사하강법을 활용한 이미지 복원 코드입니다.



- 프로젝트 개요
  - 이미지 처리를 위해 만들어 두었던 weird_function() 함수에 실수로 버그가 들어가 100×100 픽셀의 오염된 미미지가 만들어졌다. 
  - 이 오염된 이미지와 오염되기 전 원본 이미지를 동시에 파일로 저장하려고 했으나, 모종의 이유로 원본 이미지 파일은 삭제된 상황이다. 
  - 다행히 weird_function()의 소스코드는 남아 있다. 
  - 오염된 이미지와 weird_function()을 활용해 원본 이미지를 복원해보자.



- 일반적인 접근 방법
  1. weird_function() 함수의 소스코드 분석
  2. 분석을 토대로 weird_function() 함수의 동작을 반대로 이행하는 함수 구현
  3. 2에서 구현한 함수에 오염된 이미지를 입력한 후, 복구된 이미지 출력
  
  
  
- 머신러닝 방식의 접근 방법(사고 방법)
  1. 오염된 이미지와 같은 크기의 랜덤 텐서를 생성한다.
  2. 랜덤 텐서를 weird_function() 함수에 입력해 똑같이 오염된 이미지를 가설이라고 부른다.
    - (사실) 원본 이미지가 weird_function() 함수에 입력되어 오염된 이미지를 출력했다.
    - (사실) 인위적으로 생성한 무작위 이미지가 weird_function() 함수에 입력되어 가설을 출력했다.
  3. 가설과 오염된 이미지가 같다면 무작위 이미지와 원본 이미지도 같을 것이다.
  4. 그러므로 weird_function(random_tensor) = broken_image 관계가 성립하도록 만든다.
  
  
  
  
  작성하기에 앞서 [ICT COG Academy] 인공지능 고급(언어)과정을 수강하며 복습을 위해 작성한 글임을 명시합니다.
