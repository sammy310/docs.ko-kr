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
# <a name="499---transferemitted"></a><span data-ttu-id="9e896-102">499 - TransferEmitted</span><span class="sxs-lookup"><span data-stu-id="9e896-102">499 - TransferEmitted</span></span>
## <a name="properties"></a><span data-ttu-id="9e896-103">속성</span><span class="sxs-lookup"><span data-stu-id="9e896-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9e896-104">ID</span><span class="sxs-lookup"><span data-stu-id="9e896-104">ID</span></span>|<span data-ttu-id="9e896-105">499</span><span class="sxs-lookup"><span data-stu-id="9e896-105">499</span></span>|  
|<span data-ttu-id="9e896-106">키워드</span><span class="sxs-lookup"><span data-stu-id="9e896-106">Keywords</span></span>|<span data-ttu-id="9e896-107">문제 해결, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span><span class="sxs-lookup"><span data-stu-id="9e896-107">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span></span>|  
|<span data-ttu-id="9e896-108">수준</span><span class="sxs-lookup"><span data-stu-id="9e896-108">Level</span></span>|<span data-ttu-id="9e896-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="9e896-109">LogAlways</span></span>|  
|<span data-ttu-id="9e896-110">채널</span><span class="sxs-lookup"><span data-stu-id="9e896-110">Channel</span></span>|<span data-ttu-id="9e896-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="9e896-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9e896-112">설명</span><span class="sxs-lookup"><span data-stu-id="9e896-112">Description</span></span>  
 <span data-ttu-id="9e896-113">전송 이벤트가 발생하는 경우 이 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="9e896-113">This event is emitted when the transfer event takes place.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9e896-114">메시지</span><span class="sxs-lookup"><span data-stu-id="9e896-114">Message</span></span>  
 <span data-ttu-id="9e896-115">전송 이벤트를 내보냈습니다.</span><span class="sxs-lookup"><span data-stu-id="9e896-115">Transfer event emitted.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9e896-116">설명</span><span class="sxs-lookup"><span data-stu-id="9e896-116">Details</span></span>  
  
|<span data-ttu-id="9e896-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="9e896-117">Data Item Name</span></span>|<span data-ttu-id="9e896-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="9e896-118">Data Item Type</span></span>|<span data-ttu-id="9e896-119">설명</span><span class="sxs-lookup"><span data-stu-id="9e896-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9e896-120">HostReference</span><span class="sxs-lookup"><span data-stu-id="9e896-120">HostReference</span></span>|`xs:string`|<span data-ttu-id="9e896-121">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="9e896-121">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="9e896-122">해당 형식으로 정의 됩니다 ' Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="9e896-122">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="9e896-123">예제: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="9e896-123">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="9e896-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9e896-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="9e896-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9e896-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
