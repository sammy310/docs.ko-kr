---
title: '방법: 데이터 서비스에 액세스할 수 있도록 설정(WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 3d830bcd-32b4-4f26-9287-d58a071452c6
ms.openlocfilehash: 377b031c48ed831cfa5e270426283ed03a55f886
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90542309"
---
# <a name="how-to-enable-access-to-the-data-service-wcf-data-services"></a><span data-ttu-id="6a303-102">방법: 데이터 서비스에 액세스할 수 있도록 설정(WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="6a303-102">How to: Enable Access to the Data Service (WCF Data Services)</span></span>
<span data-ttu-id="6a303-103">WCF Data Services에서 데이터 서비스에 의해 노출 되는 리소스에 대 한 액세스 권한을 명시적으로 부여 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a303-103">In WCF Data Services, you must explicitly grant access to the resources that are exposed by a data service.</span></span> <span data-ttu-id="6a303-104">즉, 새 데이터 서비스를 만든 후 엔터티 집합으로 개별 리소스에 대한 액세스 권한을 명시적으로 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a303-104">This means that after you create a new data service, you must still explicitly provide access to individual resources as entity sets.</span></span> <span data-ttu-id="6a303-105">이 항목에서는 [빠른](quickstart-wcf-data-services.md)시작을 완료할 때 만들어지는 Northwind 데이터 서비스에서 5 개의 엔터티 집합에 대 한 읽기 및 쓰기 액세스를 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6a303-105">This topic shows how to enable read and write access to five of the entity sets in the Northwind data service that is created when you complete the [quickstart](quickstart-wcf-data-services.md).</span></span> <span data-ttu-id="6a303-106"><xref:System.Data.Services.EntitySetRights> 열거형이 <xref:System.FlagsAttribute>를 사용하여 정의되기 때문에 논리 OR 연산자를 사용하여 단일 엔터티 집합에 여러 사용 권한을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a303-106">Because the <xref:System.Data.Services.EntitySetRights> enumeration is defined by using the <xref:System.FlagsAttribute>, you can use a logical OR operator to specify multiple permissions for a single entity set.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6a303-107">ASP.NET 애플리케이션에 액세스할 수 있는 클라이언트는 데이터 서비스에 의해 노출되는 리소스에도 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a303-107">Any client that can access the ASP.NET application can also access the resources exposed by the data service.</span></span> <span data-ttu-id="6a303-108">리소스에 무단으로 액세스할 수 없도록 하려면 프로덕션 데이터 서비스에서 애플리케이션 자체에도 보안을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a303-108">In a production data service, to prevent unauthorized access to resources, you should also secure the application itself.</span></span> <span data-ttu-id="6a303-109">자세한 내용은 [ASP.NET 웹 사이트 보안](/previous-versions/aspnet/91f66yxt(v=vs.100))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6a303-109">For more information, see [Securing ASP.NET Web Sites](/previous-versions/aspnet/91f66yxt(v=vs.100)).</span></span>  
  
### <a name="to-enable-access-to-the-data-service"></a><span data-ttu-id="6a303-110">데이터 서비스에 액세스할 수 있도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="6a303-110">To enable access to the data service</span></span>  
  
- <span data-ttu-id="6a303-111">데이터 서비스 코드에서 `InitializeService` 함수의 자리 표시자 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6a303-111">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#allreadconfig)]  
  
     <span data-ttu-id="6a303-112">이렇게 하면 클라이언트가 `Orders` 및 `Order_Details` 엔터티 집합에 대한 읽기 및 쓰기 액세스 권한과 `Customers` 엔터티 집합에 대한 읽기 전용 액세스 권한을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a303-112">This enables clients to have read and write access to the `Orders` and `Order_Details` entity sets and read-only access to the `Customers` entity sets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a303-113">참조</span><span class="sxs-lookup"><span data-stu-id="6a303-113">See also</span></span>

- [<span data-ttu-id="6a303-114">방법: IIS에서 실행되는 WCF Data Service 개발</span><span class="sxs-lookup"><span data-stu-id="6a303-114">How to: Develop a WCF Data Service Running on IIS</span></span>](how-to-develop-a-wcf-data-service-running-on-iis.md)
- [<span data-ttu-id="6a303-115">데이터 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="6a303-115">Configuring the Data Service</span></span>](configuring-the-data-service-wcf-data-services.md)
