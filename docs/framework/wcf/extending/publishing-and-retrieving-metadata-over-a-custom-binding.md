---
title: 사용자 지정 바인딩을 통해 메타데이터 게시 및 검색
ms.date: 03/30/2017
ms.assetid: 904e11b4-d90e-45c6-9ee5-c3472c90008c
ms.openlocfilehash: 33777358262465e9ecbadd75df8abf066bafcd01
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991213"
---
# <a name="publishing-and-retrieving-metadata-over-a-custom-binding"></a>사용자 지정 바인딩을 통해 메타데이터 게시 및 검색
<xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType>에서는 메타데이터 엔드포인트를 서비스에 추가할 수 있도록 지원합니다. 이러한 메타 데이터 끝점에 있는 URL에 HTTP GET 요청에 응답할 수는 `?wsdl` querystring 및 Ws-metadataexchange (MEX) 사양에 정의 된 대로 Ws-transfer GET 요청을 합니다. MEX 엔드포인트는 <xref:System.ServiceModel.Description.IMetadataExchange?displayProperty=nameWithType> 계약을 구현합니다.  
  
## <a name="publishing-metadata-over-a-custom-binding"></a>사용자 지정 바인딩을 통해 메타데이터 게시  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A?displayProperty=nameWithType> 또는 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A?displayProperty=nameWithType> 속성을 `true`로 설정하여 HTTP GET 메타데이터 엔드포인트 및 HTTPS GET 메타데이터 엔드포인트를 사용할 수 있습니다. 이러한 엔드포인트에 대한 바인딩은 구성할 수 없습니다.  
  
 그러나 합니다 <xref:System.ServiceModel.Description.IMetadataExchange> 를 포함 하 여 사용자 지정 바인딩을 사용 하므로 모든 끝점을 사용 하 여 계약 수 <xref:System.ServiceModel.Description.IMetadataExchange> 끝점은 다른 Windows Communication Foundation (WCF) 서비스 끝점에 동일 합니다. 시스템 제공 바인딩의 구성을 수정하는 방법을 알고 있거나 <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>을 구성하는 방법을 알고 있는 경우 <xref:System.ServiceModel.Description.IMetadataExchange> 엔드포인트에 사용할 바인딩을 구성할 수 있습니다.  
  
## <a name="retrieving-metadata-over-a-custom-binding"></a>사용자 지정 바인딩을 통해 메타데이터 검색  
 표준 HTTP 또는 HTTPS GET 요청을 사용하여 HTTP Get 및 HTTPS Get 메타데이터 엔드포인트에서 메타데이터를 검색할 수 있습니다.  
  
 MEX 메타 데이터 끝점에서 메타 데이터를 검색 하려면 일반적으로 WCF에서 지 원하는 표준 MEX 바인딩 중 하나 사용 수 있습니다. 자세한 내용은 <xref:System.ServiceModel.Description.MetadataExchangeBindings?displayProperty=nameWithType>을 참조하세요. <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> 형식 및 Svcutil.exe 도구에서는 지정된 메타데이터 엔드포인트의 주소에 따라 이러한 표준 MEX 바인딩 중 하나를 자동으로 선택합니다.  
  
 MEX 메타데이터 엔드포인트에서 표준 MEX 바인딩과 다른 바인딩을 사용하는 경우 코드를 사용하거나 <xref:System.ServiceModel.Description.MetadataExchangeClient> 클라이언트 엔드포인트 구성을 제공하여 <xref:System.ServiceModel.Description.IMetadataExchange>에서 사용하는 바인딩을 구성할 수 있습니다. Svcutil.exe 도구는 메타데이터 엔드포인트 주소의 URI 스키마와 이름이 같은 <xref:System.ServiceModel.Description.IMetadataExchange> 클라이언트 엔드포인트 구성을 구성 파일에서 자동으로 로드합니다.  
  
## <a name="security"></a>보안  
 사용자 지정 바인딩을 통해 메타데이터를 게시하는 경우 바인딩에서 메타데이터가 필요로 하는 보안 지원을 제공하는지 확인합니다. 예를 들어, 정보 공개를 방지하고 클라이언트에 메타데이터를 가져올 권한이 있는지 확인하려면 인증 및 암호화가 필요한 <xref:System.ServiceModel.Description.IMetadataExchange> 엔드포인트를 구성하여 메타데이터 및 응용 프로그램의 보안을 더욱 향상시킬 수 있습니다. 샘플 [사용자 지정 보안 메타 데이터 끝점](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) 이 시나리오를 보여 줍니다.  
  
## <a name="see-also"></a>참고자료

- [서비스에 보안 설정](../../../../docs/framework/wcf/securing-services.md)
- [WS-MetadataExchange 바인딩](../../../../docs/framework/wcf/extending/ws-metadataexchange-bindings.md)
- [방법: 구성 사용자 지정 Ws-metadata Exchange 바인딩](../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)
- [방법: 가 아닌-MEX 바인딩을 통해 메타 데이터를 검색 합니다.](../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)
