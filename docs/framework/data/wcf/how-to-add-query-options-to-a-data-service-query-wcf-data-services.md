---
title: '방법: 데이터 서비스 쿼리 (WCF Data Services) 쿼리 옵션 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- querying the data service [WCF Data Services]
- WCF Data Services, querying
- WCF Data Services, accessing data
ms.assetid: e4258526-557e-4e96-91e1-2175400c7c8f
ms.openlocfilehash: 2056b803b34faafdaebb85883de8b76ea2f9dcd8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765546"
---
# <a name="how-to-add-query-options-to-a-data-service-query-wcf-data-services"></a>방법: 데이터 서비스 쿼리 (WCF Data Services) 쿼리 옵션 추가
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]를 사용하면 생성된 클라이언트 데이터 서비스 클래스를 통해 .NET Framework 기반 클라이언트 응용 프로그램에서 데이터 서비스를 쿼리할 수 있습니다. 이렇게 하는 가장 쉬운 방법은 원하는 쿼리 옵션을 포함하는 LINQ(Language-Integrated Query) 쿼리 식을 작성하는 것입니다. 일련의 LINQ 쿼리 메서드를 호출하여 동등한 쿼리를 작성할 수도 있습니다. 마지막으로 <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> 메서드를 사용하여 쿼리에 쿼리 옵션을 추가할 수 있습니다. 이러한 각 경우에 클라이언트에서 생성된 URI에는 선택한 쿼리 옵션이 적용된 요청한 엔터티 집합이 포함됩니다. 자세한 내용은 [데이터 서비스 쿼리](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)합니다.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터 서비스 및 자동 생성된 클라이언트 데이터 서비스 클래스를 사용합니다. 이 서비스 및 클라이언트 데이터 클래스를 수행할 때 생성 됩니다는 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 운송료가 $30를 초과하는 주문만 반환하고 운송 날짜의 내림차순으로 결과를 정렬하는 LINQ 쿼리 식을 작성하는 방법을 보여 줍니다.  
  
 [!code-csharp[Astoria Northwind Client#AddQueryOptionsLinq](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addqueryoptionslinq)]
 [!code-vb[Astoria Northwind Client#AddQueryOptionsLinq](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addqueryoptionslinq)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 LINQ 쿼리 메서드를 사용하여 앞의 쿼리와 동등한 LINQ 쿼리를 작성하는 방법을 보여 줍니다.  
  
 [!code-csharp[Astoria Northwind Client#AddQueryOptionsLinqExpression](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addqueryoptionslinqexpression)]
 [!code-vb[Astoria Northwind Client#AddQueryOptionsLinqExpression](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addqueryoptionslinqexpression)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> 메서드를 사용하여 앞의 예제와 동등한 <xref:System.Data.Services.Client.DataServiceQuery%601>를 만드는 방법을 보여 줍니다.  
  
 [!code-csharp[Astoria Northwind Client#AddQueryOptions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addqueryoptions)]
 [!code-vb[Astoria Northwind Client#AddQueryOptions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addqueryoptions)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 `$orderby` 쿼리 옵션을 사용하여 Freight 속성을 기준으로 반환된 Orders 개체를 필터링 및 정렬하는 방법을 보여 줍니다.  
  
 [!code-csharp[Astoria Northwind Client#OrderWithFilter](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#orderwithfilter)]
 [!code-vb[Astoria Northwind Client#OrderWithFilter](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#orderwithfilter)]  
  
## <a name="see-also"></a>참고자료

- [데이터 서비스 쿼리](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)
- [방법: 쿼리 결과 프로젝션](../../../../docs/framework/data/wcf/how-to-project-query-results-wcf-data-services.md)
