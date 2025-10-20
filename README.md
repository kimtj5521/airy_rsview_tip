# airy_rsview_tip

update date: 2025.Octo.22

robosense company 의 airy 를 ubuntu 22.04 에서 사용하기 위해 
먼저 rsview software 로 data를 보려고 할 때 tip 이다.

Robosense 의 홈페이지에 Developer -> support -> Download 로 가면
Airy product에 관련된 brochure, user guide, 2D Drawing, 3D model, software 등을 다운 받을 수 있다.
여기서 software 에 ubuntu 용 rsview를 보면 
'RSView V4.3.15 for Ubuntu 20' 라는 이름으로 2025.10.06 날짜의 압축파일을 받을 수 있다.

하지만 다운 받아서 run_rsview.sh 파일을 실행하려고 보면 permission denied 라는 메시지를 터미널에서 보게 될 것이다.
3개의 파일에 대한 권한 허가를 해줘야 한다.
1) run_rsview.sh : 우클릭 후 properties 에 permissions 에서 Allow executing file as program 을 체크 해준다.
   (chmod +x rus_rsview.sh 커맨드를 터미널에 입력해도 됨)
2) bin 퐁더에 RSView 파일 : 우클릭 후 properties 에 permissions 에서 Allow executing file as program 을 체크 해준다.
   (chmod +x RSView 커맨드를 터미널에 입력해도 됨)
3) lib/rsview-4.3 폴더에 RSView 파일 : 우클릭 후 properties 에 permissions 에서 Allow executing file as program 을 체크 해준다.
   (chmod +x RSView 커맨드를 터미널에 입력해도 됨)

이렇게 하면 권한 문제는 해결되는데, 다른 문제가 나올 것이다. 
lib 폴더에 libpcap.so.1: file too short 
이라는 메시지가 나오면서 실행이 안될 것이다. libpcap.so.1 파일이 손상된 것이다. 

다시 robosense 홈페이지에서 Airy 모델이 아닌 M2 product 를 선택해보면, 
똑같은 'RSView V4.3.15 for Ubuntu 20' 라는 이름의 2025.07.20 날짜의 압축파일을 받을 수 있다.
이걸 받은 후 libpcap.so.1 파일을 복사해서 아까 손상되었던 파일에 덮어쓰기를 한다.
그러면 airy 모델이 선택 가능한 rsview 프로그램을 실행 시킬 수 있다.

(robosense 회사는 배포 소프트웨어를 검수하지 않고 배포하는 것인지 의문이다.. )
