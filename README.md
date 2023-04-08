# Chest_X-ray_Detection

## 🫁 프로젝트 소개

* ### 프로젝트 주제
  - X-ray 사진내의 병변 부위를 검출, 해당 부위가 어떤 병에 걸렸는지 14개의 병명 라벨로 분류
   
* ### 프로젝트 목적 
  - 의료 상황에서 의사 진단을 지원:
    - 병변 부위를 검출하는 시간과 노력을 줄이고, 진단의 정확도와 속도를 향상
    - 의사의 역량으로 인한 의사간의 정확도 차이 감소
    
* ### 개발 환경
  - AWS, VSCode, Phycharm, Anaconda

---

## 🫁 데이터 분석 
<p align="center"><img src="https://user-images.githubusercontent.com/112038669/229672556-5c3d02b5-f1db-4ab4-ab81-2680a8322434.png" width="50%" height="50%"></p>


- 각 라벨에 따른 데이터 양 비교
<p align="center"><img src="https://user-images.githubusercontent.com/112038669/229672417-0eaa8c3e-059e-4f98-af06-8da930db510f.png" width="50%" height="50%"></p>



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

* ### Detectron2(Fast RCNN):
    - 특징:
      - pytorch 기반
      - 기존 Detectron 과 Mask RCNN보다 빠르고 정확한 연산
      - Mask RCNN을 벤치마킹하여 만들어진 detection/segmentation library
    - 선정 이유:
      - 모듈화 돼 있어 추가적인 코드 없이 다양한 model을 사용할 수 있으며 기존 library와 model보다 평균적으로 높은 성능과 빠른 연산을 보이기에 채용 
      
* ### MMDetection(Fast RCNN):
    - 특징:
      - pytorch 기반
      - modulatr design을 통해 다양한 모델을 구성가능
    - 선정 이유:
      - open library 중 detectron2에 다음가는 정확도와 연산 속도를 갖고 있으며 detectron2와 YoloV5와 같이 pytorch를 기반으로 하고 있어 채용

* ### WBF Ensemble:
    - 예측된 bounding box 중 score가 가장 높은 bounding box을 남기는 NMS Ensemble과 달리 정해둔 threshold값 이상인 bounding box들을 융합하여 새로운 bounding box를 만들어내는 ensemble 기법
      
     <p align="center"><img src="https://user-images.githubusercontent.com/112038669/223396724-acc6d212-6434-4a6d-80c3-de6da0c38d21.png" width="50%" height="50%"></p> 
---

## 🫁 모델 결과
<p align="center"><img src="https://user-images.githubusercontent.com/112038669/229686688-a0825945-d30c-443a-9f04-c9403f00f198.png" width="80%" height="80%"></p>




## 🫁 참조
https://jamanetwork.com/journals/jamainternalmedicine/fullarticle/2565684
https://www.kaggle.com/competitions/vinbigdata-chest-xray-abnormalities-detection/overview
https://github.com/open-mmlab/mmdetection
https://github.com/facebookresearch/detectron2
