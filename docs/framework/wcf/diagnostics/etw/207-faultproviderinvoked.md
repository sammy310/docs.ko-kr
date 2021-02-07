---
description: '자세한 정보: 207-FaultProviderInvoked'
title: 207 - FaultProviderInvoked
ms.date: 03/30/2017
ms.assetid: b730d903-01c2-4deb-85a4-da12f8a21fe4
ms.openlocfilehash: 03c4f1669fc61019ccf4d23d2994f136e231fbec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728069"
---
# <a name="207---faultproviderinvoked"></a><span data-ttu-id="638f4-103">207 - FaultProviderInvoked</span><span class="sxs-lookup"><span data-stu-id="638f4-103">207 - FaultProviderInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="638f4-104">속성</span><span class="sxs-lookup"><span data-stu-id="638f4-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="638f4-105">ID</span><span class="sxs-lookup"><span data-stu-id="638f4-105">ID</span></span>|<span data-ttu-id="638f4-106">207</span><span class="sxs-lookup"><span data-stu-id="638f4-106">207</span></span>|  
|<span data-ttu-id="638f4-107">키워드</span><span class="sxs-lookup"><span data-stu-id="638f4-107">Keywords</span></span>|<span data-ttu-id="638f4-108">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="638f4-108">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="638f4-109">Level</span><span class="sxs-lookup"><span data-stu-id="638f4-109">Level</span></span>|<span data-ttu-id="638f4-110">정보</span><span class="sxs-lookup"><span data-stu-id="638f4-110">Information</span></span>|  
|<span data-ttu-id="638f4-111">채널</span><span class="sxs-lookup"><span data-stu-id="638f4-111">Channel</span></span>|<span data-ttu-id="638f4-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="638f4-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="638f4-113">설명</span><span class="sxs-lookup"><span data-stu-id="638f4-113">Description</span></span>  

 <span data-ttu-id="638f4-114">이 이벤트는 `FaultProvider`가 호출된 후에 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="638f4-114">This event is emitted after a `FaultProvider` has been invoked.</span></span>  
  
## <a name="message"></a><span data-ttu-id="638f4-115">메시지</span><span class="sxs-lookup"><span data-stu-id="638f4-115">Message</span></span>  

 <span data-ttu-id="638f4-116">디스패처가 '%2' 형식의 예외와 함께 '%1' 형식의 FaultProvider를 호출했습니다.</span><span class="sxs-lookup"><span data-stu-id="638f4-116">The Dispatcher invoked a FaultProvider of type '%1' with an exception of type '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="638f4-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="638f4-117">Details</span></span>  
  
|<span data-ttu-id="638f4-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="638f4-118">Data Item Name</span></span>|<span data-ttu-id="638f4-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="638f4-119">Data Item Type</span></span>|<span data-ttu-id="638f4-120">설명</span><span class="sxs-lookup"><span data-stu-id="638f4-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="638f4-121">TypeName</span><span class="sxs-lookup"><span data-stu-id="638f4-121">TypeName</span></span>|`xs:string`|<span data-ttu-id="638f4-122">호출된 `FaultProvider` 형식의 CLR FullName입니다.</span><span class="sxs-lookup"><span data-stu-id="638f4-122">The CLR FullName of the type of the invoked `FaultProvider`.</span></span>|  
|<span data-ttu-id="638f4-123">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="638f4-123">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="638f4-124">`FaultProvider`가 처리한 예외의 CLR FullName입니다.</span><span class="sxs-lookup"><span data-stu-id="638f4-124">The CLR FullName of the exception that the `FaultProvider` has operated on.</span></span>|  
|<span data-ttu-id="638f4-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="638f4-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="638f4-126">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="638f4-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="638f4-127">해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="638f4-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="638f4-128">예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="638f4-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="638f4-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="638f4-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="638f4-130">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="638f4-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
