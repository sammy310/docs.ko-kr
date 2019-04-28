---
title: Entity Framework 공급자(WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: 650b5eb6-c71d-4dc1-8b64-b6beaf752114
ms.openlocfilehash: a09c81b2d0f052884e8e54c899653a6f0e038aff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765624"
---
# <a name="entity-framework-provider-wcf-data-services"></a>Entity Framework 공급자(WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]와 마찬가지로 ADO.NET Entity Framework는 엔터티-관계 모델의 한 형식인 엔터티 데이터 모델을 기반으로 합니다. Entity Framework 변환 이라고 하는 엔터티 데이터 모델의 구현에 대 한 작업을 *개념적 모델*, 데이터 원본에 대 한 동등한 작업으로 합니다. 따라서 Entity Framework는 관계형 데이터를 기반으로 하는 데이터 서비스에 적합한 공급자이며, Entity Framework를 지원하는 데이터 공급자가 있는 모든 데이터베이스를 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]와 함께 사용할 수 있습니다. 현재 Entity Framework를 지 원하는 데이터 원본의 목록을 보려면 참조 [Entity Framework 용 타사 공급자](https://go.microsoft.com/fwlink/?LinkId=143699)합니다.  
  
 개념적 모델에서 엔터티 컨테이너는 서비스 루트입니다. 먼저 Entity Framework에서 개념적 모델을 정의해야 데이터 서비스가 데이터를 노출할 수 있습니다. 자세한 내용은 [방법: ADO.NET Entity Framework 데이터 원본을 사용 하 여 데이터 서비스를 만드는](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)합니다.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 엔터티의 동시성 토큰을 정의할 수 있도록 하 여 낙관적 동시성 모델을 지원 합니다. 엔터티의 속성을 하나 이상 포함하는 이 동시성 토큰은 요청되거나 업데이트 또는 삭제되고 있는 데이터가 변경되었는지 여부를 데이터 서비스에서 확인하는 데 사용됩니다. 요청의 eTag에서 가져온 토큰 값이 엔터티의 현재 값과 다르면 데이터 서비스에서 예외가 발생합니다. 속성이 동시성 토큰의 일부임을 나타내려면 `ConcurrencyMode="Fixed"` 공급자가 정의하는 데이터 모델에서 [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] 특성을 적용해야 합니다. 동시성 토큰에는 키 속성이나 탐색 속성이 포함될 수 없습니다. 자세한 내용은 [데이터 서비스 업데이트](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md)합니다.  
  
 Entity Framework에 대 한 자세한 내용은 참조 하세요 [Entity Framework 개요](../../../../docs/framework/data/adonet/ef/overview.md)합니다.  
  
## <a name="see-also"></a>참고자료

- [Data Services 공급자](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)
- [리플렉션 공급자](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)
- [엔터티 데이터 모델](../../../../docs/framework/data/adonet/entity-data-model.md)
