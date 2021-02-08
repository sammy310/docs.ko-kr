---
description: '자세한 정보: 219-ServiceException'
title: 219 - ServiceException
ms.date: 03/30/2017
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
ms.openlocfilehash: b2ac12d6c5c68517b085b39dd7d0f81c39db9ebd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794327"
---
# <a name="219---serviceexception"></a><span data-ttu-id="651a4-103">219 - ServiceException</span><span class="sxs-lookup"><span data-stu-id="651a4-103">219 - ServiceException</span></span>

## <a name="properties"></a><span data-ttu-id="651a4-104">속성</span><span class="sxs-lookup"><span data-stu-id="651a4-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="651a4-105">ID</span><span class="sxs-lookup"><span data-stu-id="651a4-105">ID</span></span>|<span data-ttu-id="651a4-106">219</span><span class="sxs-lookup"><span data-stu-id="651a4-106">219</span></span>|  
|<span data-ttu-id="651a4-107">키워드</span><span class="sxs-lookup"><span data-stu-id="651a4-107">Keywords</span></span>|<span data-ttu-id="651a4-108">EndToEndMonitoring, HealthMonitoring, 문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="651a4-108">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="651a4-109">Level</span><span class="sxs-lookup"><span data-stu-id="651a4-109">Level</span></span>|<span data-ttu-id="651a4-110">Error</span><span class="sxs-lookup"><span data-stu-id="651a4-110">Error</span></span>|  
|<span data-ttu-id="651a4-111">채널</span><span class="sxs-lookup"><span data-stu-id="651a4-111">Channel</span></span>|<span data-ttu-id="651a4-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="651a4-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="651a4-113">설명</span><span class="sxs-lookup"><span data-stu-id="651a4-113">Description</span></span>  

 <span data-ttu-id="651a4-114">이 이벤트는 WCF 서비스에서 처리되지 않은 예외가 발생할 때 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="651a4-114">This event is emitted when a WCF service encounters an unhandled exception.</span></span> <span data-ttu-id="651a4-115">이러한 처리되지 않은 예외로는 활성화 중에 발생한 예외, 메시지 처리 중에 발생한 예외 및 사용자 코드에서 발생한 예외가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="651a4-115">This includes unhandled exceptions during activation, during message processing, and in user code.</span></span>  
  
## <a name="message"></a><span data-ttu-id="651a4-116">메시지</span><span class="sxs-lookup"><span data-stu-id="651a4-116">Message</span></span>  

 <span data-ttu-id="651a4-117">메시지를 처리하는 동안 '%2' 형식의 처리되지 않은 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="651a4-117">There was an unhandled exception of type '%2' during message processing.</span></span> <span data-ttu-id="651a4-118">전체 예외 ToString: %1.</span><span class="sxs-lookup"><span data-stu-id="651a4-118">Full Exception ToString: %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="651a4-119">세부 정보</span><span class="sxs-lookup"><span data-stu-id="651a4-119">Details</span></span>  
  
|<span data-ttu-id="651a4-120">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="651a4-120">Data Item Name</span></span>|<span data-ttu-id="651a4-121">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="651a4-121">Data Item Type</span></span>|<span data-ttu-id="651a4-122">설명</span><span class="sxs-lookup"><span data-stu-id="651a4-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="651a4-123">ExceptionToString</span><span class="sxs-lookup"><span data-stu-id="651a4-123">ExceptionToString</span></span>|`xs:string`|<span data-ttu-id="651a4-124">CLR 예외에 대해 `ToString`()을 호출한 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="651a4-124">The result of calling `ToString`() on the CLR exception.</span></span>|  
|<span data-ttu-id="651a4-125">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="651a4-125">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="651a4-126">예외 형식의 CLR FullName입니다.</span><span class="sxs-lookup"><span data-stu-id="651a4-126">The CLR FullName of the exception's type.</span></span>|  
|<span data-ttu-id="651a4-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="651a4-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="651a4-128">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="651a4-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="651a4-129">해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="651a4-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="651a4-130">예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="651a4-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="651a4-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="651a4-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="651a4-132">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="651a4-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
