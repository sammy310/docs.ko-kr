---
description: '자세한 정보: 클라이언트 유효성 검사'
title: Client Validation
ms.date: 03/30/2017
ms.assetid: f0c1f805-1a81-4d0d-a112-bf5e2e87a631
ms.openlocfilehash: 373ee49bccd8905e0cb9bfebf281abdd183ac506
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778570"
---
# <a name="client-validation"></a>Client Validation

서비스는 메타데이터를 자주 게시하여 클라이언트 프록시 형식의 자동 생성 및 구성을 활성화합니다. 서비스를 신뢰할 수 없으면 클라이언트 애플리케이션에서 메타데이터가 보안, 트랜잭션, 서비스 계약 형식 등에 대한 클라이언트 애플리케이션의 정책을 준수하는지 확인해야 합니다. 다음 샘플에서는 서비스 엔드포인트를 안전하게 사용할 수 있도록 서비스 엔드포인트의 유효성을 검사하는 클라이언트 엔드포인트 동작 기록 방법을 보여 줍니다.  
  
 서비스는 네 개의 서비스 엔드포인트를 노출합니다. 첫 번째 엔드포인트는 WSDualHttpBinding을, 두 번째 엔드포인트는 NTLM 인증을, 세 번째 엔드포인트는 트랜잭션 흐름을, 네 번째 엔드포인트는 인증서 기반 인증을 사용합니다.  
  
 클라이언트는 <xref:System.ServiceModel.Description.MetadataResolver> 클래스를 사용하여 서비스에 대한 메타데이터를 검색합니다. 클라이언트에서는 이중 바인딩 방지, NTLM 인증 및 유효성 검사 동작을 사용하는 트랜잭션 흐름에 대한 정책을 적용합니다. <xref:System.ServiceModel.Description.ServiceEndpoint>클라이언트 응용 프로그램은 서비스의 메타 데이터에서 가져온 각 인스턴스에 대해 끝점 동작의 인스턴스를에 추가 하 여 `InternetClientValidatorBehavior` <xref:System.ServiceModel.Description.ServiceEndpoint> WCF (Windows Communication Foundation) 클라이언트를 사용 하 여 끝점에 연결 하려고 시도 합니다. 동작의 `Validate` 메서드는 서비스의 작업이 호출되기 전에 실행되고 `InvalidOperationExceptions`를 throw하여 클라이언트의 정책을 적용합니다.  
  
### <a name="to-build-the-sample"></a>이 샘플을 빌드하려면  
  
1. 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](building-the-samples.md)의 지침을 따르세요.  
  
### <a name="to-run-the-sample-on-the-same-computer"></a>단일 컴퓨터 구성에서 샘플을 실행하려면  
  
1. 관리자 권한으로 Visual Studio에 대 한 개발자 명령 프롬프트를 열고 샘플 설치 폴더에서 Setup.bat를 실행 합니다. 이 작업은 샘플 실행에 필요한 모든 인증서를 설치합니다.  
  
2. \service\bin\Debug에서 서비스 애플리케이션을 실행합니다.  
  
3. \client\bin\Debug에서 클라이언트 애플리케이션을 실행합니다. 클라이언트 콘솔 애플리케이션에 클라이언트 동작이 표시됩니다.  
  
4. 클라이언트와 서비스가 통신할 수 없는 경우 [WCF 샘플에 대 한 문제 해결 팁](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))을 참조 하세요.  
  
5. 샘플 사용을 마치면 Cleanup.bat를 실행하여 인증서를 제거합니다. 다른 보안 샘플에도 동일한 인증서가 사용됩니다.  
  
### <a name="to-run-the-sample-across-computers"></a>다중 컴퓨터 구성에서 샘플을 실행하려면  
  
1. 서버에서 관리자 권한으로 Visual Studio를 실행 하는 개발자 명령 프롬프트에서를 입력 `setup.bat service` 합니다. `setup.bat`인수를 사용 하 여를 실행 하면 컴퓨터의 정규화 된 `service` 도메인 이름으로 서비스 인증서가 생성 되 고 서비스 인증서가 이름이 .cer 인 파일로 내보내집니다.  
  
2. 서버에서 새 인증서 이름을 반영하도록 App.config를 편집합니다. 즉, `findValue` 요소의 특성을 [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) 컴퓨터의 정규화 된 도메인 이름으로 변경 합니다.  
  
3. 서비스 디렉터리에서 클라이언트 컴퓨터의 클라이언트 디렉터리로 Service.cer 파일을 복사합니다.  
  
4. 클라이언트에서 관리자 권한으로 Visual Studio에 대 한 개발자 명령 프롬프트를 열고를 입력 `setup.bat client` 합니다. `setup.bat`인수를 사용 하 여를 실행 `client` 하면 이름이 Client.com 인 클라이언트 인증서가 만들어지고 클라이언트 인증서가 client.msi 이라는 파일로 내보내집니다.  
  
5. client.cs 파일에서 MEX 엔드포인트의 주소 값과 `findValue`를 변경하여 서비스의 새 주소와 일치하도록 기본 서버 인증서를 설정합니다. 이 작업을 수행하려면 localhost를 서버의 정규화된 도메인 이름으로 바꿉니다. 다시 빌드합니다.  
  
6. 클라이언트 디렉터리에서 서버의 서비스 디렉터리로 Client.cer 파일을 복사합니다.  
  
7. 클라이언트에서 관리자 권한으로 연 Visual Studio 용 개발자 명령 프롬프트에서 ImportServiceCert.bat를 실행 합니다. 이 작업은 Service.cer 파일의 서비스 인증서를 CurrentUser - TrustedPeople 저장소로 가져옵니다.  
  
8. 서버에서 관리자 권한으로 연 Visual Studio 용 개발자 명령 프롬프트에서 ImportClientCert.bat를 실행 합니다. 이 작업은 Client.cer 파일의 클라이언트 인증서를 LocalMachine - TrustedPeople 저장소로 가져옵니다.  
  
9. 서비스 컴퓨터에서 Visual Studio로 서비스 프로젝트를 빌드하고 service.exe를 실행합니다.  
  
10. 클라이언트 컴퓨터에서 client.exe를 실행합니다.  
  
    1. 클라이언트와 서비스가 통신할 수 없는 경우 [WCF 샘플에 대 한 문제 해결 팁](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))을 참조 하세요.  
  
### <a name="to-clean-up-after-the-sample"></a>샘플 실행 후 정리를 수행하려면  
  
- 샘플 실행을 완료했으면 샘플 폴더에서 Cleanup.bat를 실행합니다.  
  
    > [!NOTE]
    > 다중 컴퓨터 구성에서 이 샘플을 실행할 경우에는 이 스크립트로 클라이언트의 서비스 인증서를 제거할 수 없습니다. 컴퓨터에서 인증서를 사용 하는 WCF 샘플을 실행 한 경우에는 CurrentUser-비트 사용자 저장소에 설치 된 서비스 인증서를 지워야 합니다. 이렇게 하려면 `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>. For example: certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com` 명령을 사용합니다.  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 사용](../feature-details/using-metadata.md)
