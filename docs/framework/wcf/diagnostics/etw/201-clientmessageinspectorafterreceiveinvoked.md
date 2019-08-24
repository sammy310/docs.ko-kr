---
title: 201 - ClientMessageInspectorAfterReceiveInvoked
ms.date: 03/30/2017
ms.assetid: 9ff637f1-cc26-4400-ab9b-546f70e5057d
ms.openlocfilehash: 96ca318c141d49e2ac5594d5ee101658a2aa8f21
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782040"
---
# <a name="201---clientmessageinspectorafterreceiveinvoked"></a><span data-ttu-id="5f7ab-102">201 - ClientMessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="5f7ab-102">201 - ClientMessageInspectorAfterReceiveInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="5f7ab-103">속성</span><span class="sxs-lookup"><span data-stu-id="5f7ab-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5f7ab-104">ID</span><span class="sxs-lookup"><span data-stu-id="5f7ab-104">ID</span></span>|<span data-ttu-id="5f7ab-105">201</span><span class="sxs-lookup"><span data-stu-id="5f7ab-105">201</span></span>|  
|<span data-ttu-id="5f7ab-106">키워드</span><span class="sxs-lookup"><span data-stu-id="5f7ab-106">Keywords</span></span>|<span data-ttu-id="5f7ab-107">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="5f7ab-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="5f7ab-108">수준</span><span class="sxs-lookup"><span data-stu-id="5f7ab-108">Level</span></span>|<span data-ttu-id="5f7ab-109">정보</span><span class="sxs-lookup"><span data-stu-id="5f7ab-109">Information</span></span>|  
|<span data-ttu-id="5f7ab-110">채널</span><span class="sxs-lookup"><span data-stu-id="5f7ab-110">Channel</span></span>|<span data-ttu-id="5f7ab-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="5f7ab-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5f7ab-112">설명</span><span class="sxs-lookup"><span data-stu-id="5f7ab-112">Description</span></span>  
 <span data-ttu-id="5f7ab-113">이 이벤트는 서비스 모델이 클라이언트 메시지 검사자에 대해 `AfterReceiveReply` 메서드를 호출한 후에 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="5f7ab-113">This event is emitted after the Service Model has invoked the `AfterReceiveReply` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5f7ab-114">메시지</span><span class="sxs-lookup"><span data-stu-id="5f7ab-114">Message</span></span>  
 <span data-ttu-id="5f7ab-115">디스패처가 '%1' 형식의 ClientMessageInspector에 대해 'AfterReceiveReply'를 호출했습니다.</span><span class="sxs-lookup"><span data-stu-id="5f7ab-115">The Dispatcher invoked 'AfterReceiveReply' on a ClientMessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5f7ab-116">설명</span><span class="sxs-lookup"><span data-stu-id="5f7ab-116">Details</span></span>  
  
|<span data-ttu-id="5f7ab-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="5f7ab-117">Data Item Name</span></span>|<span data-ttu-id="5f7ab-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="5f7ab-118">Data Item Type</span></span>|<span data-ttu-id="5f7ab-119">설명</span><span class="sxs-lookup"><span data-stu-id="5f7ab-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5f7ab-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="5f7ab-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="5f7ab-121">호출된 검사자 형식의 CLR FullName입니다.</span><span class="sxs-lookup"><span data-stu-id="5f7ab-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="5f7ab-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="5f7ab-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="5f7ab-123">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="5f7ab-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="5f7ab-124">해당 형식으로 정의 됩니다 ' Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="5f7ab-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="5f7ab-125">예제: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="5f7ab-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="5f7ab-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5f7ab-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="5f7ab-127">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5f7ab-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
