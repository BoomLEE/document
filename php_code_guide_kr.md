# PHP Coding Style Guide(PSR-1 + PSR-2) 한글

- 다수의 인원이 코드를 읽을 때, 인식의 차이를 줄이기 위한 가이드라인
- 사내 공유용입니다.
- [Japanese](https://github.com/BoomLEE/document/blob/master/php_code_guide_jp.md)

## PSR-1
- 파일은 반드시 <?PHP  또는 <?= 태그로 시작해야한다.
- 파일엔코딩은 UTF-8을 사용한다.
- 네임스페이스와 클래스는 반드시 PSR-0과 PSR-4의 "autoloading" 규칙을 따라야한다.
- 클래스 이름은 반드시 Studlycaps.
- 상수는 (언더스코아+대문자).
- 프로퍼티(멤버변수)는 $Studlycaps, $camelCase, $under_score
   어느 것을 이용하든 상관없으나 $under_score로 통일한다.
- 매서드 이름은 반드시 camelCase.


## PSR-2
- PSR-1에 준거해야한다.
- 들여쓰기(intent)는 4개의 스페이스를 적용, 탭은 사용하지 않음.
 - 스페이스만 사용하는 이유는
 탭과 스페이스가 섞이면 diffs, patches, SVN history등 확인에서 문제가 생기는 것을 피할 수 있다.
- 행의 길이는  80자이내를 권장.
- namespace의 선언 뒤에는 공백하나를 넣어야 함.
- use의 선언 뒤에는 공백 하나를 넣어야 함.
- 클래스에서 열고 닫는 괄호({})는 반드시 다음 라인에 추가한다.
- 메서드에서 열고 닫는 괄호({})는 반드시 다음 라인에 추가한다.
- 모든 프로퍼티(변수)와 메서드에는 반드시 visibility를 선언해야 한다. 
 - Visibility : public, private, protected
  - private : selected class
  - protected : selected class, subclass
  - public  : all
- abstract와 final은 반드시 visibility 앞에 선언한다.
- static는 반드시 visibility 뒤에 선언한다.

## Link
- http://www.php-fig.org/psr/psr-1/
- http://www.php-fig.org/psr/psr-2/
