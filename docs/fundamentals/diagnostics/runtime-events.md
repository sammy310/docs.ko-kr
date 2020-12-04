---
title: 런타임 이벤트
description: ETW, LTTng 또는 EventPipe에서 사용할 수 있는 .NET runtime (CoreCLR)에서 내보낸 진단 이벤트를 검토 합니다.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- runtime events (CoreCLR)
- ETW, EventPipe runtime events (CoreCLR)
ms.openlocfilehash: 33fa7275ce40934ce043b4d0dba5749c37515755
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "96594051"
---
# <a name="net-runtime-events"></a><span data-ttu-id="da870-103">.NET 런타임 이벤트</span><span class="sxs-lookup"><span data-stu-id="da870-103">.NET runtime events</span></span>

<span data-ttu-id="da870-104">CoreCLR (.NET 런타임)은, 및와 같은 다양 한 메커니즘을 통해 사용 될 수 있는 .NET 응용 프로그램의 문제를 진단 하는 데 사용할 수 있는 다양 한 이벤트를 내보냅니다 `ETW` `LTTng` `EventPipe` .</span><span class="sxs-lookup"><span data-stu-id="da870-104">The .NET runtime (CoreCLR) emits various events that can be used to diagnose issues with your .NET application that can be consumed via various mechanisms such as `ETW`, `LTTng`, and `EventPipe`.</span></span>

<span data-ttu-id="da870-105">이 문서는 .NET Core 런타임에서 발생 하는 이벤트에 대 한 참조로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da870-105">This document serves as a reference on the events that are fired by .NET Core runtime.</span></span>

<span data-ttu-id="da870-106">.NET Framework의 런타임 이벤트는 [CLR ETW 이벤트](../../framework/performance/clr-etw-events.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da870-106">For runtime events in .NET Framework, see [CLR ETW Events](../../framework/performance/clr-etw-events.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="da870-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="da870-107">In this section</span></span>

<span data-ttu-id="da870-108">[경합 이벤트](runtime-contention-events.md)</span><span class="sxs-lookup"><span data-stu-id="da870-108">[Contention Events](runtime-contention-events.md)</span></span>\
<span data-ttu-id="da870-109">이러한 이벤트는 모니터 잠금 경합에 대 한 정보를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="da870-109">These events collect information about monitor lock contentions.</span></span>

<span data-ttu-id="da870-110">[가비지 수집 이벤트](runtime-garbage-collection-events.md)</span><span class="sxs-lookup"><span data-stu-id="da870-110">[Garbage Collection Events](runtime-garbage-collection-events.md)</span></span>\
<span data-ttu-id="da870-111">이들 이벤트는 가비지 수집과 관련된 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="da870-111">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="da870-112">가비지 수집 수행 횟수, 가비지 수집 중에 해제 된 메모리 양 등을 확인 하는 등 진단 및 디버깅에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da870-112">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, etc.</span></span>

<span data-ttu-id="da870-113">[예외 이벤트](runtime-exception-events.md)</span><span class="sxs-lookup"><span data-stu-id="da870-113">[Exception Events](runtime-exception-events.md)</span></span>\
<span data-ttu-id="da870-114">이러한 런타임 이벤트는 throw 되는 예외에 대 한 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="da870-114">These runtime events capture information about exceptions that are thrown.</span></span>

<span data-ttu-id="da870-115">[Interop 이벤트](runtime-interop-events.md)</span><span class="sxs-lookup"><span data-stu-id="da870-115">[Interop Events](runtime-interop-events.md)</span></span>\
<span data-ttu-id="da870-116">이러한 런타임 이벤트는 CIL (공용 중간 언어) 스텁 생성에 대 한 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="da870-116">These runtime events capture information about Common Intermediate Language (CIL) stub generation.</span></span>

<span data-ttu-id="da870-117">[로더 및 바인더 이벤트](runtime-loader-binder-events.md)</span><span class="sxs-lookup"><span data-stu-id="da870-117">[Loader and Binder Events](runtime-loader-binder-events.md)</span></span>\
<span data-ttu-id="da870-118">이러한 이벤트는 어셈블리 및 모듈 로드 및 언로드와 관련 된 정보를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="da870-118">These events collect information relating to loading and unloading assemblies and modules.</span></span>

<span data-ttu-id="da870-119">[메서드 이벤트](runtime-method-events.md)</span><span class="sxs-lookup"><span data-stu-id="da870-119">[Method Events](runtime-method-events.md)</span></span>\
<span data-ttu-id="da870-120">이들 이벤트는 메서드와 관련된 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="da870-120">These events collect information that is specific to methods.</span></span> <span data-ttu-id="da870-121">이들 이벤트의 페이로드는 기호 확인을 위해 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="da870-121">The payload of these events is required for symbol resolution.</span></span> <span data-ttu-id="da870-122">또한 이들 이벤트는 메서드를 호출한 횟수와 같은 유용한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="da870-122">In addition, these events provide helpful information such as the number of times a method was called.</span></span>

<span data-ttu-id="da870-123">[스레드 이벤트](runtime-thread-events.md)</span><span class="sxs-lookup"><span data-stu-id="da870-123">[Thread Events](runtime-thread-events.md)</span></span>\
<span data-ttu-id="da870-124">이러한 이벤트는 작업자 스레드 및 I/O 스레드에 대한 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="da870-124">These events collect information about worker and I/O threads.</span></span>

<span data-ttu-id="da870-125">[유형 이벤트](runtime-type-events.md)</span><span class="sxs-lookup"><span data-stu-id="da870-125">[Type Events](runtime-type-events.md)</span></span>\
<span data-ttu-id="da870-126">이러한 이벤트는 형식 시스템에 대 한 정보를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="da870-126">These events collect information about the type system.</span></span>
