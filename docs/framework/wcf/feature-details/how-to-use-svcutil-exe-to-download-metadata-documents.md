---
title: '방법: Svcutil.exe를 사용하여 메타데이터 문서 다운로드'
description: Svcutil.exe를 사용 하 여 실행 중인 서비스에서 메타 데이터를 다운로드 하 고 로컬 파일에 메타 데이터를 저장 하는 방법을 알아봅니다.
ms.date: 03/30/2017
ms.assetid: 15524274-3167-4627-b722-d6cedb9fa8c6
ms.openlocfilehash: 449dd3023b5d688ed0de22e3651cccf16bee0c52
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280678"
---
# <a name="how-to-use-svcutilexe-to-download-metadata-documents"></a>방법: Svcutil.exe를 사용하여 메타데이터 문서 다운로드

Svcutil.exe를 사용하면 실행 중인 서비스에서 메타데이터를 다운로드하여 로컬 파일에 저장할 수 있습니다. HTTP 및 HTTPS URL 스키마의 경우 Svcutil.exe WS-MetadataExchange 및 [XML Web Services 검색](/previous-versions/dotnet/netframework-4.0/fxx6cfx2(v=vs.100))을 사용 하 여 메타 데이터 검색을 시도 합니다. 기타 URL 스키마의 경우 Svcutil.exe에서 WS-MetadataExchange만 사용합니다.  
  
 기본적으로 Svcutil.exe는 <xref:System.ServiceModel.Description.MetadataExchangeBindings> 클래스에 정의된 바인딩을 사용합니다. WS-MetadataExchange에 사용되는 바인딩을 구성하려면 `IMetadataExchange` 계약을 사용하고 메타데이터 엔드포인트 주소의 URI(Uniform Resource Identifier) 스키마와 이름이 같은 Svcutil.exe(svcutil.exe.config)의 구성 파일에서 클라이언트 엔드포인트를 정의해야 합니다.  
  
> [!CAUTION]
> Svcutil.exe를 실행 하 여 각각 같은 이름의 작업을 포함 하는 두 개의 서로 다른 서비스 계약을 노출 하는 서비스에 대 한 메타 데이터를 가져오는 경우, Svcutil.exe에서 "메타 데이터를 가져올 수 없습니다." 라는 오류 메시지가 표시 됩니다. 예를 들어, 작업을 포함 하는 라는 서비스 계약을 노출 하는 서비스가 있고 `ICarService` `Get(Car c)` 동일한 서비스에서 `IBookService` 작업을 포함 하는 라는 서비스 계약을 노출 `Get(Book b)` 하는 경우 이 문제를 해결하려면 다음 중 하나를 수행합니다.
>
> - 작업 중 하나의 이름을 바꿉니다.
> - <xref:System.ServiceModel.OperationContractAttribute.Name%2A>을 다른 이름으로 설정합니다.
> - <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> 속성을 사용하여 작업 중 하나의 네임스페이스를 다른 네임스페이스로 설정합니다.
  
## <a name="to-download-metadata-using-svcutilexe"></a>Svcutil.exe를 사용하여 메타데이터를 다운로드하려면  
  
1. 다음 위치에서 Svcutil.exe 도구를 찾습니다.  
  
     C:\Program Files\Microsoft SDKs\Windows\v1.0.\bin  
  
2. 명령 프롬프트에서 다음 형식을 사용하여 이 도구를 실행합니다.  
  
    ```console
    svcutil.exe /t:metadata  <url>* | <epr>  
    ```  
  
     메타데이터를 다운로드하려면 `/t:metadata` 옵션을 지정해야 합니다. 그렇지 않으면 클라이언트 코드와 구성이 생성됩니다.  
  
3. <`url`>인수는 메타 데이터를 제공 하는 서비스 끝점의 URL 또는 온라인으로 호스팅되는 메타 데이터 문서를 지정 합니다. <`epr`> 인수는 `EndpointAddress` WS-ws-metadataexchange를 지 원하는 서비스 끝점에 대 한 WS-Addressing를 포함 하는 XML 파일의 경로를 지정 합니다.  
  
 메타 데이터 다운로드에이 도구를 사용 하는 방법에 대 한 자세한 옵션은 [ServiceModel Metadata Utility tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)을 참조 하세요.  
  
## <a name="example"></a>예제  

 다음 명령은 실행 중인 서비스에서 메타데이터 문서를 다운로드합니다.  
  
```console
svcutil /t:metadata http://service/metadataEndpoint  
```  
  
## <a name="see-also"></a>참고 항목

- [ServiceModel Metadata 유틸리티 도구(Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)
