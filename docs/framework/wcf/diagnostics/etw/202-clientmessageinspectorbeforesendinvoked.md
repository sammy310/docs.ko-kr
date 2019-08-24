---
title: 202 - ClientMessageInspectorBeforeSendInvoked
ms.date: 03/30/2017
ms.assetid: 0b02ca82-8a55-45e3-b2e2-ddfe28a7269c
ms.openlocfilehash: 98de1d7e8e5e87ec7fbd783092f7fbc212fec65d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781994"
---
# <a name="202---clientmessageinspectorbeforesendinvoked"></a><span data-ttu-id="b97f6-102">202 - ClientMessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="b97f6-102">202 - ClientMessageInspectorBeforeSendInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="b97f6-103">속성</span><span class="sxs-lookup"><span data-stu-id="b97f6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b97f6-104">ID</span><span class="sxs-lookup"><span data-stu-id="b97f6-104">ID</span></span>|<span data-ttu-id="b97f6-105">202</span><span class="sxs-lookup"><span data-stu-id="b97f6-105">202</span></span>|  
|<span data-ttu-id="b97f6-106">키워드</span><span class="sxs-lookup"><span data-stu-id="b97f6-106">Keywords</span></span>|<span data-ttu-id="b97f6-107">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b97f6-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="b97f6-108">수준</span><span class="sxs-lookup"><span data-stu-id="b97f6-108">Level</span></span>|<span data-ttu-id="b97f6-109">정보</span><span class="sxs-lookup"><span data-stu-id="b97f6-109">Information</span></span>|  
|<span data-ttu-id="b97f6-110">채널</span><span class="sxs-lookup"><span data-stu-id="b97f6-110">Channel</span></span>|<span data-ttu-id="b97f6-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="b97f6-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b97f6-112">설명</span><span class="sxs-lookup"><span data-stu-id="b97f6-112">Description</span></span>  
 <span data-ttu-id="b97f6-113">이 이벤트는 서비스 모델이 클라이언트 메시지 검사자에 대해 `BeforeSendRequest` 메서드를 호출한 후에 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="b97f6-113">This event is emitted after the Service Model has invoked the `BeforeSendRequest` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b97f6-114">메시지</span><span class="sxs-lookup"><span data-stu-id="b97f6-114">Message</span></span>  
 <span data-ttu-id="b97f6-115">디스패처가 '%1' 형식의 ClientMessageInspector에 대해 'BeforeSendRequest'를 호출했습니다.</span><span class="sxs-lookup"><span data-stu-id="b97f6-115">The Dispatcher invoked 'BeforeSendRequest' on a ClientMessageInspector of type  '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b97f6-116">설명</span><span class="sxs-lookup"><span data-stu-id="b97f6-116">Details</span></span>  
  
|<span data-ttu-id="b97f6-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="b97f6-117">Data Item Name</span></span>|<span data-ttu-id="b97f6-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="b97f6-118">Data Item Type</span></span>|<span data-ttu-id="b97f6-119">설명</span><span class="sxs-lookup"><span data-stu-id="b97f6-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b97f6-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="b97f6-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="b97f6-121">호출된 검사자 형식의 CLR FullName입니다.</span><span class="sxs-lookup"><span data-stu-id="b97f6-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="b97f6-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="b97f6-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="b97f6-123">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="b97f6-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="b97f6-124">해당 형식으로 정의 됩니다 ' Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="b97f6-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="b97f6-125">예제: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="b97f6-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="b97f6-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b97f6-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="b97f6-127">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b97f6-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
