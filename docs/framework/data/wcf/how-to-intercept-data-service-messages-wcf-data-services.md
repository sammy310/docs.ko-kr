---
description: '자세한 정보: 방법: 데이터 서비스 메시지 가로채기 (WCF Data Services)'
title: '방법: 데이터 서비스 메시지 가로채기(WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: 24b9df1b-b54b-4795-a033-edf333675de6
ms.openlocfilehash: 6768fa9f0c7ca9a5a6ed6faa318675f2c2c51543
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765284"
---
# <a name="how-to-intercept-data-service-messages-wcf-data-services"></a><span data-ttu-id="eac5f-103">방법: 데이터 서비스 메시지 가로채기(WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="eac5f-103">How to: Intercept Data Service Messages (WCF Data Services)</span></span>

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

<span data-ttu-id="eac5f-104">WCF Data Services를 사용 하면 사용자 지정 논리를 작업에 추가할 수 있도록 요청 메시지를 가로챌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eac5f-104">With WCF Data Services, you can intercept request messages so that you can add custom logic to an operation.</span></span> <span data-ttu-id="eac5f-105">메시지를 가로채려면 데이터 서비스에서 특별한 특성이 있는 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="eac5f-105">To intercept a message, you use specially attributed methods in the data service.</span></span> <span data-ttu-id="eac5f-106">자세한 내용은 [인터셉터](interceptors-wcf-data-services.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eac5f-106">For more information, see [Interceptors](interceptors-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="eac5f-107">이 항목의 예제에서는 Northwind 샘플 데이터 서비스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="eac5f-107">The example in this topic uses the Northwind sample data service.</span></span> <span data-ttu-id="eac5f-108">이 서비스는 [WCF Data Services 빠른](quickstart-wcf-data-services.md)시작을 완료 하면 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eac5f-108">This service is created when you complete the [WCF Data Services quickstart](quickstart-wcf-data-services.md).</span></span>  
  
### <a name="to-define-a-query-interceptor-for-the-orders-entity-set"></a><span data-ttu-id="eac5f-109">Orders 엔터티 집합에 대해 쿼리 인터셉터를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="eac5f-109">To define a query interceptor for the Orders entity set</span></span>  
  
1. <span data-ttu-id="eac5f-110">Northwind 데이터 서비스 프로젝트에서 Northwind.svc 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="eac5f-110">In the Northwind data service project, open the Northwind.svc file.</span></span>  
  
2. <span data-ttu-id="eac5f-111">`Northwind` 클래스의 코드 페이지에서 다음 `using` 문(Visual Basic에서는 `Imports`)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="eac5f-111">In the code page for the `Northwind` class, add the following `using` statement (`Imports` in Visual Basic).</span></span>  
  
     [!code-csharp[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#usinglinqexpressions)]
     [!code-vb[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#usinglinqexpressions)]  
  
3. <span data-ttu-id="eac5f-112">`Northwind` 클래스에서 `OnQueryOrders`라는 서비스 작업 메서드를 다음과 같이 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="eac5f-112">In the `Northwind` class, define a service operation method named `OnQueryOrders` as follows:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptordef)]
     [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
### <a name="to-define-a-change-interceptor-for-the-products-entity-set"></a><span data-ttu-id="eac5f-113">Products 엔터티 집합에 대해 변경 인터셉터를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="eac5f-113">To define a change interceptor for the Products entity set</span></span>  
  
1. <span data-ttu-id="eac5f-114">Northwind 데이터 서비스 프로젝트에서 Northwind.svc 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="eac5f-114">In the Northwind data service project, open the Northwind.svc file.</span></span>  
  
2. <span data-ttu-id="eac5f-115">`Northwind` 클래스에서 `OnChangeProducts`라는 서비스 작업 메서드를 다음과 같이 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="eac5f-115">In the `Northwind` class, define a service operation method named `OnChangeProducts` as follows:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptordef)]
     [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
## <a name="example"></a><span data-ttu-id="eac5f-116">예제</span><span class="sxs-lookup"><span data-stu-id="eac5f-116">Example</span></span>  

 <span data-ttu-id="eac5f-117">다음 예제에서는 `Orders` 엔터티 집합에 대해 람다 식을 반환하는 쿼리 인터셉터 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="eac5f-117">This example defines a query interceptor method for the `Orders` entity set that returns a lambda expression.</span></span> <span data-ttu-id="eac5f-118">이 식에는 특정 연락처 이름이 있는 관련 `Orders`를 기반으로 요청된 `Customers`를 필터링하는 대리자가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eac5f-118">This expression contains a delegate that filters the requested `Orders` based on related `Customers` that have a specific contact name.</span></span> <span data-ttu-id="eac5f-119">이름은 요청하는 사용자를 기반으로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="eac5f-119">The name is in turn determined based on the requesting user.</span></span> <span data-ttu-id="eac5f-120">이 예제에서는 WCF를 사용하고 인증이 사용하도록 설정된 ASP.NET 웹 애플리케이션 내에 데이터 서비스가 호스트된다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="eac5f-120">This example assumes that the data service is hosted within an ASP.NET Web application that uses WCF, and that authentication is enabled.</span></span> <span data-ttu-id="eac5f-121"><xref:System.Web.HttpContext> 클래스는 현재 요청의 사용자를 검색하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eac5f-121">The <xref:System.Web.HttpContext> class is used to retrieve the principle of the current request.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptor)]
 [!code-vb[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptor)]  
  
## <a name="example"></a><span data-ttu-id="eac5f-122">예제</span><span class="sxs-lookup"><span data-stu-id="eac5f-122">Example</span></span>  

 <span data-ttu-id="eac5f-123">다음 예제에서는 `Products` 엔터티 집합에 대해 변경 인터셉터 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="eac5f-123">This example defines a change interceptor method for the `Products` entity set.</span></span> <span data-ttu-id="eac5f-124">이 메서드는 <xref:System.Data.Services.UpdateOperations.Add> 또는 <xref:System.Data.Services.UpdateOperations.Change> 작업에 대해 서비스 입력의 유효성을 검사하고 판매가 중단된 제품이 변경되는 경우 예외를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="eac5f-124">This method validates input to the service for an <xref:System.Data.Services.UpdateOperations.Add> or <xref:System.Data.Services.UpdateOperations.Change> operation and raises an exception if a change is being made to a discontinued product.</span></span> <span data-ttu-id="eac5f-125">또한 제품 삭제를 지원되지 않는 작업으로 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="eac5f-125">It also blocks the deletion of products as an unsupported operation.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptor)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptor)]  
  
## <a name="see-also"></a><span data-ttu-id="eac5f-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eac5f-126">See also</span></span>

- [<span data-ttu-id="eac5f-127">방법: 서비스 작업 정의</span><span class="sxs-lookup"><span data-stu-id="eac5f-127">How to: Define a Service Operation</span></span>](how-to-define-a-service-operation-wcf-data-services.md)
- [<span data-ttu-id="eac5f-128">WCF Data Services 정의</span><span class="sxs-lookup"><span data-stu-id="eac5f-128">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)
