---
description: '자세한 정보: 방법: 데이터 서비스에 대 한 액세스 사용 (WCF Data Services)'
title: '방법: 데이터 서비스에 액세스할 수 있도록 설정(WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 3d830bcd-32b4-4f26-9287-d58a071452c6
ms.openlocfilehash: 42be9c4c31da7bbbfef07958deef685d52df597b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765427"
---
# <a name="how-to-enable-access-to-the-data-service-wcf-data-services"></a>방법: 데이터 서비스에 액세스할 수 있도록 설정(WCF Data Services)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

WCF Data Services에서 데이터 서비스에 의해 노출 되는 리소스에 대 한 액세스 권한을 명시적으로 부여 해야 합니다. 즉, 새 데이터 서비스를 만든 후 엔터티 집합으로 개별 리소스에 대한 액세스 권한을 명시적으로 제공해야 합니다. 이 항목에서는 [빠른](quickstart-wcf-data-services.md)시작을 완료할 때 만들어지는 Northwind 데이터 서비스에서 5 개의 엔터티 집합에 대 한 읽기 및 쓰기 액세스를 설정 하는 방법을 보여 줍니다. <xref:System.Data.Services.EntitySetRights> 열거형이 <xref:System.FlagsAttribute>를 사용하여 정의되기 때문에 논리 OR 연산자를 사용하여 단일 엔터티 집합에 여러 사용 권한을 지정할 수 있습니다.  
  
> [!NOTE]
> ASP.NET 애플리케이션에 액세스할 수 있는 클라이언트는 데이터 서비스에 의해 노출되는 리소스에도 액세스할 수 있습니다. 리소스에 무단으로 액세스할 수 없도록 하려면 프로덕션 데이터 서비스에서 애플리케이션 자체에도 보안을 설정해야 합니다. 자세한 내용은 [ASP.NET 웹 사이트 보안](/previous-versions/aspnet/91f66yxt(v=vs.100))을 참조 하세요.  
  
### <a name="to-enable-access-to-the-data-service"></a>데이터 서비스에 액세스할 수 있도록 설정하려면  
  
- 데이터 서비스 코드에서 `InitializeService` 함수의 자리 표시자 코드를 다음 코드로 바꿉니다.  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#allreadconfig)]  
  
     이렇게 하면 클라이언트가 `Orders` 및 `Order_Details` 엔터티 집합에 대한 읽기 및 쓰기 액세스 권한과 `Customers` 엔터티 집합에 대한 읽기 전용 액세스 권한을 가질 수 있습니다.  
  
## <a name="see-also"></a>참고 항목

- [방법: IIS에서 실행되는 WCF Data Service 개발](how-to-develop-a-wcf-data-service-running-on-iis.md)
- [데이터 서비스 구성](configuring-the-data-service-wcf-data-services.md)
