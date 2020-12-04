---
title: 형식 시스템 런타임 이벤트
description: '.NET 형식 시스템과 관련 된 진단 정보를 수집 하는 .NET 런타임 이벤트 (예: TypeLoadStart 및 Typeloadstart)를 참조 하세요.'
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- type system events (CoreCLR)
- ETW, EventPipe, LTTng type system events (CoreCLR)
ms.openlocfilehash: 8eee89cddb0098da2cb449a4be21945adac725e3
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "96594039"
---
# <a name="net-runtime-type-events"></a><span data-ttu-id="a9e93-103">.NET 런타임 형식 이벤트</span><span class="sxs-lookup"><span data-stu-id="a9e93-103">.NET runtime type events</span></span>

<span data-ttu-id="a9e93-104">이러한 이벤트는 형식 로드와 관련 된 정보를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e93-104">These events collect information relating to loading types.</span></span> <span data-ttu-id="a9e93-105">진단 목적으로 이러한 이벤트를 사용 하는 방법에 대 한 자세한 내용은 [.net 응용 프로그램 로깅 및 추적](../../core/diagnostics/logging-tracing.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9e93-105">For more information about how to use these events for diagnostic purposes, see [logging and tracing .NET applications](../../core/diagnostics/logging-tracing.md)</span></span>

## <a name="typeloadstart-event"></a><span data-ttu-id="a9e93-106">TypeLoadStart 이벤트</span><span class="sxs-lookup"><span data-stu-id="a9e93-106">TypeLoadStart Event</span></span>

|<span data-ttu-id="a9e93-107">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="a9e93-107">Keyword for raising the event</span></span>|<span data-ttu-id="a9e93-108">이벤트</span><span class="sxs-lookup"><span data-stu-id="a9e93-108">Event</span></span>|<span data-ttu-id="a9e93-109">수준</span><span class="sxs-lookup"><span data-stu-id="a9e93-109">Level</span></span>|  
|-----------------------------------|-----------|-----------|  
|<span data-ttu-id="a9e93-110">`TypeDiagnosticKeyword` (0x8000000000)</span><span class="sxs-lookup"><span data-stu-id="a9e93-110">`TypeDiagnosticKeyword` (0x8000000000)</span></span>|<span data-ttu-id="a9e93-111">정보(4)</span><span class="sxs-lookup"><span data-stu-id="a9e93-111">Informational (4)</span></span>|  

|<span data-ttu-id="a9e93-112">이벤트</span><span class="sxs-lookup"><span data-stu-id="a9e93-112">Event</span></span>|<span data-ttu-id="a9e93-113">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="a9e93-113">Event ID</span></span>|<span data-ttu-id="a9e93-114">Description</span><span class="sxs-lookup"><span data-stu-id="a9e93-114">Description</span></span>|  
|-----------|--------------|-----------------|  
|`TypeLoadStart`|<span data-ttu-id="a9e93-115">73</span><span class="sxs-lookup"><span data-stu-id="a9e93-115">73</span></span>|<span data-ttu-id="a9e93-116">유형 로드가 시작 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a9e93-116">A type load has started.</span></span>|

|<span data-ttu-id="a9e93-117">필드 이름</span><span class="sxs-lookup"><span data-stu-id="a9e93-117">Field name</span></span>|<span data-ttu-id="a9e93-118">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a9e93-118">Data type</span></span>|<span data-ttu-id="a9e93-119">Description</span><span class="sxs-lookup"><span data-stu-id="a9e93-119">Description</span></span>|  
|----------------|---------------|-----------------|  
|`TypeLoadStartID`|`win:UInt32`|<span data-ttu-id="a9e93-120">유형 로드 작업의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a9e93-120">ID for the type load operation.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="a9e93-121">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a9e93-121">Unique ID for the instance of CLR or CoreCLR.</span></span>|  

## <a name="typeloadstop-event"></a><span data-ttu-id="a9e93-122">TypeLoadStop 이벤트</span><span class="sxs-lookup"><span data-stu-id="a9e93-122">TypeLoadStop Event</span></span>

|<span data-ttu-id="a9e93-123">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="a9e93-123">Keyword for raising the event</span></span>|<span data-ttu-id="a9e93-124">수준</span><span class="sxs-lookup"><span data-stu-id="a9e93-124">Level</span></span>|  
|-----------------------------------|-----------|-----------|  
|<span data-ttu-id="a9e93-125">`TypeDiagnosticKeyword` (0x8000000000)</span><span class="sxs-lookup"><span data-stu-id="a9e93-125">`TypeDiagnosticKeyword` (0x8000000000)</span></span>|<span data-ttu-id="a9e93-126">정보(4)</span><span class="sxs-lookup"><span data-stu-id="a9e93-126">Informational (4)</span></span>|  

|<span data-ttu-id="a9e93-127">이벤트</span><span class="sxs-lookup"><span data-stu-id="a9e93-127">Event</span></span>|<span data-ttu-id="a9e93-128">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="a9e93-128">Event ID</span></span>|<span data-ttu-id="a9e93-129">Description</span><span class="sxs-lookup"><span data-stu-id="a9e93-129">Description</span></span>|  
|-----------|--------------|-----------------|  
|`TypeLoadStop`|<span data-ttu-id="a9e93-130">74</span><span class="sxs-lookup"><span data-stu-id="a9e93-130">74</span></span>|<span data-ttu-id="a9e93-131">유형 로드가 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a9e93-131">A type load is finished.</span></span>|

|<span data-ttu-id="a9e93-132">필드 이름</span><span class="sxs-lookup"><span data-stu-id="a9e93-132">Field name</span></span>|<span data-ttu-id="a9e93-133">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a9e93-133">Data type</span></span>|<span data-ttu-id="a9e93-134">Description</span><span class="sxs-lookup"><span data-stu-id="a9e93-134">Description</span></span>|  
|----------------|---------------|-----------------|  
|`TypeLoadStartID`|`win:UInt32`|<span data-ttu-id="a9e93-135">유형 로드 작업의 ID입니다. 해당 TypeLoadStart 이벤트의 TypeLoadStartID와 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e93-135">ID for the type load operation (matches the corresponding TypeLoadStart event's TypeLoadStartID).</span></span>|
|`LoadLevel`|`win:UInt16`|<span data-ttu-id="a9e93-136">로드 수준을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e93-136">Type load level.</span></span>|
|`TypeID`|`win:UInt64`|<span data-ttu-id="a9e93-137">형식 핸들에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a9e93-137">Pointer to the type handle.</span></span>|
|`TypeName`|`win:UnicodeString`|<span data-ttu-id="a9e93-138">형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a9e93-138">Name of the type.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="a9e93-139">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a9e93-139">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
