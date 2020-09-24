---
title: '방법: 기존 엔터티를 DataServiceContext에 연결(WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, changing data
ms.assetid: e3f2d71d-434c-4e98-91c3-95adae4702b6
ms.openlocfilehash: 69ca64f4ab3470c1a4f58c582b31c06aed9cadd5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166133"
---
# <a name="how-to-attach-an-existing-entity-to-the-dataservicecontext-wcf-data-services"></a>방법: 기존 엔터티를 DataServiceContext에 연결(WCF Data Services)

엔터티가 데이터 서비스에 이미 있는 경우에는 WCF Data Services 클라이언트 라이브러리를 사용 하 여 <xref:System.Data.Services.Client.DataServiceContext> 먼저 쿼리를 실행 하지 않고 엔터티를 나타내는 개체를에 직접 연결할 수 있습니다. 자세한 내용은 [데이터 서비스 업데이트](updating-the-data-service-wcf-data-services.md)를 참조 하세요.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터 서비스 및 자동 생성된 클라이언트 데이터 서비스 클래스를 사용합니다. 이 서비스 및 클라이언트 데이터 클래스는 [WCF Data Services 빠른](quickstart-wcf-data-services.md)시작을 완료 하면 생성 됩니다.  
  
## <a name="example"></a>예제  

 다음 예제에서는 데이터 서비스에 저장될 변경 내용이 포함되어 있는 기존 `Customer` 개체를 만드는 방법을 보여 줍니다. 개체가 컨텍스트에 연결되고 <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> 메서드가 호출되어 <xref:System.Data.Services.Client.EntityStates.Modified> 메서드를 호출하기 전에 연결된 개체를 <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>로 표시합니다.  
  
 [!code-csharp[Astoria Northwind Client#AttachObject](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#attachobject)]
 [!code-vb[Astoria Northwind Client#AttachObject](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#attachobject)]  
  
## <a name="see-also"></a>참고 항목

- [WCF Data Services 클라이언트 라이브러리](wcf-data-services-client-library.md)
