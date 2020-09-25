---
title: '방법: 쿼리가 반환하는 엔터티의 수 확인(WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, row count
ms.assetid: 03d41a82-df95-40ac-8439-a6c327d37ba8
ms.openlocfilehash: 0513d7cdb3ab8de8cd8a73528f7e6038a0e4faed
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194286"
---
# <a name="how-to-determine-the-number-of-entities-returned-by-a-query-wcf-data-services"></a>방법: 쿼리가 반환하는 엔터티의 수 확인(WCF Data Services)

WCF Data Services를 사용 하 여 쿼리 URI로 지정 된 엔터티 집합에 있는 엔터티 수를 확인할 수 있습니다. 이 수는 쿼리 결과와 함께 포함되거나 정수 값으로 포함될 수 있습니다. 자세한 내용은 [데이터 서비스 쿼리](querying-the-data-service-wcf-data-services.md)를 참조 하세요.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터 서비스 및 자동 생성된 클라이언트 데이터 서비스 클래스를 사용합니다. 이 서비스 및 클라이언트 데이터 클래스는 [WCF Data Services 빠른](quickstart-wcf-data-services.md)시작을 완료 하면 생성 됩니다.  
  
## <a name="example"></a>예제  

 이 예제에서는 <xref:System.Data.Services.Client.DataServiceQuery%601.IncludeTotalCount%2A> 메서드를 호출한 후 쿼리를 실행합니다. <xref:System.Data.Services.Client.QueryOperationResponse%601.TotalCount%2A> 속성은 `Customers` 엔터티 집합에 있는 엔터티 수를 반환합니다.  
  
 [!code-csharp[Astoria Northwind Client#CountAllCustomers](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#countallcustomers)]
 [!code-vb[Astoria Northwind Client#CountAllCustomers](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#countallcustomers)]  
  
## <a name="example"></a>예제  

 이 예제에서는 <xref:System.Linq.Enumerable.Count%2A> 메서드를 호출하여 `Customers` 엔터티 집합에 있는 엔터티 수인 정수 값만 반환합니다.  
  
 [!code-csharp[Astoria Northwind Client#CountAllCustomersValueOnly](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#countallcustomersvalueonly)]
 [!code-vb[Astoria Northwind Client#CountAllCustomersValueOnly](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#countallcustomersvalueonly)]  
  
## <a name="see-also"></a>참고 항목

- [데이터 서비스 쿼리](querying-the-data-service-wcf-data-services.md)
