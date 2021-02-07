---
description: '자세한 정보: 방법: 일괄 처리로 쿼리 실행 (WCF Data Services)'
title: '방법: 일괄 처리로 쿼리 실행 (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, batch requests
ms.assetid: 3b4db7df-bd33-43a1-8ea4-63a18e131f97
ms.openlocfilehash: bcd95be57d2f3f2cea075a4b87fb6858c59ea41e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765297"
---
# <a name="how-to-execute-queries-in-a-batch-wcf-data-services"></a>방법: 일괄 처리로 쿼리 실행 (WCF Data Services)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

WCF Data Services 클라이언트 라이브러리를 사용 하 여 단일 일괄 처리에서 데이터 서비스에 대해 둘 이상의 쿼리를 실행할 수 있습니다. 자세한 내용은 [일괄 처리 작업](batching-operations-wcf-data-services.md)을 참조 하세요.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터 서비스 및 자동 생성된 클라이언트 데이터 서비스 클래스를 사용합니다. 이 서비스 및 클라이언트 데이터 클래스는 [WCF Data Services 빠른](quickstart-wcf-data-services.md)시작을 완료 하면 생성 됩니다.  
  
## <a name="example"></a>예제  

 다음 예제에서는 메서드를 호출 하 여 <xref:System.Data.Services.Client.DataServiceContext.ExecuteBatch%2A> <xref:System.Data.Services.Client.DataServiceRequest%601> `Customers` `Products` Northwind 데이터 서비스에서 및 개체를 모두 반환 하는 쿼리를 포함 하는 개체의 배열을 실행 하는 방법을 보여 줍니다. 반환된 <xref:System.Data.Services.Client.QueryOperationResponse%601>의 <xref:System.Data.Services.Client.DataServiceResponse> 개체 컬렉션이 열거되고 각 <xref:System.Data.Services.Client.QueryOperationResponse%601>에 포함되어 있는 개체 컬렉션도 열거됩니다.  
  
 [!code-csharp[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#batchquery)]
 [!code-vb[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#batchquery)]  
  
## <a name="see-also"></a>참고 항목

- [WCF Data Services 클라이언트 라이브러리](wcf-data-services-client-library.md)
