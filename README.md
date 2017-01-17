TRTC -T전화 글로벌을 위한 mVoIP 프레임워크
======================================

> T전화 어플리케이션내에 mVoIP 솔루션 내재화를 위해 생성된 프로젝트 입니다.
> WebRTC 기반의 미디어 프레임워크와, 단순화된 Signaling, NAT Traversal을 통해,
> 기본보다 빠른, 호접속 시간, 고품질의 화상통화 제공을 목표로 하고 있습니다.

설치
----

    $ git clone http://git.prod.sktelecom.com/developer/trtc.git

iOS BUILD
------

국립국어원 사이트에 있는 [외래어 표기법][1]을 토대로 작성한 테스트수트를
작동시킵니다:

    $ gn gen out/Release-universal -args='target_os="ios" target_cpu="x64" additional_target_cpus=["arm", "arm64", "x86"] is_component_build=false is_debug=false ios_enable_code_signing=false' -ide=xcode
    $ ninja -C out/Release-universal/ rtc_sdk_framework_objc -t clean
    $ ninja -C out/Release-universal/ rtc_sdk_framework_objc

Android BUILD
------

국립국어원 사이트에 있는 [외래어 표기법][1]을 토대로 작성한 테스트수트를
작동시킵니다:

    $ gn gen out/debug/android/arm --args='target_os="android" target_cpu="arm" rtc_support_quic=true is_component_build=false rtc_include_tests=false'
    $ ninja -C out/debug/android/arm -t clean
    $ ninja -C out/debug/android/arm

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
 [1]: https://webrtc.org/license/software

링크
----

- [웹사이트][]
- [WebRTC][]
- [QUIC][] QUIC Protocol

 [웹사이트]: https://git.prod.sktelecom.com/developer/trtc
 [WebRTC]: https://webrtc.org
 [QUIC]: https://www.chromium.org/quic
 
