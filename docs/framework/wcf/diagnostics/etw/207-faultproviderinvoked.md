---
title: 207 - FaultProviderInvoked
ms.date: 03/30/2017
ms.assetid: b730d903-01c2-4deb-85a4-da12f8a21fe4
ms.openlocfilehash: 9f97e74e7685d57b487f456625826ee9cd8e1760
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781916"
---
# <a name="207---faultproviderinvoked"></a><span data-ttu-id="05d0f-102">207 - FaultProviderInvoked</span><span class="sxs-lookup"><span data-stu-id="05d0f-102">207 - FaultProviderInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="05d0f-103">속성</span><span class="sxs-lookup"><span data-stu-id="05d0f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="05d0f-104">ID</span><span class="sxs-lookup"><span data-stu-id="05d0f-104">ID</span></span>|<span data-ttu-id="05d0f-105">207</span><span class="sxs-lookup"><span data-stu-id="05d0f-105">207</span></span>|  
|<span data-ttu-id="05d0f-106">키워드</span><span class="sxs-lookup"><span data-stu-id="05d0f-106">Keywords</span></span>|<span data-ttu-id="05d0f-107">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="05d0f-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="05d0f-108">수준</span><span class="sxs-lookup"><span data-stu-id="05d0f-108">Level</span></span>|<span data-ttu-id="05d0f-109">정보</span><span class="sxs-lookup"><span data-stu-id="05d0f-109">Information</span></span>|  
|<span data-ttu-id="05d0f-110">채널</span><span class="sxs-lookup"><span data-stu-id="05d0f-110">Channel</span></span>|<span data-ttu-id="05d0f-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="05d0f-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="05d0f-112">설명</span><span class="sxs-lookup"><span data-stu-id="05d0f-112">Description</span></span>  
 <span data-ttu-id="05d0f-113">이 이벤트는 `FaultProvider`가 호출된 후에 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="05d0f-113">This event is emitted after a `FaultProvider` has been invoked.</span></span>  
  
## <a name="message"></a><span data-ttu-id="05d0f-114">메시지</span><span class="sxs-lookup"><span data-stu-id="05d0f-114">Message</span></span>  
 <span data-ttu-id="05d0f-115">디스패처가 '%2' 형식의 예외와 함께 '%1' 형식의 FaultProvider를 호출했습니다.</span><span class="sxs-lookup"><span data-stu-id="05d0f-115">The Dispatcher invoked a FaultProvider of type '%1' with an exception of type '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="05d0f-116">설명</span><span class="sxs-lookup"><span data-stu-id="05d0f-116">Details</span></span>  
  
|<span data-ttu-id="05d0f-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="05d0f-117">Data Item Name</span></span>|<span data-ttu-id="05d0f-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="05d0f-118">Data Item Type</span></span>|<span data-ttu-id="05d0f-119">설명</span><span class="sxs-lookup"><span data-stu-id="05d0f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="05d0f-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="05d0f-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="05d0f-121">호출된 `FaultProvider` 형식의 CLR FullName입니다.</span><span class="sxs-lookup"><span data-stu-id="05d0f-121">The CLR FullName of the type of the invoked `FaultProvider`.</span></span>|  
|<span data-ttu-id="05d0f-122">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="05d0f-122">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="05d0f-123">`FaultProvider`가 처리한 예외의 CLR FullName입니다.</span><span class="sxs-lookup"><span data-stu-id="05d0f-123">The CLR FullName of the exception that the `FaultProvider` has operated on.</span></span>|  
|<span data-ttu-id="05d0f-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="05d0f-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="05d0f-125">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="05d0f-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="05d0f-126">해당 형식으로 정의 됩니다 ' Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="05d0f-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="05d0f-127">예제: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="05d0f-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="05d0f-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="05d0f-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="05d0f-129">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="05d0f-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
