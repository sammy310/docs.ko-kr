---
title: 서비스로 데이터 노출(WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- getting started, WCF Data Services
- WCF Data Services, getting started
ms.assetid: df0bbcee-f66f-4a88-abb4-4e73c8b9c908
ms.openlocfilehash: 3c0763f21940831f401194356dc25b0d99c8d6f2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765637"
---
# <a name="expose-your-data-as-a-service-wcf-data-services"></a>As a Service (WCF Data Services) 데이터를 노출 합니다.

WCF Data Services로 데이터를 노출 하는 서비스를 더 쉽게 정의할 수 있도록 Visual Studio와 통합 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] 피드 합니다. OData 피드를 노출 하는 데이터 서비스를 만드는 기본 단계를 다음과 같습니다.

1. **데이터 모델을 정의 합니다.** WCF Data Services 기반으로 하는 데이터 모델을 고유 하 게 지원 합니다 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md)합니다. 자세한 내용은 [방법: ADO.NET Entity Framework 데이터 원본을 사용 하 여 데이터 서비스를 만드는](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)합니다.

     WCF Data Services에서는 인스턴스를 반환 하는 공용 언어 런타임 (CLR) 개체를 기반으로 하는 데이터 모델을 <xref:System.Linq.IQueryable%601> 인터페이스입니다. 따라서 .NET Framework의 목록, 배열 및 컬렉션을 기반으로 하는 데이터 서비스를 배포할 수 있습니다. 이러한 데이터 구조에 대해 만들기, 업데이트 및 삭제 작업을 수행하려면 <xref:System.Data.Services.IUpdatable> 인터페이스도 구현해야 합니다. 자세한 내용은 [방법: 리플렉션 공급자를 사용 하 여 데이터 서비스를 만드는](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)합니다.

     고급 시나리오에 대 한 WCF Data Services는 런타임에 바인딩된 데이터 형식을 기반으로 데이터 모델을 정의할 수 있도록 공급자 집합을 포함 합니다. 자세한 내용은 [사용자 지정 데이터 서비스 공급자](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md)합니다.

2. **데이터 서비스를 만듭니다.** 가장 기본적인 데이터 서비스는 <xref:System.Data.Services.DataService%601> 클래스에서 상속하는 클래스를 엔터티 컨테이너의 네임스페이스로 정규화된 이름인 `T` 형식으로 노출합니다. 자세한 내용은 [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)의 개발 및 배포에 대한 정보를 제공합니다.

3. **데이터 서비스를 구성 합니다.** 기본적으로 WCF Data Services는 엔터티 컨테이너에 의해 노출 되는 리소스에 대 한 액세스를 비활성화 합니다. <xref:System.Data.Services.DataServiceConfiguration> 인터페이스를 사용 하면 리소스에 대 한 액세스를 구성 및 서비스 작업, odata, 지원 되는 버전을 지정 하 고 일괄 처리 동작 또는 반환할 수 있는 엔터티의 최대 수와 같은 서비스 전반적인 기타 동작을 정의 하려면 단일 응답 합니다. 자세한 내용은 [데이터 서비스 구성](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)합니다.

Northwind 샘플 데이터베이스를 기반으로 하는 간단한 데이터 서비스를 만드는 방법의 예제를 참조 하세요 [퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)합니다.

## <a name="see-also"></a>참고자료

- [시작](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)
- [개요](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)