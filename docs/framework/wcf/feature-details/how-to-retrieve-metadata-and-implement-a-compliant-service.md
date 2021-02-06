---
description: '방법: 메타 데이터 검색 및 규격 서비스 구현에 대 한 자세한 정보'
title: '방법: 메타데이터 검색 및 규정 준수 서비스 구현'
ms.date: 03/30/2017
ms.assetid: f6f3a2b9-c8aa-4b0b-832c-ec2927bf1163
ms.openlocfilehash: f9af65115fa4d60faa332159ccd99319a916bc73
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99643412"
---
# <a name="how-to-retrieve-metadata-and-implement-a-compliant-service"></a>방법: 메타데이터 검색 및 규정 준수 서비스 구현

서비스를 디자인하는 사람과 구현하는 사람이 다른 경우가 많습니다. 상호 운용하는 애플리케이션이 중요한 환경에서는 WSDL(웹 서비스 기술 언어)로 계약을 디자인하거나 설명할 수 있으며 개발자는 제공된 계약에 따라 서비스를 구현해야 합니다. 기존 서비스를 Windows Communication Foundation (WCF)로 마이그레이션할 수는 있지만 통신 형식은 유지 하려고 할 수도 있습니다. 또한 이중 계약에서는 호출자가 콜백 계약도 구현해야 합니다.  
  
 이러한 경우에는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) (또는 동등한 도구)를 사용 하 여 계약 요구 사항을 충족 하기 위해 구현할 수 있는 관리 언어로 서비스 계약 인터페이스를 생성 해야 합니다. 일반적으로 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) 는 채널 팩터리 또는 WCF 클라이언트 형식과 함께 사용 되는 서비스 계약과 올바른 바인딩과 주소를 설정 하는 클라이언트 구성 파일을 가져오는 데 사용 됩니다. 생성된 구성 파일을 사용하려면 해당 파일을 서비스 구성 파일로 변경해야 합니다. 서비스 계약을 수정해야 할 수도 있습니다.  
  
### <a name="to-retrieve-data-and-implement-a-compliant-service"></a>데이터 검색 및 규격 서비스 구현  
  
1. 메타 데이터 파일 또는 메타 데이터 끝점에 대해 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) 를 사용 하 여 코드 파일을 생성 합니다.  
  
2. <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType> 특성으로 표시된 필요한 인터페이스(두 개 이상 있는 경우)를 포함하는 출력 코드 파일 부분을 검색합니다. 다음 코드 예제에서는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)에서 생성 된 두 인터페이스를 보여 줍니다. 첫 번째(`ISampleService`)는 규격 서비스를 만들기 위해 구현하는 서비스 계약 인터페이스입니다. 두 번째(`ISampleServiceChannel`)는 서비스 계약 인터페이스 및 <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>을 모두 확장하는 클라이언트와 클라이언트 애플리케이션에 사용하기 위한 도우미 인터페이스입니다.  
  
     [!code-csharp[ClientProxyCodeSample#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/proxycode.cs#2)]  
  
3. WSDL에서 모든 작업에 대한 회신 동작을 지정하지 않으면 생성되는 작업 계약에서 <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> 속성이 와일드카드 문자(*)로 설정될 수 있습니다. 이 속성 설정을 제거합니다. 그렇지 않으면 서비스 계약 메타데이터를 구현할 때 해당 작업에 대해 메타데이터를 내보낼 수 없습니다.  
  
4. 클래스에서 인터페이스를 구현하고 서비스를 호스트합니다. 예제를 보려면 [방법: 서비스 계약 구현](../how-to-implement-a-wcf-contract.md)을 참조 하거나 아래 예제 섹션에서 간단한 구현을 참조 하세요.  
  
5. [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) 가 생성 하는 클라이언트 구성 파일에서 구성 섹션 [\<client>](../../configure-apps/file-schema/wcf/client.md) 을 구성 섹션으로 변경 합니다 [\<services>](../../configure-apps/file-schema/wcf/services.md) . 생성되는 클라이언트 애플리케이션 구성 파일의 예제를 보려면 다음 &quot;예제&quot; 단원을 참조하세요.  
  
6. [\<services>](../../configure-apps/file-schema/wcf/services.md)구성 섹션 내에서 `name` [\<services>](../../configure-apps/file-schema/wcf/services.md) 서비스 구현에 대 한 특성을 구성 섹션에 만듭니다.  
  
7. 서비스 `name` 특성을 서비스 구현을 위한 구성 이름으로 설정합니다.  
  
8. 구현된 서비스 계약을 사용하는 엔드포인트 구성 요소를 서비스 구성 섹션에 추가합니다.  
  
## <a name="example"></a>예제  

 다음 코드 예제에서는 데이터 파일에 대해 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) 를 실행 하 여 생성 된 대부분의 코드 파일을 보여 줍니다.  
  
 코드 내용은 다음과 같습니다.  
  
- 계약 요구 사항을 준수하는 서비스 계약 인터페이스(구현된 경우)(`ISampleService`).  
  
- 서비스 계약 인터페이스와 <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>을 모두 확장하는 클라이언트와 클라이언트 애플리케이션에 사용하기 위한 도우미 인터페이스(`ISampleServiceChannel`)  
  
- <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>를 확장하고 클라이언트 애플리케이션에 사용하기 위한 도우미 클래스(`SampleServiceClient`)  
  
- 서비스에서 생성된 구성 파일  
  
- 간단한 `ISampleService` 서비스 구현  
  
- 클라이언트측 구성 파일을 서비스측 버전으로 변환  
  
[!code-csharp[ClientProxyCodeSample#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/proxycode.cs#1)]

[!code-xml[ClientProxyCodeSample#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/client.exe.config#10)]

[!code-csharp[ClientProxyCodeSample#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/hostapplication.cs#5)]

[!code-xml[ClientProxyCodeSample#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/hostapplication.exe.config#20)]
  
## <a name="see-also"></a>참고 항목

- [ServiceModel Metadata 유틸리티 도구(Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)
