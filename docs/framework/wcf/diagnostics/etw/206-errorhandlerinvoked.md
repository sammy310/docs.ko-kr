---
description: '자세한 정보: 206-ErrorHandlerInvoked'
title: 206 - ErrorHandlerInvoked
ms.date: 03/30/2017
ms.assetid: 97340f4d-4e09-4e42-a17a-982b3868dbcf
ms.openlocfilehash: addbcbdea25c7f8e7515b743e98e426476fa0b28
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783783"
---
# <a name="206---errorhandlerinvoked"></a><span data-ttu-id="527c8-103">206 - ErrorHandlerInvoked</span><span class="sxs-lookup"><span data-stu-id="527c8-103">206 - ErrorHandlerInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="527c8-104">속성</span><span class="sxs-lookup"><span data-stu-id="527c8-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="527c8-105">ID</span><span class="sxs-lookup"><span data-stu-id="527c8-105">ID</span></span>|<span data-ttu-id="527c8-106">206</span><span class="sxs-lookup"><span data-stu-id="527c8-106">206</span></span>|  
|<span data-ttu-id="527c8-107">키워드</span><span class="sxs-lookup"><span data-stu-id="527c8-107">Keywords</span></span>|<span data-ttu-id="527c8-108">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="527c8-108">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="527c8-109">Level</span><span class="sxs-lookup"><span data-stu-id="527c8-109">Level</span></span>|<span data-ttu-id="527c8-110">정보</span><span class="sxs-lookup"><span data-stu-id="527c8-110">Information</span></span>|  
|<span data-ttu-id="527c8-111">채널</span><span class="sxs-lookup"><span data-stu-id="527c8-111">Channel</span></span>|<span data-ttu-id="527c8-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="527c8-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="527c8-113">설명</span><span class="sxs-lookup"><span data-stu-id="527c8-113">Description</span></span>  

 <span data-ttu-id="527c8-114">이 이벤트는 서비스 작업에서 발생한 예외를 처리할 수 있는 기회가 `ErrorHandler`에 제공된 후에 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="527c8-114">This event is emitted after an `ErrorHandler` has had an opportunity to handle an exception that occurred in a service operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="527c8-115">메시지</span><span class="sxs-lookup"><span data-stu-id="527c8-115">Message</span></span>  

 <span data-ttu-id="527c8-116">디스패처가 ' %3 ' 형식의 예외를 사용 하 여 ' %1 ' 형식의 ErrorHandler를 호출 했습니다.</span><span class="sxs-lookup"><span data-stu-id="527c8-116">The Dispatcher invoked an ErrorHandler of type '%1' with an exception of type '%3'.</span></span> <span data-ttu-id="527c8-117">ErrorHandled == '%2'.</span><span class="sxs-lookup"><span data-stu-id="527c8-117">ErrorHandled == '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="527c8-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="527c8-118">Details</span></span>  
  
|<span data-ttu-id="527c8-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="527c8-119">Data Item Name</span></span>|<span data-ttu-id="527c8-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="527c8-120">Data Item Type</span></span>|<span data-ttu-id="527c8-121">설명</span><span class="sxs-lookup"><span data-stu-id="527c8-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="527c8-122">TypeName</span><span class="sxs-lookup"><span data-stu-id="527c8-122">TypeName</span></span>|`xs:string`|<span data-ttu-id="527c8-123">호출된 `ErrorHandler` 형식의 CLR FullName입니다.</span><span class="sxs-lookup"><span data-stu-id="527c8-123">The CLR FullName of the type of the invoked `ErrorHandler`.</span></span>|  
|<span data-ttu-id="527c8-124">처리됨</span><span class="sxs-lookup"><span data-stu-id="527c8-124">Handled</span></span>|`xs:unsignedByte`|<span data-ttu-id="527c8-125">오류 처리기가 오류를 처리했으면 `true`이고, 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="527c8-125">`true` if the error handler handled the error, otherwise `false`.</span></span>|  
|<span data-ttu-id="527c8-126">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="527c8-126">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="527c8-127">처리된 예외의 CLR FullName입니다.</span><span class="sxs-lookup"><span data-stu-id="527c8-127">The CLR FullName of the exception that was being handled.</span></span>|  
|<span data-ttu-id="527c8-128">HostReference</span><span class="sxs-lookup"><span data-stu-id="527c8-128">HostReference</span></span>|`xs:string`|<span data-ttu-id="527c8-129">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="527c8-129">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="527c8-130">해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="527c8-130">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="527c8-131">예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="527c8-131">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="527c8-132">AppDomain</span><span class="sxs-lookup"><span data-stu-id="527c8-132">AppDomain</span></span>|`xs:string`|<span data-ttu-id="527c8-133">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="527c8-133">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
