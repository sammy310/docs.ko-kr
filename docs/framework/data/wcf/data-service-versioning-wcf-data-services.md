---
title: 데이터 서비스 버전 관리(WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- versioning, WCF Data Services
- versioning [WCF Data Services]
- WCF Data Services, versioning
ms.assetid: e3e899cc-7f25-4f67-958f-063f01f79766
ms.openlocfilehash: f82ab4c98e724bbed658a6c77de9c5a5d5c3390f
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121533"
---
# <a name="data-service-versioning-wcf-data-services"></a>데이터 서비스 버전 관리(WCF Data Services)
OData(개방형 데이터 프로토콜)를 사용하면 클라이언트가 데이터 모델을 기반으로 하는 URI를 사용하여 리소스로 데이터에 액세스할 수 있도록 데이터 서비스를 만들 수 있습니다. OData는 서비스 작업의 정의도 지원합니다. 이러한 데이터 서비스는 비즈니스 요구 사항의 변경, 정보 기술의 요구 사항 또는 다른 문제 해결 등의 다양한 이유 때문에 최초로 배포된 후, 수명 동안 여러 차례에 걸쳐 변경되어야 할 수 있습니다. 기존 데이터 서비스를 변경한 경우 새 버전의 데이터 서비스를 정의할 것인지 그리고 기존 클라이언트 애플리케이션에 미치는 영향을 최소화할 최선의 방법을 고려해야 합니다. 이 항목에서는 새 버전의 데이터 서비스를 만드는 방법 및 시기에 대한 지침을 제공합니다. 또한 WCF 데이터 서비스가 다양한 버전의 OData 프로토콜을 지원하는 클라이언트와 데이터 서비스 간의 교환을 처리하는 방법에 대해서도 설명합니다.

## <a name="versioning-a-wcf-data-service"></a>WCF Data Service 버전 관리
 데이터 서비스를 배포한 후 데이터가 사용되고 있을 때 데이터 서비스를 변경하면 기존 클라이언트 애플리케이션에 호환성 문제가 나타날 수 있습니다. 하지만 서비스의 전반적 비즈니스 요구 사항으로 인해 변경이 필요한 경우가 많기 때문에 클라이언트 애플리케이션에 가장 적은 영향을 미치면서 데이터 서비스의 새 버전을 만들 시기와 방법을 고려해야 합니다.

### <a name="data-model-changes-that-recommend-a-new-data-service-version"></a>새 데이터 서비스 버전을 권장하는 데이터 모델 변경
 데이터 서비스의 새로운 버전을 게시할 것인지를 고려할 때에는 다른 종류의 변경이 클라이언트 애플리케이션에 어떻게 영향을 미칠 것인가를 이해하는 것이 중요합니다. 데이터 서비스의 새로운 버전을 만들어야 할 수 있는 데이터 서비스 변경은 다음 두 가지 범주로 나눌 수 있습니다.

- 서비스 계약 변경 - 서비스 작업 업데이트, 엔터티 집합(피드)의 액세스 가능성 변경, 버전 변경, 기타 서비스 동작 변경이 포함됩니다.

- 데이터 계약 변경 - 데이터 모델 또는 피드 형식 변경이나 피드 사용자 지정이 포함됩니다.

 다음 표에는 새 버전의 데이터 서비스를 게시할 때 고려해야 하는 변경의 종류가 자세히 나와 있습니다.

|변경 형식|새 버전 필요|새 버전이 필요하지 않음|
|--------------------|----------------------------|----------------------------|
|서비스 작업|- 새 매개 변수 추가<br />- 변경 반환 유형<br />- 서비스 운영 제거|- 기존 매개 변수 삭제<br />- 새로운 서비스 운영 추가|
|서비스 동작|- 카운트 요청을 비활성화<br />- 프로젝션 지원 비활성화<br />- 필요한 데이터 서비스 버전을 증가|- 카운트 요청을 활성화<br />- 프로젝션 지원 활성화<br />- 필요한 데이터 서비스 버전 감소|
|엔터티 집합 권한|- 엔터티 세트 사용 권한 제한<br />- 변경 응답 코드 (새로운 첫 번째 숫자 값) <sup>1</sup>|- 완화 엔티티 세트 권한<br />- 변경 응답 코드 (동일한 첫 번째 숫자 값)|
|엔터티 속성|- 기존 속성 또는 관계 제거<br />- 무효 속성 추가<br />- 기존 속성 변경|- 무효 속성<sup>추가 2</sup>|
|엔터티 집합|- 엔터티 집합 제거|- 파생 된 유형 추가<br />- 기본 유형 변경<br />- 엔터티 집합 추가|
|피드 사용자 지정|- 엔터티-속성 매핑 변경||

 <sup>1</sup> 클라이언트 응용 프로그램이 특정 오류 코드를 수신하는 데 얼마나 엄격하게 의존하는지에 따라 달라질 수 있습니다.

 <sup>2</sup> 클라이언트에 <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A> 정의되지 `true` 않은 데이터 서비스에서 전송된 새 속성을 무시하도록 속성을 설정할 수 있습니다. 그러나 삽입이 수행되면 클라이언트에 의해 POST 요청에 포함되지 않은 속성이 기본값으로 설정됩니다. 업데이트의 경우 클라이언트에 알려지지 않은 속성의 모든 기존 데이터는 기본값으로 덮어쓰여질 수 있습니다. 이 경우 업데이트를 기본값인 MERGE 요청으로 보내야 합니다. 자세한 내용은 [데이터 서비스 컨텍스트 관리를](managing-the-data-service-context-wcf-data-services.md)참조하십시오.

### <a name="how-to-version-a-data-service"></a>데이터 서비스 버전을 관리하는 방법
 필요한 경우 업데이트된 서비스 계약 또는 데이터 모델로 서비스의 새 인스턴스를 만들어 새 데이터 서비스 버전을 정의할 수 있습니다. 그런 다음 이 새로운 서비스는 이전 버전과 차별화하는 새 URI 엔드포인트를 사용하여 노출됩니다. 다음은 그 예입니다.

- 이전 버전: `http://services.odata.org/Northwind/v1/Northwind.svc/`

- 새 버전: `http://services.odata.org/Northwind/v2/Northwind.svc/`

 또한 데이터 서비스를 업그레이드 하는 경우 새 데이터 서비스 메타데이터를 기반으로 클라이언트를 업데이트해야 하고 클라이언트에서 새 루트 URI를 사용해야 합니다. 가능한 경우, 아직 업그레이드되지 않아 새 버전을 사용하지 않는 클라이언트를 지원할 수 있도록 이전 버전의 데이터 서비스를 유지해야 합니다. 이전 버전의 데이터 서비스가 더 이상 필요하지 않으면 제거할 수 있습니다. 외부 구성 파일에 데이터 서비스 엔드포인트의 URI를 유지하는 것을 고려해야 합니다.

## <a name="odata-protocol-versions"></a>OData 프로토콜 버전
 새 버전의 OData가 릴리스되면 클라이언트 응용 프로그램이 데이터 서비스에서 지원하는 동일한 버전의 OData 프로토콜을 사용하지 않을 수 있습니다. 이전 클라이언트 응용 프로그램은 최신 버전의 OData를 지원하는 데이터 서비스에 액세스할 수 있습니다. 클라이언트 응용 프로그램은 액세스중인 데이터 서비스보다 최신 버전의 OData를 지원하는 WCF 데이터 서비스 클라이언트 라이브러리의 최신 버전을 사용할 수도 있습니다.

 WCF 데이터 서비스는 OData에서 제공하는 지원을 활용하여 이러한 버전 관리 시나리오를 처리합니다. 또한 클라이언트가 데이터 서비스에서 사용하는 것과 다른 버전의 OData를 사용할 때 데이터 모델 메타데이터를 생성하고 사용하여 클라이언트 데이터 서비스 클래스를 만드는 지원도 있습니다. 자세한 내용은 [OData: 개요](https://www.odata.org/documentation/odata-version-2-0/overview/) 문서의 프로토콜 버전 버전 섹션을 참조하십시오.

### <a name="version-negotiation"></a>버전 협상
 데이터 서비스는 클라이언트가 요청한 버전에 관계없이 서비스에서 사용할 OData 프로토콜의 가장 높은 버전을 정의하도록 구성할 수 있습니다. 데이터 서비스에서 <xref:System.Data.Services.Common.DataServiceProtocolVersion> <xref:System.Data.Services.DataServiceBehavior.MaxProtocolVersion%2A> <xref:System.Data.Services.DataServiceBehavior> 사용하는 속성에 대한 값을 지정하여 이 작업을 수행할 수 있습니다. 자세한 내용은 [데이터 서비스 구성](configuring-the-data-service-wcf-data-services.md)합니다.

 응용 프로그램이 WCF 데이터 서비스 클라이언트 라이브러리를 사용하여 데이터 서비스에 액세스하는 경우 라이브러리는 OData 버전 및 응용 프로그램에서 사용되는 기능에 따라 이러한 헤더를 올바른 값으로 자동으로 설정합니다. 기본적으로 WCF 데이터 서비스는 요청된 작업을 지원하는 가장 낮은 프로토콜 버전을 사용합니다.

 다음 표는 OData 프로토콜의 특정 버전에 대한 WCF 데이터 서비스 지원을 포함하는 .NET Framework 및 Silverlight 버전에 대해 자세히 설명합니다.

|OData 프로토콜 버전|도입된 지원|
|-----------------------------------------------------------------------------------|----------------------------|
|버전 1|- .NET 프레임워크 3.5 서비스 팩 1(SP1)<br />- 실버 라이트 버전 3|
|버전 2|- .NET 프레임워크 4<br />- 실버 라이트 버전 4|

### <a name="metadata-versions"></a>메타데이터 버전
 기본적으로 WCF 데이터 서비스는 CSDL 버전 1.1을 사용하여 데이터 모델을 나타냅니다. 이는 리플렉션 공급자 또는 사용자 지정 데이터 서비스 공급자를 기반으로 하는 데이터 모델의 경우 항상 해당됩니다. 그러나 데이터 모델이 Entity Framework를 사용하여 정의된 경우 반환된 CSDL 버전은 Entity Framework에서 사용되는 버전과 동일합니다. CSDL 버전은 [CSDL(스키마 요소)의](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#schema-element-csdl)네임스페이스에 의해 결정됩니다.

 반환된 메타데이터의 `DataServices` 요소에는 응답 메시지의 `DataServiceVersion` 헤더와 값이 동일한 `DataServiceVersion` 특성도 포함되어 있습니다. Visual Studio의 서비스 **참조 추가** 대화 상자와 같은 클라이언트 응용 프로그램은 이 정보를 사용하여 데이터 서비스를 호스트하는 WCF 데이터 서비스 버전에서 올바르게 작동하는 클라이언트 데이터 서비스 클래스를 생성합니다. 자세한 내용은 [OData: 개요](https://www.odata.org/documentation/odata-version-2-0/overview/) 문서의 프로토콜 버전 버전 섹션을 참조하십시오.

## <a name="see-also"></a>참조

- [Data Services 공급자](data-services-providers-wcf-data-services.md)
- [WCF Data Services 정의](defining-wcf-data-services.md)
