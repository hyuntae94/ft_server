# 권한설정
775 : 외부인의 쓰기권한만 제외
755 : 그룹,외부인 쓰기권한 제외

소유권바꾸기 : chown [-R] [user][:group] target1 [target2 ..]
(/etc/nginx/nginx.conf 를 보면 user 가 www-data로 설정됨)
ex) $ chown rob:developers strace.log
    strace.log의 소유권을 'rob'으로, 그리고 그룹 식별자를 'developers'로 바꾸기

# ssl 개인키 및 인증서 생성
req : 인증서 요청 및 인증서 생성 유틸
-newkey : 개인키생성
rsa:4096 : 암호비트수
days 365 : 인증서유효기간
-x509 : x509기반 인증서 (중요x)
-subj: subject  입력하기위한 옵션
CN	Common Name	일반 이름 (인증서 고유 이름).
대부분의 인증기관 CA에서는 SSL인증서 신청시에 도메인명을 CN으로 지정.
O	Organization	기관명
OU	Organization Unit	회사/기관 내의 ‘사업부, 부문, 부서, 본부, 과,팀
L	City/Locality	시/도
S	State/County/Region	구/군
ST	Street	나머지 상세 주소. (OV,EV 인증시에만 필요)
C	Country	국가를 나타내는 ISO 코드를 지정. 한국은 KR, 미국은 US 등 2자리 코드

개인키(.key), 서면요청파일(.csr), 인증서파일(.crt)

# nginx 설정
sites-available : 활성화,비활성화된 모든 사이트의 설정이 들어있다.

-p: 파일의 소유자, 그룹, 권한, 시간 정보들이 그대로 보존되어 복사된다.
-r: 원본이 파일이면 그냥 복사되고 디렉터리라면 디렉터리 전체가 복사된다.

# wordpress 설치 및 설정
apt-get 사용 x -> wget 사용
tar 
-x:묶음을 해제
-v:묶음/해제 과정을 화면에 표시
-f:파일이름을 지정

# wordpress를 위한 DB 테이블 생성 

유저 생성 아이디 hyunkim , 패스워드 
내 아이디에 모든권한부여

* root계정 외부접근권한부여
ex)GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED by '비밀번호'; 
