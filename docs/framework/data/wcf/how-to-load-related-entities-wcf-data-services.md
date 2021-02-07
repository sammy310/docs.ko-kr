---
description: '자세한 정보: 방법: 관련 엔터티 로드 (WCF Data Services)'
title: '방법: 관련 엔터티 로드(WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, deferred content
- WCF Data Services, loading data
ms.assetid: 6f143d30-d997-4e6b-bcf0-d5c394ecb108
ms.openlocfilehash: 004e52b17c399abe8564dd069dd251d7baf296cc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765258"
---
# <a name="how-to-load-related-entities-wcf-data-services"></a>방법: 관련 엔터티 로드(WCF Data Services)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

WCF Data Services에서 연결 된 엔터티를 로드 해야 하는 경우 클래스에서 메서드를 사용할 수 있습니다 <xref:System.Data.Services.Client.DataServiceContext.LoadProperty%2A> <xref:System.Data.Services.Client.DataServiceContext> . 또한에서 메서드를 사용 하 여 <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> <xref:System.Data.Services.Client.DataServiceQuery%601> 관련 엔터티를 동일한 쿼리 응답에서 적극적으로 로드할 수 있습니다.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터 서비스 및 자동 생성된 클라이언트 데이터 서비스 클래스를 사용합니다. 이 서비스 및 클라이언트 데이터 클래스는 [WCF Data Services 빠른](quickstart-wcf-data-services.md)시작을 완료 하면 생성 됩니다.  
  
## <a name="example"></a>예제  

 다음 예제에서는 반환되는 각 `Customer` 인스턴스와 관련된 `Orders`를 명시적으로 로드하는 방법을 보여 줍니다.  
  
 [!code-csharp[Astoria Northwind Client#LoadRelatedOrderCustomer](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#loadrelatedordercustomer)]
 [!code-vb[Astoria Northwind Client#LoadRelatedOrderCustomer](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#loadrelatedordercustomer)]  
  
## <a name="example"></a>예제  

 다음 예제에서는 <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> 메서드를 사용하여 쿼리에서 반환된 `Order Details`에 속하는 `Orders`를 반환하는 방법을 보여 줍니다.  
  
 [!code-csharp[Astoria Northwind Client#ExpandOrderDetails](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#expandorderdetails)]
 [!code-vb[Astoria Northwind Client#ExpandOrderDetails](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#expandorderdetails)]  
  
## <a name="see-also"></a>참고 항목

- [데이터 서비스 쿼리](querying-the-data-service-wcf-data-services.md)
