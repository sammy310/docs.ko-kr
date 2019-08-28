---
title: FindPrivateKey 샘플-WCF
ms.date: 12/04/2017
helpviewer_keywords:
- FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
ms.openlocfilehash: b89d135d7412f10cb9de1e4bda1aaab14b29cbf0
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490775"
---
# <a name="findprivatekey-sample"></a>FindPrivateKey 샘플

인증서 저장소에서 특정 X.509 인증서와 연결된 프라이빗 키 파일의 위치 및 이름을 찾기가 어려울 수 있습니다. FindPrivateKey.exe 도구는 이 과정에 도움이 됩니다.

> [!IMPORTANT]
> FindPrivateKey는 사용하기 전에 컴파일되어야 하는 샘플입니다. 참조 된 [FindPrivateKey 프로젝트를 빌드하려면](#to-build-the-findprivatekey-project) FindPrivateKey 도구를 빌드하는 방법에 대 한 지침은 섹션.

X.509 인증서는 관리자 또는 시스템에 있는 모든 사용자가 설치합니다. 그러나 인증서를 다른 계정으로 실행 되는 서비스에서 액세스할 수 있습니다. 예를 들어, 네트워크 서비스 계정입니다.

처음에 인증서를 이 계정으로 설치하지 않았기 때문에 이 계정에 프라이빗 키 파일에 대한 액세스 권한이 없을 수도 있습니다. FindPrivateKey 도구는 지정된 X.509 인증서의 개인 키 파일 위치를 알려줍니다. 특정 X.509 인증서의 프라이빗 키 파일 위치를 알고 나면 이 파일의 사용 권한을 추가하거나 제거할 수 있습니다.

보안에 대 한 인증서를 사용 하는 샘플에서 FindPrivateKey 도구를 사용 합니다 *Setup.bat* 파일입니다. 와 같은 다른 도구를 개인 키 파일을 찾으면 사용할 수 있습니다 *Cacls.exe* 파일에 적절 한 액세스 권한을 설정 합니다.

자체 호스팅된 실행 파일을 같은 사용자 계정으로 Windows Communication Foundation (WCF) 서비스를 실행할 때 사용자 계정에 파일에 읽기 전용 액세스를 확인 합니다. 인터넷 정보 서비스 (IIS)에서 WCF 서비스를 실행 하는 경우는 서비스가 실행 되는 기본 계정은 IIS 7 및 이전 버전의 네트워크 서비스 또는 IIS 7.5 이상 버전에서 응용 프로그램 풀 Id입니다. 자세한 내용은 [응용 프로그램 풀 Id](/iis/manage/configuring-security/application-pool-identities)합니다.

## <a name="examples"></a>예제

프로세스 읽기 권한이 없는 인증서에 액세스 하는 경우 다음 예와 비슷한 예외 메시지가 표시:

```
System.ArgumentException was unhandled
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."
Source="System.ServiceModel"
```

이 경우 FindPrivateKey 도구를 사용 하 여 개인 키 파일을 찾으려고 하 고 오른쪽에서 서비스가 실행 되는 프로세스에 대 한 액세스를 설정 합니다. 예를 들어, 다음 예와에서 같이 Cacls.exe 도구를 사용 하 여이 수행할 수 있습니다.

```
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R
```

#### <a name="to-build-the-findprivatekey-project"></a>FindPrivateKey 프로젝트를 빌드하려면

프로젝트를 다운로드 하려면 방문 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://www.microsoft.com/download/details.aspx?id=21459)합니다.

1. 파일 탐색기를 열고로 이동 합니다 *WF_WCF_Samples\WCF\Setup\FindPrivateKey\CS* 샘플을 설치한 디렉터리 위치 아래의 폴더입니다.

2. .sln 파일 아이콘을 두 번 클릭하여 Visual Studio에서 파일을 엽니다.

3. 에 **빌드** 메뉴에서 **솔루션 다시 빌드**합니다.

4. 솔루션을 빌드하는 파일을 생성 합니다. FindPrivateKey.exe.

## <a name="conventionscommand-line-entries"></a>규칙 — 명령줄 항목

 "[*옵션*]"은 선택적 매개 변수 집합을 나타냅니다.

 "{*옵션*}" 매개 변수의 필수 집합을 나타냅니다.

 "*option1* &#124; *option2*"는 옵션 집합 사이의 선택을 나타냅니다.

 "\<*값*>" 입력 매개 변수 값을 나타냅니다.

## <a name="usage"></a>사용법

```
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

여기서

```
       <subjectName> The subject name of the certificate
       <thumbprint>  The thumbprint of the certificate (You can use the Certmgr.exe tool to find this)
       -f            output file name only
       -d            output directory only
       -a            output absolute file name
```

명령 프롬프트에서 지정 된 매개 변수가 없는 경우에이 도움말 텍스트가 표시 됩니다.

## <a name="examples"></a>예제

인증서의 주체 이름 가진 파일 이름을 검색 하는이 예제 "CN = localhost", 현재 사용자의 개인 저장소에 있습니다.

```
FindPrivateKey My CurrentUser -n "CN=localhost"
```

인증서의 주체 이름 가진 파일 이름을 검색 하는이 예제 "CN = localhost", 개인 현재 사용자의 저장소 및 전체 디렉터리 경로 출력 합니다.

```
FindPrivateKey My CurrentUser -n "CN=localhost" -a
```

이 예제에서는 로컬 컴퓨터의 개인 저장소에서 지문이 "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52"인 인증서의 파일 이름을 찾습니다.

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52"
```
