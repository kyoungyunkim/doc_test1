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

![\_scroll\_external/attachments/image2019-7-10\_16-30-13-77308d60592b6132e85ddcf6364333c4e5b62fb612b230b94ab40f1556ace33a.png](media/image3.png){width="5.9006944444444445in"
height="2.5893339895013123in"}

신규 개설은 [신청]{.underline} 메뉴에서 할 수 있으며, 아래와 같이 입력
후 전자결재로 전송 을 클릭하여 주십시오.

[T-net - 전자결재]{.underline} 로 가셔서 결재를 상신합니다.

![\_scroll\_external/attachments/image2019-7-10\_16-29-55-6c5c124b75c3d154b5e2f640665a86758e1dd028ae61cb12de051d84a253d56e.png](media/image4.png){width="5.9006944444444445in"
height="4.4706550743657045in"}

VDI가 정상적으로 개설이 되면 아래와 같은 페이지가 나타납니다.
-------------------------------------------------------------

![\_scroll\_external/attachments/image2019-7-10\_16-42-16-649643caf0f9781677c5d54bfee5d53afa3cf2b592a10f50b323aa130c976ce9.png](media/image5.png){width="5.9006944444444445in"
height="4.159646762904637in"}

Citrix Receiver Profile(.ica) 파일을 다운로드하여 VDI 환경에 접속합니다.

VDI 환경 성능 최적화
--------------------

[바탕화면 - 마우스 오른쪽 클릭 - 개인 설정]{.underline} 을 클릭하여
윈도우 테마를 [윈도우 고전]{.underline} 으로 변경 합니다.

![\_scroll\_external/attachments/image2019-7-10\_16-13-39-0d3812feecce82b282d29c473d230628c4a4da88915e9b1a8a1a659272a7f424.png](media/image6.png){width="5.9006944444444445in"
height="3.429803149606299in"}

TiDC VDI에서 Yellow Elephant 화면/로그에 hostname 기반으로 접속할 수 있도록 설정하기
====================================================================================

TiDC VDI 에서 YellowElepaht 로그를 볼 때 FQDN(\*.sktai.io) 형식이 아닌
hostname(bdp-dmi-dn016) 기반의 URL의 경우 DNS Resolve가 되지 않아 링크가
깨진다.

이 문제를 해결하기 위해서는 VDI Windows 머신의 hosts 파일을 갱신해주면
해결할 수 있다.

**\<TiDC VDI에서 hostname 기반 URL 클릭 시 링크 깨짐 현상\>**

![\_scroll\_external/attachments/image2019-9-23\_14-18-50-b2234e27f9dcdbcb1545ad6480743fba03a2c36daff6ee9f61b9426123e737fd.png](media/image7.png){width="5.9006944444444445in"
height="4.7436953193350835in"}

해결 방법
---------

-   TiDC VDI에서 아래 사이트에 접속하여 hosts.for.windows.yyyymmdd 최신
    파일을 다운로드 받습니다.

    -   접속 사이트: <http://repo.sktai.io/hosts/>

-   가장 최신 버전인 hosts.for.windows.20190923 파일을 다운로드
    받습니다.

    -   저장위치: VDI 자신의 HOME 아래 Downloads에 다운로드 받습니다.

![\_scroll\_external/attachments/image2019-9-23\_14-2-16-081d22304b9e7f353c4d0c0f5bd6ecb14d3e7013d7a4e949288ec63e5ae58131.png](media/image8.png){width="5.9006944444444445in"
height="2.0648665791776026in"}

-   Windows Command 창에서 아래와 같이 명령어를 입력 합니다. (시작 -
    실행 - cmd 입력 후 엔터)

+-----------------------------------------------------------------------+
| > C:\\Users\\1111942\> **copy** /V /Y                                 |
| > %HOMEDRIVE%\\%HOMEPATH%\\Downloads\\hosts.for.windows.20190923      |
| > %HOMEDRIVE%\\Windows\\System32\\drivers\\etc\\hosts                 |
+-----------------------------------------------------------------------+

**\<명령어 입력 창 화면\>**

![\_scroll\_external/attachments/image2019-9-23\_14-22-53-f94af1dd120fb8b5a325952f8c19325b4a0b719d4c8de1bb3ae9a10abcd0d7d8.png](media/image9.png){width="5.9006944444444445in"
height="1.8669750656167978in"}

**\<정상 연결 확인\>**

![\_scroll\_external/attachments/image2019-9-23\_14-23-56-e968ce507051e85f25354f8640720abea0997327ef7b8b9a2b789d5294298f2b.png](media/image10.png){width="5.9006944444444445in"
height="4.792148950131233in"}

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
