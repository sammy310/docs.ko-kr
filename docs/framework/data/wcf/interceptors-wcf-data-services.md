---
title: 인터셉터(WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: e33ae8dc-8069-41d0-99a0-75ff28db7050
ms.openlocfilehash: c9799037ae0ea8b29b5e989859aff29c310593d4
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568981"
---
# <a name="interceptors-wcf-data-services"></a><span data-ttu-id="a4abf-102">인터셉터(WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="a4abf-102">Interceptors (WCF Data Services)</span></span>
<span data-ttu-id="a4abf-103">WCF Data Services를 사용 하면 응용 프로그램에서 요청 메시지를 가로채서 작업에 사용자 지정 논리를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4abf-103">WCF Data Services enables an application to intercept request messages so that you can add custom logic to an operation.</span></span> <span data-ttu-id="a4abf-104">이 사용자 지정 논리를 사용 하 여 들어오는 메시지의 데이터 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4abf-104">You can use this custom logic to validate data in incoming messages.</span></span> <span data-ttu-id="a4abf-105">요청별로 사용자 지정 인증 정책을 삽입하는 등 쿼리 요청 범위를 추가로 제한하는 데에도 이 논리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4abf-105">You can also use it to further restrict the scope of a query request, such as to insert a custom authorization policy on a per request basis.</span></span>  
  
 <span data-ttu-id="a4abf-106">가로채기는 데이터 서비스에서 특별한 특성이 있는 메서드에 의해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4abf-106">Interception is performed by specially attributed methods in the data service.</span></span> <span data-ttu-id="a4abf-107">이러한 메서드는 메시지 처리 중 적절 한 시점에 WCF Data Services에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4abf-107">These methods are called by WCF Data Services at the appropriate point in message processing.</span></span> <span data-ttu-id="a4abf-108">인터셉터는 엔터티 집합 단위로 정의 되며 인터셉터 메서드는 서비스 작업과 같은 요청에서 매개 변수를 받아들일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4abf-108">Interceptors are defined on a per-entity set basis, and interceptor methods cannot accept parameters from the request like service operations can.</span></span> <span data-ttu-id="a4abf-109">HTTP GET 요청을 처리할 때 호출 되는 쿼리 인터셉터 메서드는 쿼리 결과에서 인터셉터 엔터티 집합의 인스턴스를 반환 해야 하는지 여부를 결정 하는 람다 식을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4abf-109">Query interceptor methods, which are called when processing an HTTP GET request, must return a lambda expression that determines whether an instance of the interceptor's entity set should be returned by the query results.</span></span> <span data-ttu-id="a4abf-110">데이터 서비스는 이 식을 사용하여 요청된 작업을 보다 구체화합니다.</span><span class="sxs-lookup"><span data-stu-id="a4abf-110">This expression is used by the data service to further refine the requested operation.</span></span> <span data-ttu-id="a4abf-111">다음은 쿼리 인터셉터의 정의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="a4abf-111">The following is an example definition of a query interceptor.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptordef)]
 [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
 <span data-ttu-id="a4abf-112">자세한 내용은 [방법: 데이터 서비스 메시지 가로채기](how-to-intercept-data-service-messages-wcf-data-services.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4abf-112">For more information, see [How to: Intercept Data Service Messages](how-to-intercept-data-service-messages-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="a4abf-113">쿼리가 아닌 작업을 처리할 때 호출되는 변경 인터셉터는 `void`(Visual Basic에서는 `Nothing`)를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4abf-113">Change interceptors, which are called when processing non-query operations, must return `void` (`Nothing` in Visual Basic).</span></span> <span data-ttu-id="a4abf-114">변경 인터셉터 메서드는 다음 두 매개 변수를 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4abf-114">Change interceptor methods must accept the following two parameters:</span></span>  
  
1. <span data-ttu-id="a4abf-115">엔터티 집합의 엔터티 형식과 호환되는 형식의 매개 변수.</span><span class="sxs-lookup"><span data-stu-id="a4abf-115">A parameter of a type that is compatible with the entity type of the entity set.</span></span> <span data-ttu-id="a4abf-116">데이터 서비스에서 변경 인터셉터를 호출하는 경우 이 매개 변수의 값은 요청에서 보낸 엔터티 정보를 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="a4abf-116">When the data service invokes the change interceptor, the value of this parameter will reflect the entity information that is sent by the request.</span></span>  
  
2. <span data-ttu-id="a4abf-117"><xref:System.Data.Services.UpdateOperations> 형식의 매개 변수.</span><span class="sxs-lookup"><span data-stu-id="a4abf-117">A parameter of type <xref:System.Data.Services.UpdateOperations>.</span></span> <span data-ttu-id="a4abf-118">데이터 서비스에서 변경 인터셉터를 호출하는 경우 이 매개 변수의 값은 요청에서 수행하려는 작업을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="a4abf-118">When the data service invokes the change interceptor, the value of this parameter will reflect the operation that the request is trying to perform.</span></span>  
  
 <span data-ttu-id="a4abf-119">다음은 변경 인터셉터의 정의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="a4abf-119">The following is an example definition of a change interceptor.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptordef)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
 <span data-ttu-id="a4abf-120">자세한 내용은 [방법: 데이터 서비스 메시지 가로채기](how-to-intercept-data-service-messages-wcf-data-services.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4abf-120">For more information, see [How to: Intercept Data Service Messages](how-to-intercept-data-service-messages-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="a4abf-121">다음 특성은 가로채기에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4abf-121">The following attributes are supported for interception.</span></span>  
  
 <span data-ttu-id="a4abf-122">**[Queryinterceptor (** *EntitySetName* **)]**</span><span class="sxs-lookup"><span data-stu-id="a4abf-122">**[QueryInterceptor(** *EntitySetName* **)]**</span></span>  
 <span data-ttu-id="a4abf-123"><xref:System.Data.Services.QueryInterceptorAttribute> 특성이 적용된 메서드는 대상 엔터티 집합 리소스에 대해 HTTP GET 요청을 받을 때 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4abf-123">Methods with the <xref:System.Data.Services.QueryInterceptorAttribute> attribute applied are called when an HTTP GET request is received for the targeted entity set resource.</span></span> <span data-ttu-id="a4abf-124">이 메서드는 항상 `Expression<Func<T,bool>>` 형식의 람다 식을 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4abf-124">These methods must always return a lambda expression in the form of `Expression<Func<T,bool>>`.</span></span>  
  
 <span data-ttu-id="a4abf-125">**[Changeinterceptor (** *EntitySetName* **)]**</span><span class="sxs-lookup"><span data-stu-id="a4abf-125">**[ChangeInterceptor(** *EntitySetName* **)]**</span></span>  
 <span data-ttu-id="a4abf-126"><xref:System.Data.Services.ChangeInterceptorAttribute> 특성이 적용된 메서드는 대상 엔터티 집합 리소스에 대해 HTTP GET 요청 이외의 HTTP 요청을 받을 때 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4abf-126">Methods with the <xref:System.Data.Services.ChangeInterceptorAttribute> attribute applied are called when an HTTP request other than HTTP GET request is received for the targeted entity set resource.</span></span> <span data-ttu-id="a4abf-127">이 메서드는 항상 `void`(Visual Basic에서는 `Nothing`)를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4abf-127">These methods must always return `void` (`Nothing` in Visual Basic).</span></span>  
  
 <span data-ttu-id="a4abf-128">자세한 내용은 [방법: 데이터 서비스 메시지 가로채기](how-to-intercept-data-service-messages-wcf-data-services.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4abf-128">For more information, see [How to: Intercept Data Service Messages](how-to-intercept-data-service-messages-wcf-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4abf-129">참조</span><span class="sxs-lookup"><span data-stu-id="a4abf-129">See also</span></span>

- [<span data-ttu-id="a4abf-130">서비스 작업</span><span class="sxs-lookup"><span data-stu-id="a4abf-130">Service Operations</span></span>](service-operations-wcf-data-services.md)
