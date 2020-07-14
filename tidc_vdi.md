TiDC VDI 개설 신청하기(DMIG 인프라 접근)

AI/DT Engineering CoE

Exported on 2020 07 13,

-   [TiDC VDI 개설 신청하기](#tidc-vdi-개설-신청하기)

    -   [VDI 사이트 접속 후 MyDesk와 같은 방식으로 로그인 합니다. (FIDO
        인증
        필요)](#vdi-사이트-접속-후-mydesk와-같은-방식으로-로그인-합니다.-fido-인증-필요)

    -   [로그인 후 보안프로그램 설치 페이지가
        나타납니다.](#로그인-후-보안프로그램-설치-페이지가-나타납니다.)

-   [VDI 가 없는 경우 개설 신청하기](#vdi-가-없는-경우-개설-신청하기)

    -   [VDI가 정상적으로 개설이 되면 아래와 같은 페이지가
        나타납니다.](#vdi가-정상적으로-개설이-되면-아래와-같은-페이지가-나타납니다.)

    -   [VDI 환경 성능 최적화](#vdi-환경-성능-최적화)

-   [TiDC VDI에서 Yellow Elephant 화면/로그에 hostname 기반으로 접속할
    수 있도록
    설정하기](#tidc-vdi에서-yellow-elephant-화면로그에-hostname-기반으로-접속할-수-있도록-설정하기)

    -   [해결 방법](#해결-방법)

-   [주요 분석환경 제공 URL](#주요-분석환경-제공-url)

-   [참고) TiDC VDI → YellowElephant Firewall
    Rules](#참고-tidc-vdi-yellowelephant-firewall-rules)

    -   [YellowElephant Host Group](#yellowelephant-host-group)

TiDC VDI 개설 신청하기
======================

VDI 사이트 접속 후 MyDesk와 같은 방식으로 로그인 합니다. (FIDO 인증 필요)
-------------------------------------------------------------------------

-   TiDC VDI 접속 URL: <https://devdi.sktelecom.com>.

 ![](http://18.219.180.88:9000/tidc_vdi_img/image1.png)

로그인 후 보안프로그램 설치 페이지가 나타납니다.
------------------------------------------------

Mac에서 보안 프로그램을 설치 할 경우 ***스크린 캡춰가 동작하지 않는
문제*** 가 발생합니다.

다소 불편하지만, 주소 URL을 아래와 같이 변경하여 보안 프로그램 설치
단계를 우회 합니다.

-   우회 주소:  <https://devdi.sktelecom.com/NON_SSO/Vdi/Main>

![](http://18.219.180.88:9000/tidc_vid_img/image2.png)

VDI Main 페이지에 접근하여 Citrix Receiver Profile(.ica) 파일을
다운로드하여 VDI 환경에 접속합니다.

VDI 가 없는 경우 개설 신청하기
==============================

아래와 같이 \'계정이 부여되어 있지 않습니다\' 라고 나오면 VDI 개설이
아직 되지 않은 것입니다.

![](http://18.219.180.88:9000/tidc_vid_img/image3.png)

신규 개설은 [신청]{.underline} 메뉴에서 할 수 있으며, 아래와 같이 입력
후 전자결재로 전송 을 클릭하여 주십시오.

[T-net - 전자결재]{.underline} 로 가셔서 결재를 상신합니다.

![](http://18.219.180.88:9000/tidc_vid_img/image4.png)

VDI가 정상적으로 개설이 되면 아래와 같은 페이지가 나타납니다.
-------------------------------------------------------------

![](http://18.219.180.88:9000/tidc_vid_img/image5.png)

Citrix Receiver Profile(.ica) 파일을 다운로드하여 VDI 환경에 접속합니다.

VDI 환경 성능 최적화
--------------------

[바탕화면 - 마우스 오른쪽 클릭 - 개인 설정]{.underline} 을 클릭하여
윈도우 테마를 [윈도우 고전]{.underline} 으로 변경 합니다.

![](http://18.219.180.88:9000/tidc_vid_img/image6.png){width="5.9006944444444445in"
height="3.429803149606299in"}

TiDC VDI에서 Yellow Elephant 화면/로그에 hostname 기반으로 접속할 수 있도록 설정하기
====================================================================================

TiDC VDI 에서 YellowElepaht 로그를 볼 때 FQDN(\*.sktai.io) 형식이 아닌
hostname(bdp-dmi-dn016) 기반의 URL의 경우 DNS Resolve가 되지 않아 링크가
깨진다.

이 문제를 해결하기 위해서는 VDI Windows 머신의 hosts 파일을 갱신해주면
해결할 수 있다.

**\<TiDC VDI에서 hostname 기반 URL 클릭 시 링크 깨짐 현상\>**

![](http://18.219.180.88:9000/tidc_vid_img/image7.png)

해결 방법
---------

-   TiDC VDI에서 아래 사이트에 접속하여 hosts.for.windows.yyyymmdd 최신
    파일을 다운로드 받습니다.

    -   접속 사이트: <http://repo.sktai.io/hosts/>

-   가장 최신 버전인 hosts.for.windows.20190923 파일을 다운로드
    받습니다.

    -   저장위치: VDI 자신의 HOME 아래 Downloads에 다운로드 받습니다.

![](http://18.219.180.88:9000/tidc_vid_img/image8.png)

-   Windows Command 창에서 아래와 같이 명령어를 입력 합니다. (시작 -
    실행 - cmd 입력 후 엔터)

+-----------------------------------------------------------------------+
| > C:\\Users\\1111942\> **copy** /V /Y                                 |
| > %HOMEDRIVE%\\%HOMEPATH%\\Downloads\\hosts.for.windows.20190923      |
| > %HOMEDRIVE%\\Windows\\System32\\drivers\\etc\\hosts                 |
+-----------------------------------------------------------------------+

**\<명령어 입력 창 화면\>**

![](http://18.219.180.88:9000/tidc_vid_img/image9.png)

**\<정상 연결 확인\>**

![](http://18.219.180.88:9000/tidc_vid_img/image10.png)

주요 분석환경 제공 URL
======================

  분석환경   접속 URL                       비고
  ---------- ------------------------------ ------------------
  Jupyter    <http://jupyterhub.sktai.io>   계정은 별도 제공
  Hue        <http://hue.sktai.io>          계정은 별도 제공
  Zeppelin   <http://zeppelin.sktai.io>     계정은 별도 제공

참고) TiDC VDI → YellowElephant Firewall Rules
==============================================

TiDC VDI에서 YellowElephant로 향하는 방화벽은 아래 포트로 오픈 되어
있습니다.

  Role                         Firewall
  ---------------------------- --------------------
  Yarn Resource Manger         Master Node:8088
  Yarn NodeManager             Data Node:8042
  HDFS Namenode                Master Node: 50070
  HDFS Datanode                Data Node: 50075
  JobHistory UI                Master Node: 19888
  Hive Dashboard               Master Node: 3000
  HiveServer2 Interactive UI   Master Node: 10502
  Hive Jar Download            Master Node: 10002
  HBase Master UI              Master Node: 16010
  Solr Admin UI                Master Node: 8886
  Ambari Metrics               Mgmt. Node: 3000
  Ranger Admin UI              Master Node: 6080
  Spark2 History Server UI     Master Node: 18081
  Zeppelin Notebook            Mgmt. Node: 9995
  Druid Coordinator Console    Mgmt. Node: 8081
  Druid Overload Console       Mgmt. Node: 8090
  Superset UI                  Mgmt. Node: 9088
  DNS                          Mgmt. Node: 53

YellowElephant Host Group
-------------------------

  Host Group    Host
  ------------- -----------------------
  Master Node   bdp-dmi-nn\[001-003\]
  Data Node     bdp-dmi-dn\[001-058\]
  Mgmt. Node    bdp-dmi-mg\[001-005\]
