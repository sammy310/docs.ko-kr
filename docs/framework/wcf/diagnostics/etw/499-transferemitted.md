---
title: 499 - TransferEmitted
ms.date: 03/30/2017
ms.assetid: 07a26434-a7a0-40fc-b5d0-3520a04328ae
ms.openlocfilehash: b1ade828ee6519288165e272e7d9f36fd6aca9ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774935"
---
# <a name="499---transferemitted"></a><span data-ttu-id="49ba9-102">499 - TransferEmitted</span><span class="sxs-lookup"><span data-stu-id="49ba9-102">499 - TransferEmitted</span></span>
## <a name="properties"></a><span data-ttu-id="49ba9-103">속성</span><span class="sxs-lookup"><span data-stu-id="49ba9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="49ba9-104">ID</span><span class="sxs-lookup"><span data-stu-id="49ba9-104">ID</span></span>|<span data-ttu-id="49ba9-105">499</span><span class="sxs-lookup"><span data-stu-id="49ba9-105">499</span></span>|  
|<span data-ttu-id="49ba9-106">키워드</span><span class="sxs-lookup"><span data-stu-id="49ba9-106">Keywords</span></span>|<span data-ttu-id="49ba9-107">문제 해결, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span><span class="sxs-lookup"><span data-stu-id="49ba9-107">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span></span>|  
|<span data-ttu-id="49ba9-108">수준</span><span class="sxs-lookup"><span data-stu-id="49ba9-108">Level</span></span>|<span data-ttu-id="49ba9-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="49ba9-109">LogAlways</span></span>|  
|<span data-ttu-id="49ba9-110">채널</span><span class="sxs-lookup"><span data-stu-id="49ba9-110">Channel</span></span>|<span data-ttu-id="49ba9-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="49ba9-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="49ba9-112">설명</span><span class="sxs-lookup"><span data-stu-id="49ba9-112">Description</span></span>  
 <span data-ttu-id="49ba9-113">전송 이벤트가 발생하는 경우 이 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="49ba9-113">This event is emitted when the transfer event takes place.</span></span>  
  
## <a name="message"></a><span data-ttu-id="49ba9-114">메시지</span><span class="sxs-lookup"><span data-stu-id="49ba9-114">Message</span></span>  
 <span data-ttu-id="49ba9-115">전송 이벤트를 내보냈습니다.</span><span class="sxs-lookup"><span data-stu-id="49ba9-115">Transfer event emitted.</span></span>  
  
## <a name="details"></a><span data-ttu-id="49ba9-116">설명</span><span class="sxs-lookup"><span data-stu-id="49ba9-116">Details</span></span>  
  
|<span data-ttu-id="49ba9-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="49ba9-117">Data Item Name</span></span>|<span data-ttu-id="49ba9-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="49ba9-118">Data Item Type</span></span>|<span data-ttu-id="49ba9-119">설명</span><span class="sxs-lookup"><span data-stu-id="49ba9-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="49ba9-120">HostReference</span><span class="sxs-lookup"><span data-stu-id="49ba9-120">HostReference</span></span>|`xs:string`|<span data-ttu-id="49ba9-121">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="49ba9-121">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="49ba9-122">해당 형식으로 정의 됩니다 ' Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="49ba9-122">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="49ba9-123">예제: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="49ba9-123">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="49ba9-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="49ba9-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="49ba9-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="49ba9-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
