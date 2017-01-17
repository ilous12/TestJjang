TRTC -T전화 글로벌을 위한 mVoIP 프레임워크
======================================

> T전화 어플리케이션내에 mVoIP 솔루션 내재화를 위해 생성된 프로젝트 입니다.
> WebRTC 기반의 미디어 프레임워크와, 단순화된 Signaling, NAT Traversal을 통해,
> 기본보다 빠른, 호접속 시간, 고품질의 화상통화 제공을 목표로 하고 있습니다.

주요기능
------------------

1. 라틴어(`lat`)
1. 독일어(`deu`)
1. 러시아어(`rus`)
1. 현대 그리스어(`ell`)
1. 고대 그리스어(`grc`)
1. 이탈리아어(`ita`)
1. 스페인어(`spa`)
1. 일본어(`jpn`)
1. 폴란드어(`pol`)
1. 체코어(`ces`)
1. 세르보크로아트어(`hbs`)
1. 루마니아어(`ron`)
1. 헝가리어(`hun`)
1. 베트남어(`vie`)
1. 스웨덴어(`swe`)
1. 네덜란드어(`nld`)
1. 포르투갈어(`por`)
1. 브라질 포르투갈어(`por.br`)
1. 웨일스어(`cym`)
1. 중세 웨일스어(`wlm`)
1. 불가리아어(`bul`)
1. 조지아어 간략전사(`kat`)
1. 조지아어 정밀전사(`kat.narrow`)
1. 핀란드어(`fin`)
1. 에스토니아어(`est`)
1. 라트비아어(`lav`)
1. 리투아니아어(`lit`)
1. 아이슬란드어(`isl`)
1. 카탈루냐어(`cat`)
1. 슬로바키아어(`slk`)
1. 슬로베니아어(`slv`)
1. 알바니아어(`sqi`)
1. 에스페란토(`epo`)
1. 우크라이나어(`ukr`)
1. 벨라루스어(`bel`)
1. 마케도니아어(`mkd`)
1. 터키어(`tur`)
1. 아제르바이잔어(`aze`)

설치
----

1. pip 이용:

    $ pip install hangulize

1. easy_install 이용:

    $ easy_install hangulize

1. pip로 개발버전 받기:

    $ pip install git+git://github.com/sublee/hangulize.git#egg=hangulize

1. 저장소 내려받아 설치하기:

    $ git clone git://github.com/sublee/hangulize.git
    $ cd hangulize
    $ python setup.py install

사용법
------

`hangulize` 함수를 사용해야합니다. 우선 모듈로부터 함수를 불러옵니다:

    >>> from hangulize import hangulize

`hangulize` 함수는 첫번째 인자로 변환할 단어를, 두번째 인자로 언어코드(ISO
639-3)를 입력받습니다. 이 함수는 표준 외래어표기법을 따른 한글 변환 결과를
반환할 것입니다:

    >>> print hangulize(u"Giro d'Italia", 'ita')
    지로 디탈리아
    >>> print hangulize(u'オオサカ', 'jpn')
    오사카
    >>> print hangulize(u'przyjaciół', 'pol')
    프시야치우
    >>> print hangulize(u'Алексеев', 'rus')
    알렉세예프
    >>> print hangulize(u'კახაბერ', 'kat.narrow')
    까하베르
    >>> print hangulize(u'Ἡρακλῆς', 'grc')
    헤라클레스

테스트
------

국립국어원 사이트에 있는 [외래어 표기법][1]을 토대로 작성한 테스트수트를
작동시킵니다:

    $ python setup.py test
    제1항: gl ... ok
    제2항: gn ... ok
    제3항: sc ... ok
    제4항 ... ok
    ...

이때 `HANGULIZE_TEST_LANG` 환경 변수를 설정할 경우, 해당 언어의 테스트만
할 수도 있습니다:

    $ HANGULIZE_TEST_LANG=jpn python setup.py test
    ...

또는 REPL 모드를 사용할 수 있습니다. REPL 모드에서는 단어의 변화 과정이
표준출력으로 나타납니다:

    $ python setup.py repl
    Select Locale: pol
    ==> łóżko
    -> 'łóżko'
    -> 'Xuóżko'
    -> 'Xuużko'
    -> 'Xuuszko'
    -> 'XuusJuko'
    -> 'XusJuko'
    -> 'usJuko'
    -> 'usJu o'
    -> 'u Ju o'
    -> 'u   o'
    -> 'u    '
    -> '     '
    우슈코

contributors
------

- 조현덕 <<hyundeuk.cho@sk.com>> - Developer, PM
- 조종화 <<jonghwa.jo@sk.com>> - Developer
- 이광희 <<ubuntu@sk.com>> - Developer
- 허재호 <<jaeho.hur@sk.com>> - Developer
- 추세일 <<seil.chu@sk.com>> - Developer

라이선스
-------

WebRTC에서 포크된 프로젝트 이므로, 관련 라이센스는 아래의 참조를 따릅니다.
 [1]: https://webrtc.org/license/software/

링크
----

- [웹사이트][]
- [WebRTC][]
- [QUIC][]QUIC Protocol
- [읽어봐!][](또 다른 외래서 전사 프로그램) by 마늘아빠

 [웹사이트]: https://git.prod.sktelecom.com/developer/trtc
 [WebRTC]: https://webrtc.org
 [QUIC]: https://www.chromium.org/quic
 
