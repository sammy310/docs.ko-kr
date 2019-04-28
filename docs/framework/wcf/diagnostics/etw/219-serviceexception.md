---
title: 219 - ServiceException
ms.date: 03/30/2017
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
ms.openlocfilehash: eb4289c0346c9e1d9481347d69db8c5f007e4325
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781734"
---
# <a name="219---serviceexception"></a><span data-ttu-id="fbbdd-102">219 - ServiceException</span><span class="sxs-lookup"><span data-stu-id="fbbdd-102">219 - ServiceException</span></span>
## <a name="properties"></a><span data-ttu-id="fbbdd-103">속성</span><span class="sxs-lookup"><span data-stu-id="fbbdd-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fbbdd-104">ID</span><span class="sxs-lookup"><span data-stu-id="fbbdd-104">ID</span></span>|<span data-ttu-id="fbbdd-105">219</span><span class="sxs-lookup"><span data-stu-id="fbbdd-105">219</span></span>|  
|<span data-ttu-id="fbbdd-106">키워드</span><span class="sxs-lookup"><span data-stu-id="fbbdd-106">Keywords</span></span>|<span data-ttu-id="fbbdd-107">EndToEndMonitoring, HealthMonitoring, 문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fbbdd-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="fbbdd-108">수준</span><span class="sxs-lookup"><span data-stu-id="fbbdd-108">Level</span></span>|<span data-ttu-id="fbbdd-109">Error</span><span class="sxs-lookup"><span data-stu-id="fbbdd-109">Error</span></span>|  
|<span data-ttu-id="fbbdd-110">채널</span><span class="sxs-lookup"><span data-stu-id="fbbdd-110">Channel</span></span>|<span data-ttu-id="fbbdd-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="fbbdd-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fbbdd-112">설명</span><span class="sxs-lookup"><span data-stu-id="fbbdd-112">Description</span></span>  
 <span data-ttu-id="fbbdd-113">이 이벤트는 WCF 서비스에서 처리되지 않은 예외가 발생할 때 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="fbbdd-113">This event is emitted when a WCF service encounters an unhandled exception.</span></span> <span data-ttu-id="fbbdd-114">이러한 처리되지 않은 예외로는 활성화 중에 발생한 예외, 메시지 처리 중에 발생한 예외 및 사용자 코드에서 발생한 예외가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbbdd-114">This includes unhandled exceptions during activation, during message processing, and in user code.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fbbdd-115">메시지</span><span class="sxs-lookup"><span data-stu-id="fbbdd-115">Message</span></span>  
 <span data-ttu-id="fbbdd-116">메시지를 처리하는 동안 '%2' 형식의 처리되지 않은 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="fbbdd-116">There was an unhandled exception of type '%2' during message processing.</span></span> <span data-ttu-id="fbbdd-117">전체 예외 ToString: %1.</span><span class="sxs-lookup"><span data-stu-id="fbbdd-117">Full Exception ToString: %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fbbdd-118">설명</span><span class="sxs-lookup"><span data-stu-id="fbbdd-118">Details</span></span>  
  
|<span data-ttu-id="fbbdd-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="fbbdd-119">Data Item Name</span></span>|<span data-ttu-id="fbbdd-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="fbbdd-120">Data Item Type</span></span>|<span data-ttu-id="fbbdd-121">설명</span><span class="sxs-lookup"><span data-stu-id="fbbdd-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fbbdd-122">ExceptionToString</span><span class="sxs-lookup"><span data-stu-id="fbbdd-122">ExceptionToString</span></span>|`xs:string`|<span data-ttu-id="fbbdd-123">CLR 예외에 대해 `ToString`()을 호출한 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="fbbdd-123">The result of calling `ToString`() on the CLR exception.</span></span>|  
|<span data-ttu-id="fbbdd-124">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="fbbdd-124">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="fbbdd-125">예외 형식의 CLR FullName입니다.</span><span class="sxs-lookup"><span data-stu-id="fbbdd-125">The CLR FullName of the exception's type.</span></span>|  
|<span data-ttu-id="fbbdd-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="fbbdd-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="fbbdd-127">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbdd-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="fbbdd-128">해당 형식으로 정의 됩니다 ' Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="fbbdd-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="fbbdd-129">예제: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="fbbdd-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="fbbdd-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fbbdd-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="fbbdd-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fbbdd-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
