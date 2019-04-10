---
title: WCF Data Services 프로토콜 구현 정보
ms.date: 03/30/2017
ms.assetid: 712d689b-fada-4cbb-bcdb-d65a3ef83b4c
ms.openlocfilehash: 3fcef8778707f2bac68755762143f4a7528f0bf1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59152856"
---
# <a name="wcf-data-services-protocol-implementation-details"></a>WCF Data Services 프로토콜 구현 정보
## <a name="odata-protocol-implementation-details"></a>OData 프로토콜 구현 정보  
 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]에서는 프로토콜을 구현하는 데이터 서비스가 최소한의 기능 집합을 제공해야 합니다. 이러한 기능은 "should" 및 "must" 측면에서 프로토콜 문서에 설명 되어 있습니다. 기타 선택적 기능은 "may"로 지정 합니다. 측면에서 설명 이 항목에서는 현재 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에서 구현되지 않은 이러한 선택적 기능에 대해 설명합니다. 자세한 내용은 [OData 프로토콜 설명서](https://go.microsoft.com/fwlink/?LinkID=184554)합니다.  
  
### <a name="support-for-the-format-query-option"></a>$format 쿼리 옵션 지원  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 프로토콜은 JSON(JavaScript Notation)과 Atom 피드를 둘 다 지원하고, [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]는 클라이언트에서 응답 피드의 형식을 요청할 수 있도록 `$format` 시스템 쿼리 옵션을 제공합니다. 이 시스템 쿼리 옵션은 데이터 서비스에서 지원하는 경우 요청의 Accept 헤더 값을 재정의해야 합니다. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] JSON 및 Atom 피드를 반환을 지원 합니다. 그러나 기본 구현은 `$format` 쿼리 옵션을 지원하지 않고 Accept 헤더 값만 사용하여 응답 형식을 결정합니다. 클라이언트가 Accept 헤더를 설정할 수 없는 경우와 같이 데이터 서비스가 `$format` 쿼리 옵션을 지원해야 하는 경우가 있습니다. 이러한 시나리오를 지원하려면 URI에서 이 옵션을 처리하도록 데이터 서비스를 확장해야 합니다. 다운로드 하 여 데이터 서비스에이 기능을 추가할 수 있습니다 합니다 [ADO.NET Data Services에 대 한 JSONP 및 URL 제어 형식 지원](https://go.microsoft.com/fwlink/?LinkId=208228) 샘플 프로젝트는 MSDN 코드 갤러리 웹 사이트 및 데이터 서비스 프로젝트에 추가 합니다. 이 샘플은 `$format` 쿼리 옵션을 제거하고 Accept 헤더를 `application/json`으로 변경합니다. 샘플 프로젝트를 포함하고 데이터 서비스에 `JSONPSupportBehaviorAttribute`를 추가하면 서비스에서 `$format` 쿼리 옵션 `$format=json`을 처리할 수 있습니다. `$format=atom` 또는 다른 사용자 지정 형식도 처리하려면 이 샘플 프로젝트를 추가로 사용자 지정해야 합니다.  
  
## <a name="wcf-data-services-behaviors"></a>WCF Data Services 동작  
 다음 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 동작은 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 프로토콜에 의해 명시적으로 정의되지 않습니다.  
  
### <a name="default-sorting-behavior"></a>기본 정렬 동작  
 데이터 서비스에 전송되는 쿼리 요청에 `$top` 또는 `$skip` 시스템 쿼리 옵션이 포함되어 있고 `$orderby` 시스템 쿼리 옵션이 없는 경우 반환된 피드가 키 속성을 기준으로 오름차순으로 정렬됩니다. 그 이유는 결과의 올바른 페이징을 보장하기 위해 정렬이 필요하기 때문입니다. 이를 위해 데이터 서비스가 쿼리에 정렬 식을 추가합니다. 이 동작은 데이터 서비스에 서버 기반 페이징이 활성화된 경우에도 발생합니다. 자세한 내용은 [데이터 서비스 구성](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)합니다. 반환 된 피드의 순서를 제어 하려면 포함 해야 `$orderby` 쿼리 URI에에서 있습니다.  
  
## <a name="see-also"></a>참고자료

- [WCF Data Services 정의](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
- [WCF Data Services 클라이언트 라이브러리](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
