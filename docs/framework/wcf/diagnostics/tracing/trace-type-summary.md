---
title: 추적 형식 요약
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: 8ed6dceb19caa52f928f285064c60337e3f15a87
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674833"
---
# <a name="trace-type-summary"></a><span data-ttu-id="381c9-102">추적 형식 요약</span><span class="sxs-lookup"><span data-stu-id="381c9-102">Trace Type Summary</span></span>
<span data-ttu-id="381c9-103">[소스 수준은](xref:System.Diagnostics.SourceLevels) 중요, 오류, 경고, 정보 및 세부 정보 등 다양한 추적 수준을 `ActivityTracing` 정의하고 추적 경계 및 활동 전송 이벤트의 출력을 전환하는 플래그에 대한 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="381c9-103">[Source Levels](xref:System.Diagnostics.SourceLevels) defines various trace levels: Critical, Error, Warning, Information, and Verbose, as well as provides a description of the `ActivityTracing` flag, which toggles the output of trace boundary and activity transfer events.</span></span>  
  
 <span data-ttu-id="381c9-104">에서 내보내질 수 있는 추적 유형을 검토할 <xref:System.Diagnostics.TraceEventType> 수도 있습니다. <xref:System.Diagnostics></span><span class="sxs-lookup"><span data-stu-id="381c9-104">You can also review <xref:System.Diagnostics.TraceEventType> for the types of traces which can be emitted from <xref:System.Diagnostics>.</span></span>  
  
 <span data-ttu-id="381c9-105">다음 표에서는 가장 중요한 항목을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="381c9-105">The following table lists the most important ones.</span></span>  
  
|<span data-ttu-id="381c9-106">추적 형식</span><span class="sxs-lookup"><span data-stu-id="381c9-106">Trace Type</span></span>|<span data-ttu-id="381c9-107">Description</span><span class="sxs-lookup"><span data-stu-id="381c9-107">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="381c9-108">위험</span><span class="sxs-lookup"><span data-stu-id="381c9-108">Critical</span></span>|<span data-ttu-id="381c9-109">오류 또는 애플리케이션 충돌</span><span class="sxs-lookup"><span data-stu-id="381c9-109">Fatal error or application crash.</span></span>|  
|<span data-ttu-id="381c9-110">Error</span><span class="sxs-lookup"><span data-stu-id="381c9-110">Error</span></span>|<span data-ttu-id="381c9-111">복구할 수 있는 오류</span><span class="sxs-lookup"><span data-stu-id="381c9-111">Recoverable error.</span></span>|  
|<span data-ttu-id="381c9-112">Warning</span><span class="sxs-lookup"><span data-stu-id="381c9-112">Warning</span></span>|<span data-ttu-id="381c9-113">정보 메시지.</span><span class="sxs-lookup"><span data-stu-id="381c9-113">Informational message.</span></span>|  
|<span data-ttu-id="381c9-114">정보</span><span class="sxs-lookup"><span data-stu-id="381c9-114">Information</span></span>|<span data-ttu-id="381c9-115">중요하지 않은 문제</span><span class="sxs-lookup"><span data-stu-id="381c9-115">Non-critical problem.</span></span>|  
|<span data-ttu-id="381c9-116">자세히</span><span class="sxs-lookup"><span data-stu-id="381c9-116">Verbose</span></span>|<span data-ttu-id="381c9-117">추적 디버깅</span><span class="sxs-lookup"><span data-stu-id="381c9-117">Debugging trace.</span></span>|  
|<span data-ttu-id="381c9-118">시작</span><span class="sxs-lookup"><span data-stu-id="381c9-118">Start</span></span>|<span data-ttu-id="381c9-119">처리의 논리 단위 시작</span><span class="sxs-lookup"><span data-stu-id="381c9-119">Starting of a logical unit of processing.</span></span>|  
|<span data-ttu-id="381c9-120">일시 중지됨</span><span class="sxs-lookup"><span data-stu-id="381c9-120">Suspend</span></span>|<span data-ttu-id="381c9-121">처리의 논리 단위 일시 중단</span><span class="sxs-lookup"><span data-stu-id="381c9-121">Suspension of a logical unit of processing.</span></span>|  
|<span data-ttu-id="381c9-122">다시 시작</span><span class="sxs-lookup"><span data-stu-id="381c9-122">Resume</span></span>|<span data-ttu-id="381c9-123">처리의 논리 단위 다시 시작</span><span class="sxs-lookup"><span data-stu-id="381c9-123">Resumption of a logical unit of processing.</span></span>|  
|<span data-ttu-id="381c9-124">중지</span><span class="sxs-lookup"><span data-stu-id="381c9-124">Stop</span></span>|<span data-ttu-id="381c9-125">처리의 논리 단위 중지</span><span class="sxs-lookup"><span data-stu-id="381c9-125">Stopping of a logical unit of processing.</span></span>|  
|<span data-ttu-id="381c9-126">전송</span><span class="sxs-lookup"><span data-stu-id="381c9-126">Transfer</span></span>|<span data-ttu-id="381c9-127">상관 관계 ID의 변경</span><span class="sxs-lookup"><span data-stu-id="381c9-127">Changing of correlation identity.</span></span>|  
  
 <span data-ttu-id="381c9-128">동작은 위의 추적 형식의 조합으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="381c9-128">An activity is defined as a combination of the trace types above.</span></span>  
  
 <span data-ttu-id="381c9-129">다음은 로컬(추적 소스) 범위에서 이상적인 동작을 정의하는 정규식입니다.</span><span class="sxs-lookup"><span data-stu-id="381c9-129">The following is a regular expression that defines an ideal activity in a local (trace source) scope,</span></span>  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 <span data-ttu-id="381c9-130">이는 동작이 다음 조건을 만족해야 함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="381c9-130">This means that an activity must satisfy the following conditions.</span></span>  
  
- <span data-ttu-id="381c9-131">Start 및 Stop 추적에 의해 각각 시작되고 중지되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="381c9-131">It must start and stop respectively by a Start and Stop traces</span></span>  
  
- <span data-ttu-id="381c9-132">Suspend 추적 또는 Resume 추적의 바로 앞에 Transfer 추적이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="381c9-132">It must have a Transfer trace immediately preceding a Suspend or Resume trace</span></span>  
  
- <span data-ttu-id="381c9-133">Suspend 추적 및 Resume 추적이 존재할 경우 이 사이에 추적이 있으면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="381c9-133">It must not have any traces between the Suspend and Resume traces if such traces exist</span></span>  
  
- <span data-ttu-id="381c9-134">위와 같은 조건이 충족되는 한 Critical/Error/Warning/Information/Verbose/Transfer 추적은 여러 개가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="381c9-134">It can have any and as many of critical/Error/Warning/Information/Verbose/Transfer traces as long as the previous conditions are observed</span></span>  
  
 <span data-ttu-id="381c9-135">다음은 전역 범위에서 이상적인 동작을 정의하는 정규식입니다.</span><span class="sxs-lookup"><span data-stu-id="381c9-135">The following is a regular expression that defines an ideal activity in the global scope,</span></span>  
  
`R+`  
  
 <span data-ttu-id="381c9-136">로컬 범위에서 동작에 대한 정규식인 R을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="381c9-136">with R being the regular expression for an activity in the local scope.</span></span> <span data-ttu-id="381c9-137">이는 다음으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="381c9-137">This translates to,</span></span>  
  
`[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+`
