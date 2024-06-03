# datathon
hai x ybigta datathon에서 작성한 코드 백업

# descrption
본 대회의 Task는 다음과 같습니다.
“Instance segmentation for underwater imagery”
![image](https://github.com/chaehoon1/datathon/assets/168724562/a2be8e5a-44b8-492e-bdfc-f7094d0cbf30)
![image](https://github.com/chaehoon1/datathon/assets/168724562/f4adf5c5-5fea-47a0-bc19-cdbe494d1df2)
![image](https://github.com/chaehoon1/datathon/assets/168724562/7b6cafbc-030d-4829-b639-5c549de8d22f)
![image](https://github.com/chaehoon1/datathon/assets/168724562/f20319e7-16e3-43fa-bb28-3ebb0af2a98c)

데이터셋은 총 7개의 카테고리의 4628장의 이미지로 구성되어 있습니다.

![image](https://github.com/chaehoon1/datathon/assets/168724562/55424f21-a1a0-4ab5-8757-66367465b071)

# dataset description
기본적으로 MS COCO 데이터셋의 format을 따릅니다.

데이터셋은 train, val로 나뉘어져 있습니다.
train 데이터셋에는 여러분들의 모델을 학습시킬 이미지 데이터들이 존재합니다.
annotations 폴더 내에 존재하는 train.json을 통해 이미지의 box, segmentation 정보를 확인하실 수 있습니다!

val 데이터셋에는 이미지만 존재합니다. 여러분들이 학습시킨 모델을 통해 val 폴더 내에 존재하는 이미지들을 평가를 위해 사용하시면 됩니다!

# submission
기본적으로 submission은 csv파일을 제출해주셔야 합니다.
이때 한 이미지에 대한 모든 segmentation mask를 '하나의 행'에 넣어야 에러가 뜨지 않는 점 주의해주세요!
![image](https://github.com/chaehoon1/datathon/assets/168724562/76f0ccb9-ce56-4181-a3ab-09920112274b)
열의 이름은 'id', 'img_id', 'objects', 'height', 'width'입니다.
'id'는 1부터 순차적으로 부여하시면 됩니다.
'img_id'는 val 이미지의 이름을 의미합니다.
'height', 'width'는 제공되는 submission.csv의 내용을 바꾸지 말아주세요.
'objects'에는 인퍼런스의 결과가 json형태로 변환된 후, 리스트로 들어갑니다. segmentation에 실패한 이미지의 경우 빈 리스트가 들어가게 해주시면 됩니다. json의 key는 category_id와 rle_encoding인데, category_id에 그 mask에 해당하는 1~7 사이의 번호가, rle_encoding에 binary mask를 rle encoding한 결과를 넣어주세요!
