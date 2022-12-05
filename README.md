- 사용한 데이터셋
    
    ![Untitled](https://user-images.githubusercontent.com/103106183/205649445-3f4392f3-4ea3-4b77-b323-146868fa23fd.png)

    
    - user 데이터 추출(총 746243개)
        
        ![Untitled 1](https://user-images.githubusercontent.com/103106183/205649499-f36e94a8-2eb9-4755-953b-462ce569cbe1.png)

        ![Untitled 2](https://user-images.githubusercontent.com/103106183/205649570-959ea595-e8fc-49ea-aae7-e9f17445ecac.png)
        
    - item 데이터 추출(스팀의 전체 게임 데이터는 51927개. 실제 추천에 사용되는 게임 데이터는 11566개로 약 1/5 축소됨)
        
        ![Untitled 3](https://user-images.githubusercontent.com/103106183/205649675-166441ae-28d7-4ee4-9d1d-89e1a779af4d.png)
        
        ![Untitled 4](https://user-images.githubusercontent.com/103106183/205649728-26a81fcc-4245-4491-ac12-64b31996c361.png)

        
    - 따라서 746243*11566의 coarse한 interactions matrix 생성
- 모델
    - user_features(playtime_forever 사용)
        
        ![image](https://user-images.githubusercontent.com/103106183/205656856-0a35ac71-4a3f-4a23-ad27-96d82173cbd5.png)

        
    - 손실함수로 warp 사용, test_percentage 및 epochs 임의 조정
        
        ![Untitled 6](https://user-images.githubusercontent.com/103106183/205649835-0b025823-a571-41d3-82c7-10faffc55928.png)
        
- 평가방식
    - lightFm 모델에서 제공하는 평가방식
        - precision_at_k
        - auc

- 실제 추천
    
    유저 입력시
    
    ![Untitled 9](https://user-images.githubusercontent.com/103106183/205650144-e19598a4-ca84-49fa-88fe-371568a0d973.png)
    
    추천 함수 동작
    
    ![Untitled 8](https://user-images.githubusercontent.com/103106183/205650024-a15ffaa7-d89f-4386-92de-0263b86164b7.png)
    
    결과
    
    ![Untitled 9](https://user-images.githubusercontent.com/103106183/205650072-faea8181-d8ae-41f6-ab06-0abc4e8f0c91.png)
