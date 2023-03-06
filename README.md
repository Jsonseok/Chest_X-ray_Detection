# Chest_X-ray_Detection

*##프로젝트 목적
  ![m_ild160052t2](https://user-images.githubusercontent.com/112038669/223024754-c56526c3-312a-48b5-81ab-43ec769b74fa.png)
  - 미국의학협회 내과 저널(JAMA Internal Medicine)10일자에 발표된 자료에 의하면 의사의 진단의 평균 정확도는 72%, ai의 평균 정확도는 34%
  - 의사의 평균적인 진찰 정확도가 보다 높을지 언정, 의사의 진찰의 경우 개인의 능력에 따라 정확도가 크게 차이가 있음
  - 이러한 문제를 해결함과 동시에 진찰의 궁극적 목적인 오진율 0%를 달성하기 위해 의사가 진찰시 참고할 수 있는 ai를 개발하고자 프로젝트 진행
    - 의사의 진찰의 정확도의 최저점을 ai의 정확도인 34%로 끌어올림
    - 불확실한 진단에 대해 의사 본인의 진단과 비교분석할 수 있는 교본 제시

*##데이터 분석 
![화면 캡처 2023-03-06 152111](https://user-images.githubusercontent.com/112038669/223038259-23b052f4-43df-4834-a48e-53cbfd5bef4c.png)

![123](https://user-images.githubusercontent.com/112038669/223042000-cdfe031d-580c-4673-8fef-5c03e88b8751.png)

*##데이터 전처리
  - dicom 파일의 이미를 png파일로 변경:
    - 전체적인 데이터의 크기를 줄이기 위함
    
  - 이미지 사이즈를 자본이 감당 가능한 최대 사이즈인 1024x1024로 변환
  
  - Data Augumentation:
    - Rotation, Vertical Flip, Horizontal Flip 사용
      - 채용 이유: 이미지 내의 병변 부위를 손상시키지 않는 augumentation 기법만을 채용
         ![화면 캡처 2023-03-06 194151](https://user-images.githubusercontent.com/112038669/223087864-12fa8a37-f0e3-4509-a08f-53a56593a661.png)








##참조
https://jamanetwork.com/journals/jamainternalmedicine/fullarticle/2565684
