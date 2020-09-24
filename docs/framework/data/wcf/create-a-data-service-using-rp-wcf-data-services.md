---
title: '방법: 리플렉션 공급자를 사용 하 여 데이터 서비스 만들기 (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: 7315c6d8-f452-4fb2-a0c1-76ab0593c146
ms.openlocfilehash: 6bab9d9be484cf90cb85df63a1b237b5cc39a5e0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91152769"
---
# <a name="how-to-create-a-data-service-using-the-reflection-provider-wcf-data-services"></a>방법: 리플렉션 공급자를 사용 하 여 데이터 서비스 만들기 (WCF Data Services)

WCF Data Services를 사용 하면 해당 클래스가 인터페이스를 구현 하는 개체로 노출 되는 한 임의의 클래스를 기반으로 하는 데이터 모델을 정의할 수 있습니다 <xref:System.Linq.IQueryable%601> . 자세한 내용은 [데이터 서비스 공급자](data-services-providers-wcf-data-services.md)합니다.  
  
## <a name="example"></a>예제  

 다음 예제에서는 `Orders` 및 `Items`가 포함된 데이터 모델을 정의합니다. 엔터티 컨테이너 클래스 `OrderItemData`에는 <xref:System.Linq.IQueryable%601> 인터페이스를 반환하는 두 개의 공용 메서드가 있습니다. 이러한 인터페이스는 `Orders` 및 `Items` 엔터티 형식의 엔터티 집합입니다. `Order`에는 여러 `Items`가 포함될 수 있으므로 `Orders` 엔터티 형식의 `Items` 탐색 속성은 `Items` 개체의 컬렉션을 반환합니다. `OrderItemData` 엔터티 컨테이너 클래스는 <xref:System.Data.Services.DataService%601> 데이터 서비스가 파생되는 `OrderItems` 클래스의 제네릭 형식입니다.  
  
> [!NOTE]
> 이 예제에서는 메모리 내 데이터 공급자를 보여 주며 변경 내용이 현재 개체 인스턴스 외부에서 유지되지 않으므로 <xref:System.Data.Services.IUpdatable> 인터페이스를 구현해도 파생되는 이점이 없습니다. 인터페이스를 구현 하는 예제는 <xref:System.Data.Services.IUpdatable> [방법: LINQ to SQL 데이터 소스를 사용 하 여 데이터 서비스 만들기](create-a-data-service-using-linq-to-sql-wcf.md)를 참조 하세요.  
  
 [!code-csharp[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_reflection_provider/cs/orderitems.svc.cs#customiqueryable)]
 [!code-vb[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_reflection_provider/vb/orderitems.svc.vb#customiqueryable)]  
  
## <a name="see-also"></a>참고 항목

- [방법: LINQ to SQL 데이터 원본을 사용하여 데이터 서비스 만들기](create-a-data-service-using-linq-to-sql-wcf.md)
- [Data Services 공급자](data-services-providers-wcf-data-services.md)
- [방법: ADO.NET Entity Framework 데이터 원본을 사용하여 데이터 서비스 만들기](create-a-data-service-using-an-adonet-ef-data-wcf.md)
