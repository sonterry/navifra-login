# navifra 

cmd에서 navifra 로그인

```
ssh navifra@10.42.0.1
```

비밀번호 : 123123

cd로 이 파일로 이동

```
cd install/install/share/core_launch/launch/3_hungary_bot/configs
```
```
nano QD_H_MobileRobot_Param.yaml
```

수정 할 때 false로 바꾸기
```
nano QD_H_MobileRobot_Param.yaml
```

바꾸고 난 후 리셋
```
sudo systemctl restart core.service
```

스티어링 모터 앞, 뒤 각도 출력
```
rostopic echo /motor_steer_encoder
```
반복출력 [data: "0앞 스티어링 각도/0뒤 스티어링 각도"]

ctrl-C로 중단

수정 끝나고 true로 바꾸기
```
nano QD_H_MobileRobot_Param.yaml
```

바꾸고 난 후 리셋
```
sudo systemctl restart core.service
```

navifra UI오가며 직진&후진, not_on_path 뜨고나서 팝업창의 좌측하단 계산버튼 누르고 각도값을 바로밑줄에 대입하여 정렬

```
rostopic pub /quad_cmd std_msgs/String "data: '0앞속도/0앞각도/0뒤속도/0뒤각도'"
```

```
rostopic pub /encoder_zero std_msgs/Bool "data: false
```

Press ctrl-C






