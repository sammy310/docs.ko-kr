---
title: WCF 테스트 클라이언트(WcfTestClient.exe)
ms.date: 03/30/2017
ms.assetid: d4302855-677f-4640-aa90-c5d785d72fb7
ms.openlocfilehash: 9044dc2479e8e0a31a6152321231ee1936b74351
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2019
ms.locfileid: "67487457"
---
# <a name="wcf-test-client-wcftestclientexe"></a>WCF 테스트 클라이언트(WcfTestClient.exe)
Windows Communication Foundation (WCF) 테스트 클라이언트 (WcfTestClient.exe)는 테스트 매개 변수를 입력 하 여 해당 서비스에 입력을 사용 하면 서비스가 다시 보낸 응답을 확인 하는 GUI 도구입니다. 서비스를 매끄럽게 테스트할 WCF 서비스 호스트를 함께 사용 하면 환경을 제공 합니다.  
  
 일반적으로 다음 위치에서 WCF 테스트 클라이언트 (WcfTestClient.exe)를 찾을 수 있습니다: `C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE` -커뮤니티는 "Enterprise", "전문가" 중 하나일 수 있습니다 또는 "커뮤니티"는 수준에 따라 Visual Studio가 설치 되어 있습니다.
  
## <a name="scenarios-for-using-test-client"></a>테스트 클라이언트 사용 시나리오  
 다음 섹션에서는 개발 프로세스를 간소화 하기 위해 WCF 테스트 클라이언트를 사용할 수 있는 가장 일반적인 시나리오를 설명 합니다.  
  
### <a name="inside-visual-studio"></a>Visual Studio의 경우  
  
#### <a name="wcf-service-host-starts-wcf-test-client-with-a-single-service"></a>WCF 서비스 호스트가 단일 서비스에서 WCF 테스트 클라이언트 시작  
 새 WCF 서비스 프로젝트를 만든 후 프로젝트에서 서비스를 호스팅할 WCF 서비스 호스트 시작 f5 키를 눌러 디버거를 시작 합니다. 그런 다음 WCF 테스트 클라이언트가 열리고 구성 파일에 정의 된 서비스 끝점의 목록을 표시 합니다. 그러면 매개 변수를 테스트하고, 서비스를 호출하며, 이 프로세스를 반복하여 테스트를 계속하고 서비스의 유효성을 검사할 수 있습니다.  
  
#### <a name="wcf-service-host-starts-wcf-test-client-with-multiple-services"></a>WCF 서비스 호스트가 여러 서비스에서 WCF 테스트 클라이언트 시작  
 또한 여러 서비스가 포함 된 서비스 프로젝트를 디버깅 하는 데 WCF 테스트 클라이언트를 사용할 수 있습니다. WCF 테스트 클라이언트를 열면 자동으로 프로젝트에서 서비스 목록을 반복 하 고 테스트를 위해 열립니다.  
  
### <a name="outside-visual-studio"></a>Visual Studio 외부  
 또한 인터넷에서 임의의 서비스를 테스트 하려면 Visual Studio 외부에서 WCF 테스트 클라이언트 (WcfTestClient.exe)를 호출할 수 있습니다. 도구를 찾으려면 다음 위치로 이동합니다.  
  
 `C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE` (여기서 커뮤니티 중 하나일 수 있습니다 "Enterprise", "Professional" 또는 "커뮤니티"에 따라 수준의 Visual Studio가 컴퓨터에 설치)
  
 도구를 사용하려면 파일 이름을 두 번 클릭하여 이 위치에서 열거나 명령줄에서 시작합니다.  
  
 WCF 테스트 클라이언트는 명령줄 인수로 임의 개수의 Uri입니다.  이들은 테스트할 수 있는 서비스의 URI입니다.  
  
 `wcfTestClient.exe URI1 URI2 …`  
  
 WCF 테스트 클라이언트 창이 열린 후 클릭 **파일**->**서비스 추가**를 열려는 서비스의 끝점 주소를 입력 합니다.  
  
## <a name="wcf-test-client-user-interface"></a>WCF 테스트 클라이언트 사용자 인터페이스  
 단일 서비스 또는 여러 서비스를 사용 하 여 WCF 테스트 클라이언트를 사용할 수 있습니다.  
  
### <a name="service-operations"></a>서비스 작업  
 WCF 테스트 클라이언트 주 창의 왼쪽된 창에는 각 끝점 및 작업과 함께 사용할 수 있는 모든 서비스를 나열합니다.  
  
 작업을 두 번 클릭하면 작업 이름이 표시된 새 탭 내의 오른쪽 창에서 해당 내용을 볼 수 있습니다.  
  
 또한 왼쪽 창에는 클라이언트 구성 파일이 나열됩니다. 이 항목 중 하나를 두 번 클릭하면 오른쪽 창의 새 탭 창에 파일 내용이 표시됩니다.  
  
### <a name="entering-test-parameters"></a>테스트 매개 변수 입력  
 테스트 매개 변수를 보려면 작업을 두 번 클릭하여 오른쪽 창에서 엽니다. 매개 변수는에 표시 된 **서식 있음** 보기 기본적으로 서비스를 테스트 하려면 매개 변수를 임의의 값을 입력할 수 있습니다.  
  
 메시지의 XML을 보려면 클릭 **XML**합니다. 서비스에 보낼, 클릭 **Invoke**합니다.  
  
 데이터 집합 매개 변수를 클릭 하 여 **...** 다음 단추 **편집...** DataGrid를 보여 주는 새 창에서 편집 합니다. 모양을 확인 합니다 **데이터 집합 복사** 및 **데이터 집합 붙여넣기** 단추입니다. 처음 편집할 때 DataSet 개체의 스키마를 알 수 없는 경우 DataGrid는 비어 있습니다. DataSet 개체는 같은 스키마를 사용하여 DataGrid의 현재 개체에 붙여 넣어야 합니다. 붙여넣기 작업 전에 다른 위치에서 스키마를 복사해야 합니다. 클릭 하 여 향후 사용에 대 한 데이터 집합 개체를 복사할 수도 있습니다는 **데이터 집합 복사** 단추입니다.  
  
 서비스의 응답은 테스트 매개 변수 아래에 표시됩니다.  
  
> [!NOTE]
>  예상 반환 값이 문자열이면 제공된 입력 값이 따옴표 안에 들어 있지 않은 경우에도 결과는 따옴표로 묶인 문자열로 표시됩니다.  
  
 서비스의 계약을 만들 때 특정 작업을 단방향으로 지정한 경우 서비스 응답이 표시되지 않습니다. 메시지가 배달을 위해 대기 중이면 대화 상자가 표시되어 메시지를 보냈음을 알립니다.  
  
### <a name="session-support"></a>세션 지원  
 합니다 **새 프록시 시작** 서비스 작업 탭에서 확인란을 사용 하면 세션 지원을 설정/해제할 수 있습니다. 이 상자는 기본적으로 선택되어 있지 않습니다.  
  
 특정 작업 (또는 같은 서비스 끝점의 다른 작업)에 대 한 테스트 매개 변수를 입력 하 고 클릭 **Invoke** 여러 번 확인란의 선택을 취소를 사용 하 여 이러한 작업은 하나의 프록시를 공유 하 고 서비스 상태가 여러 작업 간에 유지 합니다.  
  
 경우는 **새 프록시 시작** 확인란이 선택 되어, 각각에 대해 새 프록시 시작 될 **Invoke**, 이전 세션 시나리오는 종료 되며 서비스 상태가 다시 설정 됩니다.  
  
### <a name="editing-client-configuration"></a>클라이언트 구성 편집  
 WCF 테스트 클라이언트 주 창의 왼쪽된 창에는 클라이언트 구성 파일이 나열 됩니다. 이 항목 중 하나를 두 번 클릭하면 오른쪽 창에 파일 내용이 표시됩니다.  
  
#### <a name="edit-with-service-configuration-editor"></a>서비스 구성 편집기로 편집  
 마우스 오른쪽 단추로 클릭 **구성 파일** 왼쪽된 창에서 상황에 맞는 메뉴 선택 **서비스 구성 편집기로 편집**합니다. 서비스 구성 편집기가 시작되어 클라이언트 구성 내용이 표시됩니다. 이 도구 내에서 구성을 편집하고 저장할 수 있습니다.  
  
 WCF 테스트 클라이언트는 서비스 구성 편집기에서 파일을 저장 한 후 파일 외부에서 수정 되었습니다 및 다시 로드 하려는 지 여부를 요청 했음을 알리기 위해 경고 메시지를 표시 합니다.  
  
 선택 하는 경우 **예**, "Client.dll.config" 탭의 구성 내용이 편집기에서 변경한 내용을 반영 합니다.  
  
 선택 하는 경우 **No**"Client.dll.config" 탭의 구성 내용이 그대로 유지 하 고 수정 된 콘텐츠를 자동으로 소스 파일에 저장 됩니다.  
  
#### <a name="restore-to-default-configuration"></a>기본 구성으로 복원  
 모든 변경 내용을 취소 하 고 기본 클라이언트 구성으로 복원, 마우스 오른쪽 단추로 클릭 하려는 경우 **구성 파일** 왼쪽된 창에서 상황에 맞는 메뉴 선택 **기본 구성으로 복원**합니다. 기본 구성 값을 로드 하 고 "Client.dll.config" 탭에서 콘텐츠 복원 됩니다.  
  
#### <a name="validate-changes"></a>변경 내용 확인  
 WCF 테스트 클라이언트에서 로드 되는 변경 내용이 저장된 하는 경우 구성 WCF 스키마에 대해 유효성 확인 됩니다. 오류가 발견되면 오류 정보를 보여 주는 대화 상자가 표시됩니다.  
  
 프록시 생성, 이진 컴파일 또는 서비스 호출 중 편집 (즉, "편집...", "복원..." 등)를 지 원하는 메뉴 항목을 사용 하는 사용할 수 없습니다. 서비스 호출 WCF 테스트 클라이언트를 업데이트 된 구성을 로드 하는 경우에 비활성화 됩니다.  
  
#### <a name="persist-client-configuration"></a>클라이언트 구성 유지  
 합니다 **도구**->**옵션**->**클라이언트 구성을** 탭에는 **항상 다시 생성 구성 하면 시작 서비스** 기본적으로 사용 되는 옵션입니다. 이 옵션에는 WCF 테스트 클라이언트를 서비스 로드 될 때마다 다시 최신 서비스 계약 및 서비스 App.config 파일에 따라 구성 파일을 지정 합니다.  
  
 WCF 서비스에 대 한 클라이언트 구성을 편집한를 항상 선택 취소 하면 서비스를 디버그 하려면이 업데이트 된 파일을 사용 하는 **다시 생성** 옵션입니다. 이렇게 하면 WCF 테스트 클라이언트를 닫고 서비스를 업데이트 하는 경우에 Client.dll.config 파일이 업데이트 된 서비스에 따라 하나를 다시 생성 하는 대신 이전에 업데이트 된 것입니다.  
  
 그러나 다시 생성된 프록시와 일치하도록 구성 파일을 편집해야 할 수 있습니다. 다시 생성된 프록시와 구성 파일이 업데이트된 서비스로 인해 일치하지 않으면 서비스를 호출할 때 오류가 발생합니다.  
  
> [!CAUTION]
>  클라이언트 구성 파일을 수정한 후 나중에 다시 사용하기 위해 선택하는 경우 파일이 다음 위치에 있습니다.  
>   
>  \Documents and 설정을\\[사용자 계정] \My Documents\Test 클라이언트 프로젝트입니다.  
>   
>  클라이언트 구성 파일에 저장된 업데이트된 자격 증명 정보는 ACL(Access Control 목록)을 통해 보호됩니다.  
  
### <a name="adding-removing-and-refreshing-services"></a>서비스 추가, 제거 및 새로 고침  
  
#### <a name="add-service"></a>서비스 추가  
 클릭 **파일**->**서비스 추가** WCF 테스트 클라이언트 서비스를 추가 합니다. 그런 다음 추가할 서비스의 URI(엔드포인트 주소)를 입력해야 합니다. 서비스 주소는 mex 주소나 WSDL 주소일 수 있습니다.  
  
 10 최근에 추가 된 서비스 끝점의 목록을 수도 있습니다는 **최근 서비스** 하위 메뉴. 그 중 하나를 선택 하면 지정된 된 서비스는 WCF 테스트 클라이언트에 추가 됩니다.  
  
 서비스 트리의 루트를 마우스 오른쪽 단추로 클릭 **내 서비스 프로젝트**, 선택한 **서비스 추가** 동일한 결과 얻을 수 있습니다.  
  
 프록시 생성, 이진 컴파일 또는 서비스 호출 도중에는 서비스 편집을 지원하는 메뉴 항목을 사용할 수 없습니다. 서비스 호출도 비활성화됩니다.  
  
#### <a name="remove-service"></a>서비스 제거  
 선택한 제거할 서비스의 서비스 루트를 마우스 오른쪽 단추로 클릭 **서비스에서 제거** WCF 테스트 클라이언트에서 서비스를 제거 합니다.  
  
 프록시 생성, 이진 컴파일 또는 서비스 호출 도중에는 서비스 제거를 지원하는 메뉴 항목을 사용할 수 없습니다. 서비스 호출도 비활성화됩니다.  
  
#### <a name="refresh-service"></a>서비스 새로 고침  
 변경 하려고 하면 서비스 WCF 테스트 클라이언트가 실행 되 고 해당 서비스에 대 한 WCF 테스트 클라이언트 구현이 최신 상태 인지 확인 하려면, 선택한 서비스의 서비스 루트를 마우스 오른쪽 단추로 클릭 **서비스 새로 고침**합니다. 서비스를 새로 고친 한 서비스 상태는 다시 설정됩니다.  
  
 프록시 생성, 이진 컴파일 또는 서비스 호출 도중에는 서비스 새로 고침을 지원하는 메뉴 항목을 사용할 수 없습니다. 서비스 호출도 비활성화됩니다.  
  
## <a name="location-of-files-generated-by-the-test-client"></a>테스트 클라이언트에서 생성한 파일의 위치  
 기본적으로 WCF 테스트 클라이언트 저장소 "%appdata%\Local\temp\Test Client Projects" 폴더에서 클라이언트 코드 및 구성 파일을 생성 합니다. WCF 테스트 클라이언트 종료 된 후이 폴더는 삭제 됩니다. WCF 테스트 클라이언트에서 구성 파일을 수정할 경우와 **다시 생성 구성 서비스 시작 시 항상** 옵션 기능을 해제 하면 수정된 된 파일은 "My Documents\Test Client Projects" 아래의 "CachedConfig" 폴더에 복사 인덱스로 매핑 (메타 데이터 주소-에-파일 이름 간) XML 파일입니다.  
  
 명령줄에서 사용 하 여 WCF 테스트 클라이언트를 시작할 수도 있습니다는 `/ProjectPath` 생성 된 파일을 저장 하는 것에 대 한 새 경로 지정으로 전환 하거나 사용 하 여는 `/RestoreProjectPath` 기본 위치를 복원 하는 스위치입니다. 구문은 다음과 같습니다.  
  
 `wcfTestClient.exe /ProjectPath [desired location]`  
  
 이 명령을 실행 하면 WCF 테스트 클라이언트가 열리지 않습니다. 폴더 위치만 변경됩니다. WCF 테스트 클라이언트 실행 되는지에 상관 없이이 명령을 실행할 수 있습니다. 새 위치는 WCF 테스트 클라이언트를 다시 시작할 때 적용 됩니다. 레지스트리 나 "%appdata%\Local\temp\Test Client Projects" 폴더의 WcfTestClient.exe.option 파일에 위치 정보를 저장할 수 있습니다.  
  
## <a name="features-supported-by-wcf-test-client"></a>WCF 테스트 클라이언트에서 지원되는 기능  
 다음은 WCF 테스트 클라이언트에서 지 원하는 기능 목록입니다.  
  
- 서비스 호출: 요청/응답 및 단방향 메시지입니다.  
  
- 바인딩: Svcutil.exe에서 지원되는 모든 바인딩.  
  
- 세션 제어  
  
- 메시지 계약  
  
- XML 직렬화  
  
 다음은 WCF 테스트 클라이언트에서 지원 되지 않는 기능 목록을입니다.  
  
- 형식: <xref:System.IO.Stream>, <xref:System.ServiceModel.Channels.Message>, <xref:System.Xml.XmlElement>, <xref:System.Xml.XmlAttribute>, <xref:System.Xml.XmlNode>, <xref:System.Xml.Serialization.IXmlSerializable> 인터페이스를 구현하는 형식(관련 <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> 특성 포함), <xref:System.Xml.Linq.XDocument> 및 <xref:System.Xml.Linq.XElement> 형식, ADO.NET <xref:System.Data.DataTable> 형식  
  
- 이중 계약  
  
- 트랜잭션  
  
- 보안: CardSpace, 인증서 및 사용자 이름/암호입니다.  
  
- 바인딩: WSFederationbinding, Context 바인딩 및 Https 바인딩, WebHttpbinding (Json 응답 메시지 지원).  
  
## <a name="closing-wcf-test-client"></a>WCF 테스트 클라이언트 닫기  
 다음과 같은 방법으로 WCF 테스트 클라이언트를 닫을 수 있습니다.  
  
- **파일** 메뉴에서 **끝내기**를 클릭합니다. 또는 WCF 테스트 클라이언트 주 창에서 클릭 **닫기**합니다. 이러한 작업의 또한 WCF 서비스 자동 호스트 종료와 Visual Studio에서 WCF 테스트 클라이언트를 시작한 경우 Visual Studio 디버깅 프로세스를 중지 합니다.  
  
- 마우스 오른쪽 단추로 클릭 합니다 **WCF 서비스 호스트가** 클릭 한 다음 확인 하 고 알림 영역 아이콘 **종료 합니다.** 이 WCF 서비스 자동 호스트와 WCF 테스트 클라이언트를 종료 하 고 Visual Studio 디버깅 프로세스를 중지 합니다.  
  
## <a name="see-also"></a>참고자료

- [WCF 서비스 호스트(WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
