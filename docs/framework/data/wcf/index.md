---
title: WCF Data Services 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: 6910bfbc94f69292bb8c2a52bf3ebef8fcfb3a8a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61876462"
---
# <a name="wcf-data-services-45"></a>WCF Data Services 4.5

WCF Data Services (이전의 "ADO.NET Data Services")를 사용 하는 서비스를 만들 수 있도록.NET Framework의 구성 요소인 합니다 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] 노출 하 고의 의미 체계를 사용 하 여 웹 또는 인트라넷을 통해 데이터를 사용 [ (REST) representational state transfer](https://go.microsoft.com/fwlink/?LinkId=113919)합니다. OData는 URI로 주소를 지정할 수 있는 리소스로 데이터를 노출합니다. 데이터는 표준 HTTP 동사인 GET, PUT, POST 및 DELETE를 사용하여 액세스되고 변경됩니다. OData의 엔터티-관계 규칙을 사용 합니다 [엔터티 데이터 모델](../../../../docs/framework/data/adonet/entity-data-model.md) 리소스 연결으로 관련 된 엔터티 집합으로 노출 합니다.

WCF Data Services 주소 지정 및 업데이트 리소스에 대 한 OData 프로토콜을 사용 합니다. 따라서에서 이러한 서비스를 OData를 지 원하는 모든 클라이언트에서 액세스할 수 있습니다. OData를 사용 하면 요청 하 고 잘 알려진 전송 형식을 사용 하 여 리소스에 데이터를 쓸 수 있습니다. Atom, 교환 및 개체 JSON (JavaScript Notation), XML로 데이터를 업데이트 하기 위한 표준 집합인 AJAX 응용 프로그램에서 광범위 하 게 사용 하는 텍스트 기반 데이터 교환 형식입니다.

WCF Data Services는 OData 피드로 다양 한 원본에서 제공 되는 데이터를 노출할 수 있습니다. Visual Studio tools 쉽게 ADO.NET Entity Framework 데이터 모델을 사용 하 여 OData 기반 서비스를 만들 수 있습니다. 또한 공용 언어 런타임 (CLR) 클래스와도 런타임에 바인딩된 데이터 나 형식화 되지 않은 데이터에 따라 OData 피드를 만들 수 있습니다.

WCF Data Services에는 일반.NET Framework 클라이언트 응용 프로그램용와 Silverlight 기반 응용 프로그램용 라이브러리 등 클라이언트 라이브러리 집합이 포함 됩니다. 이러한 클라이언트 라이브러리는.NET Framework 및 Silverlight와 같은 환경에서 OData 피드에 액세스할 때 개체 기반 프로그래밍 모델을 제공 합니다.

## <a name="where-should-i-start"></a>시작 지점

관리자의 관심에 따라 다음 항목 중 하나에서 WCF Data Services를 사용 하 여 시작 하는 것이 좋습니다.

바로 시작...

- [빠른 시작](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)

- [시작](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)

- [Silverlight 빠른 시작](https://go.microsoft.com/fwlink/?LinkID=192782)

- [Windows Phone 개발을 위한 Silverlight 빠른 시작](https://go.microsoft.com/fwlink/?LinkID=214535)

방금 코드가 표시 하는 중...

- [빠른 시작](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)

- [방법: 데이터 서비스 쿼리 실행](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)

- [방법: Windows Presentation Foundation 요소에 데이터 바인딩](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)

OData에 대 한 자세한 하려고 하는 중...

- [백서: OData 소개](https://go.microsoft.com/fwlink/?LinkId=220867)

- [Open Data Protocol 웹 사이트](https://go.microsoft.com/fwlink/?LinkID=184554)

- [OData: SDK](https://go.microsoft.com/fwlink/?LinkID=185248)

- [OData: 질문과 대답](https://go.microsoft.com/fwlink/?LinkId=185867)

비디오 시청 하고자 하는 중...

- [WCF Data Services 초보자 가이드](https://go.microsoft.com/fwlink/?LinkId=220864)

- [WCF Data Services 개발자 비디오](https://go.microsoft.com/fwlink/?LinkId=220861)

- [OData: 개발자가 웹 사이트](https://go.microsoft.com/fwlink/?LinkId=185866)

종단 간 예제를 참조 하려고 하는 중...

- [MSDN 샘플 갤러리의 WCF Data Services 설명서 샘플](https://go.microsoft.com/fwlink/?LinkID=220865)

- [MSDN 샘플 갤러리의 기타 WCF Data Services 샘플](https://go.microsoft.com/fwlink/?LinkId=220866)

- [OData: SDK](https://go.microsoft.com/fwlink/?LinkID=185248)

Visual Studio와의 통합 방식

- [데이터 서비스 클라이언트 라이브러리 생성](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)

- [데이터 서비스 만들기](../../../../docs/framework/data/wcf/creating-the-data-service.md)

- [Entity Framework 공급자](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)

수행 가능 작업

- [개요](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)

- [백서: OData 소개](https://go.microsoft.com/fwlink/?LinkId=220867)

- [애플리케이션 시나리오](../../../../docs/framework/data/wcf/application-scenarios-wcf-data-services.md)

Silverlight를 사용 하려고 하는 중...

- [Silverlight 빠른 시작](https://go.microsoft.com/fwlink/?LinkID=192782)

- [WCF Data Services(Silverlight)](https://go.microsoft.com/fwlink/?LinkID=143149)

- [Silverlight 시작](https://go.microsoft.com/fwlink/?LinkId=148366)

LINQ를 사용 하려고 하는 중...

- [데이터 서비스 쿼리](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)

- [LINQ 고려 사항](../../../../docs/framework/data/wcf/linq-considerations-wcf-data-services.md)

- [방법: 데이터 서비스 쿼리 실행](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)

여전히 몇 가지 자세한 정보가 필요 하는 중...

- [WCF Data Services 팀 블로그](https://go.microsoft.com/fwlink/?LinkID=150511)

- [리소스](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)

- [WCF Data Services 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=220868)

- [Open Data Protocol 웹 사이트](https://go.microsoft.com/fwlink/?LinkID=184554)

## <a name="in-this-section"></a>섹션 내용

[개요](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)

WCF Data Services에서 사용할 수 있는 기능에 대 한 개요를 제공합니다.

[WCF Data Services 5.0의에서 새로운 기능](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))

새 OData 기능에 대 한 지원과 WCF Data Services의 새로운 기능을 설명합니다.

[시작](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)

노출 하 고 WCF Data Services를 사용 하 여 OData 피드를 사용 하는 방법을 설명 합니다.

[WCF Data Services 정의](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)

만들기 및 OData 피드를 노출 하는 데이터 서비스를 구성 하는 방법을 설명 합니다.

[WCF Data Services 클라이언트 라이브러리](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)

클라이언트 라이브러리를 사용 하 여.NET Framework 클라이언트 응용 프로그램에서 OData 피드를 사용 하는 방법에 설명 합니다.

## <a name="see-also"></a>참고자료

- [REST(Representational State Transfer)](https://go.microsoft.com/fwlink/?LinkId=113919)
