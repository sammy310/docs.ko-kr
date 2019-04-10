---
title: '방법: 데이터 서비스 (WCF Data Services)에 대 한 액세스를 사용 하도록 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 3d830bcd-32b4-4f26-9287-d58a071452c6
ms.openlocfilehash: 44f3709cf0a1485c772940e7460d3436a52aa3eb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163659"
---
# <a name="how-to-enable-access-to-the-data-service-wcf-data-services"></a>방법: 데이터 서비스 (WCF Data Services)에 대 한 액세스를 사용 하도록 설정
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에서는 데이터 서비스에서 노출하는 리소스에 대한 액세스 권한을 명시적으로 부여해야 합니다. 즉, 새 데이터 서비스를 만든 후 엔터티 집합으로 개별 리소스에 대한 액세스 권한을 명시적으로 제공해야 합니다. 이 항목에서는 읽기를 사용 하는 방법 및 쓰기 액세스의 다섯 엔터티를 완료 하면 만들어지는 Northwind 데이터 서비스에서 설정 된 [퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)합니다. <xref:System.Data.Services.EntitySetRights> 열거형이 <xref:System.FlagsAttribute>를 사용하여 정의되기 때문에 논리 OR 연산자를 사용하여 단일 엔터티 집합에 여러 사용 권한을 지정할 수 있습니다.  
  
> [!NOTE]
>  ASP.NET 응용 프로그램에 액세스할 수 있는 클라이언트는 데이터 서비스에 의해 노출되는 리소스에도 액세스할 수 있습니다. 리소스에 무단으로 액세스할 수 없도록 하려면 프로덕션 데이터 서비스에서 응용 프로그램 자체에도 보안을 설정해야 합니다. 자세한 내용은 [ASP.NET 웹 사이트 보안](https://docs.microsoft.com/previous-versions/aspnet/91f66yxt(v=vs.100))합니다.  
  
### <a name="to-enable-access-to-the-data-service"></a>데이터 서비스에 액세스할 수 있도록 설정하려면  
  
-   데이터 서비스 코드에서 `InitializeService` 함수의 자리 표시자 코드를 다음 코드로 바꿉니다.  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]  
  
     이렇게 하면 클라이언트가 `Orders` 및 `Order_Details` 엔터티 집합에 대한 읽기 및 쓰기 액세스 권한과 `Customers` 엔터티 집합에 대한 읽기 전용 액세스 권한을 가질 수 있습니다.  
  
## <a name="see-also"></a>참고자료

- [방법: IIS에서 실행되는 WCF Data Service 개발](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md)
- [데이터 서비스 구성](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)
