---
title: 206 - ErrorHandlerInvoked
ms.date: 03/30/2017
ms.assetid: 97340f4d-4e09-4e42-a17a-982b3868dbcf
ms.openlocfilehash: 99415733624752217d32f6f026a419b2b32bfa7b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244615"
---
# <a name="206---errorhandlerinvoked"></a><span data-ttu-id="09e7e-102">206 - ErrorHandlerInvoked</span><span class="sxs-lookup"><span data-stu-id="09e7e-102">206 - ErrorHandlerInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="09e7e-103">속성</span><span class="sxs-lookup"><span data-stu-id="09e7e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="09e7e-104">ID</span><span class="sxs-lookup"><span data-stu-id="09e7e-104">ID</span></span>|<span data-ttu-id="09e7e-105">206</span><span class="sxs-lookup"><span data-stu-id="09e7e-105">206</span></span>|  
|<span data-ttu-id="09e7e-106">키워드</span><span class="sxs-lookup"><span data-stu-id="09e7e-106">Keywords</span></span>|<span data-ttu-id="09e7e-107">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="09e7e-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="09e7e-108">Level</span><span class="sxs-lookup"><span data-stu-id="09e7e-108">Level</span></span>|<span data-ttu-id="09e7e-109">정보</span><span class="sxs-lookup"><span data-stu-id="09e7e-109">Information</span></span>|  
|<span data-ttu-id="09e7e-110">채널</span><span class="sxs-lookup"><span data-stu-id="09e7e-110">Channel</span></span>|<span data-ttu-id="09e7e-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="09e7e-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="09e7e-112">Description</span><span class="sxs-lookup"><span data-stu-id="09e7e-112">Description</span></span>  

 <span data-ttu-id="09e7e-113">이 이벤트는 서비스 작업에서 발생한 예외를 처리할 수 있는 기회가 `ErrorHandler`에 제공된 후에 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="09e7e-113">This event is emitted after an `ErrorHandler` has had an opportunity to handle an exception that occurred in a service operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="09e7e-114">메시지</span><span class="sxs-lookup"><span data-stu-id="09e7e-114">Message</span></span>  

 <span data-ttu-id="09e7e-115">디스패처가 ' %3 ' 형식의 예외를 사용 하 여 ' %1 ' 형식의 ErrorHandler를 호출 했습니다.</span><span class="sxs-lookup"><span data-stu-id="09e7e-115">The Dispatcher invoked an ErrorHandler of type '%1' with an exception of type '%3'.</span></span> <span data-ttu-id="09e7e-116">ErrorHandled == '%2'.</span><span class="sxs-lookup"><span data-stu-id="09e7e-116">ErrorHandled == '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="09e7e-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="09e7e-117">Details</span></span>  
  
|<span data-ttu-id="09e7e-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="09e7e-118">Data Item Name</span></span>|<span data-ttu-id="09e7e-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="09e7e-119">Data Item Type</span></span>|<span data-ttu-id="09e7e-120">Description</span><span class="sxs-lookup"><span data-stu-id="09e7e-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="09e7e-121">TypeName</span><span class="sxs-lookup"><span data-stu-id="09e7e-121">TypeName</span></span>|`xs:string`|<span data-ttu-id="09e7e-122">호출된 `ErrorHandler` 형식의 CLR FullName입니다.</span><span class="sxs-lookup"><span data-stu-id="09e7e-122">The CLR FullName of the type of the invoked `ErrorHandler`.</span></span>|  
|<span data-ttu-id="09e7e-123">처리됨</span><span class="sxs-lookup"><span data-stu-id="09e7e-123">Handled</span></span>|`xs:unsignedByte`|<span data-ttu-id="09e7e-124">오류 처리기가 오류를 처리했으면 `true`이고, 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="09e7e-124">`true` if the error handler handled the error, otherwise `false`.</span></span>|  
|<span data-ttu-id="09e7e-125">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="09e7e-125">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="09e7e-126">처리된 예외의 CLR FullName입니다.</span><span class="sxs-lookup"><span data-stu-id="09e7e-126">The CLR FullName of the exception that was being handled.</span></span>|  
|<span data-ttu-id="09e7e-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="09e7e-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="09e7e-128">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="09e7e-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="09e7e-129">해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09e7e-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="09e7e-130">예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="09e7e-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="09e7e-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="09e7e-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="09e7e-132">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="09e7e-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
