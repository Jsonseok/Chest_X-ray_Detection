# Chest_X-ray_Detection

## 🫁 프로젝트 소개

* ### 프로젝트 주제
  - X-ray 사진내의 병변 부위를 검출, 해당 
   
* ### 프로젝트 목적 
  - 미국의학협회 내과 저널(JAMA Internal Medicine)10일자에 발표된 자료에 의하면 의사의 진단의 평균 정확도는 72%, ai의 평균 정확도는 34%
  - 의사의 평균적인 진찰 정확도가 보다 높을지 언정, 개인의 능력에 따라 정확도가 크게 차이가 있음
  - 이러한 문제를 해결함과 동시에 진찰의 궁극적 목적인 오진율 0%를 달성하기 위해 의사가 진찰시 참고할 수 있는 ai를 개발하고자 프로젝트 진행
    - 의사의 진찰의 정확도를 상향 평준화에 이바지
    - 불확실한 진단에 대해 의사 본인의 진단과 비교분석할 수 있는 교본 제시
 
* ### 개발 환경
  - AWS, VSCode, Phycharm, Anaconda

---

## 🫁 데이터 분석 
<p align="center"><img src="https://user-images.githubusercontent.com/112038669/223038259-23b052f4-43df-4834-a48e-53cbfd5bef4c.png" width="80%" height="80%"></p>

<p align="center"><img src="https://user-images.githubusercontent.com/112038669/223042000-cdfe031d-580c-4673-8fef-5c03e88b8751.png" width="80%" height="80%"></p>
---

## 🫁 데이터 전처리
* ### 이미지 전처리:
  - dicom 파일의 이미지를 png파일로 변경
  - 컴퓨팅 자본이 감당 가능한 최대 사이즈인 1024x1024로 변환
  
* ### Augumentation:
  - Rotation, Vertical Flip, Horizontal Flip 사용
    - 채용 이유: 이미지 내의 병변 부위를 손상시키지 않는 augumentation 기법만을 채용

     <p align="center"><img src="https://user-images.githubusercontent.com/112038669/223087864-12fa8a37-f0e3-4509-a08f-53a56593a661.png" width="80%" height="80%"></p>
     
## 🫁 모델 선정
* ### YoloV5:
    - 특징:
      - pytorch 기반
      - 높은 정확도
      - 빠른 연산 속도
    - 선정 이유:
       - 기본적인 성능이 높으며 대용량 이미지를 사용하기 때문에 한번의 연산 속도가 빠른 model을 채용

* ### Detectron2(fast RCNN):
    - 특징:
      - pytorch 기반
      - 기존 Detectron 과 Mask RCNN보다 빠르고 정확한 연산
      - Mask RCNN을 벤치마킹하여 만들어진 detection/segmentation library
    - 선정 이유:
      - 모듈화 돼 있어 추가적인 코드 없이 다양한 model을 사용할 수 있으며 기존 library와 model보다 평균적으로 높은 성능과 빠른 연산을 보이기에 채용 
      
* ### MMDetection(fast RCNN):
    - 특징:
      - pytorch 기반
      - modulatr design을 통해 다양한 모델을 구성가능
    - 선정 이유:
      - open library 중 detectron2에 다음가는 정확도와 연산 속도를 갖고 있으며 detectron2와 YoloV5와 같이 pytorch를 기반으로 하고 있어 채용

* ### WBF Ensemble:
      - 예측된 bounding box 중 score가 가장 높은 bounding box을 남기는 NMS Ensemble과 달리 정해둔 threshold값 이상인 bounding box들을 융합하여 새로운 bounding box를 만들어내는 ensemble 기법
      ![화면 캡처 2023-03-07 193105](https://user-images.githubusercontent.com/112038669/223396724-acc6d212-6434-4a6d-80c3-de6da0c38d21.png)
      
---

## 🫁 모델 결과
<p align="center"><img src="https://user-images.githubusercontent.com/112038669/225225415-10f87740-b504-47c6-9249-9afa677c6d8f.png" width="80%" height="80%"></p>






## 🫁 참조
https://jamanetwork.com/journals/jamainternalmedicine/fullarticle/2565684
https://www.kaggle.com/competitions/vinbigdata-chest-xray-abnormalities-detection/overview
https://github.com/open-mmlab/mmdetection
https://github.com/facebookresearch/detectron2
