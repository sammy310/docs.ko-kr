---
title: 메서드 런타임 이벤트
description: CLR 메서드 이벤트, CLR 메서드 표식 또는 CLR 메서드 자세한 이벤트, MethodJittingStarted와 같은 메서드와 관련 된 진단 정보를 수집 하는 .NET 런타임 이벤트를 참조 하세요.
ms.date: 11/13/2020
helpviewer_keywords:
- Method events (CoreCLR)
- ETW, EventPipe, LTTng method events (CoreCLR)
ms.openlocfilehash: f9d08efa420670cf7a8c863f115ff270998f2dca
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "96594040"
---
# <a name="net-runtime-method-events"></a><span data-ttu-id="51393-103">.NET 런타임 메서드 이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-103">.NET runtime method events</span></span>

<span data-ttu-id="51393-104">이들 이벤트는 메서드와 관련된 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="51393-104">These events collect information that is specific to methods.</span></span> <span data-ttu-id="51393-105">이들 이벤트의 페이로드는 기호 확인을 위해 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="51393-105">The payload of these events is required for symbol resolution.</span></span> <span data-ttu-id="51393-106">또한 이러한 이벤트는 로드 되 고 언로드된 메서드와 같은 유용한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="51393-106">In addition, these events provide helpful information such as methods that are loaded and unloaded.</span></span> <span data-ttu-id="51393-107">진단 목적으로 이러한 이벤트를 사용 하는 방법에 대 한 자세한 내용은 [.net 응용 프로그램 로깅 및 추적](../../core/diagnostics/logging-tracing.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="51393-107">For more information about how to use these events for diagnostic purposes, see [logging and tracing .NET applications](../../core/diagnostics/logging-tracing.md)</span></span>

<span data-ttu-id="51393-108">모든 메서드 이벤트에는 "정보 제공(4)" 수준이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51393-108">All method events have a level of "Informational (4)".</span></span> <span data-ttu-id="51393-109">모든 메서드 자세한 정보 표시 이벤트에는 "자세한 정보 표시(5)" 수준이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51393-109">All method verbose events have a level of "Verbose (5)".</span></span>

<span data-ttu-id="51393-110">모든 메서드 이벤트는 런타임 공급자에서 `JITKeyword` (0x10) 키워드 또는 `NGenKeyword` (0x20) 키워드에 의해 발생하거나 런다운 공급자에서 `JitRundownKeyword` (0x10) 또는 `NGENRundownKeyword` (0x20)에 의해 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="51393-110">All method events are raised by the `JITKeyword` (0x10) keyword or the `NGenKeyword` (0x20) keyword under the runtime provider, or `JitRundownKeyword` (0x10) or `NGENRundownKeyword` (0x20) under the rundown provider.</span></span>

<span data-ttu-id="51393-111">이러한 이벤트의 V2 버전에는 ReJITID가 포함 되며, V1 버전은 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51393-111">The V2 versions of these events include the ReJITID, the V1 versions do not.</span></span>

## <a name="methodload_v1-event"></a><span data-ttu-id="51393-112">MethodLoad_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-112">MethodLoad_V1 event</span></span>

<span data-ttu-id="51393-113">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="51393-113">The following table shows the event information:</span></span>

|<span data-ttu-id="51393-114">이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-114">Event</span></span>|<span data-ttu-id="51393-115">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="51393-115">Event ID</span></span>|<span data-ttu-id="51393-116">Description</span><span class="sxs-lookup"><span data-stu-id="51393-116">Description</span></span>|
|-----------|--------------|-----------------|
|`MethodLoad_V1`|<span data-ttu-id="51393-117">141</span><span class="sxs-lookup"><span data-stu-id="51393-117">141</span></span>|<span data-ttu-id="51393-118">메서드가 JIT(Just-In-Time) 로드되거나 NGEN 이미지가 로드될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="51393-118">Raised when a method is just-in-time loaded (JIT-loaded) or an NGEN image is loaded.</span></span> <span data-ttu-id="51393-119">동적 및 제네릭 메서드는 메서드 로드에 대해 이 버전을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51393-119">Dynamic and generic methods do not use this version for method loads.</span></span> <span data-ttu-id="51393-120">JIT 도우미는 이 버전을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51393-120">JIT helpers never use this version.</span></span>|

|<span data-ttu-id="51393-121">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="51393-121">Keyword for raising the event</span></span>|<span data-ttu-id="51393-122">수준</span><span class="sxs-lookup"><span data-stu-id="51393-122">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="51393-123">`JITKeyword` (0x10) 런타임 공급자</span><span class="sxs-lookup"><span data-stu-id="51393-123">`JITKeyword` (0x10) runtime provider</span></span>|<span data-ttu-id="51393-124">정보(4)</span><span class="sxs-lookup"><span data-stu-id="51393-124">Informational (4)</span></span>|
|<span data-ttu-id="51393-125">`NGenKeyword` (0x20) 런타임 공급자</span><span class="sxs-lookup"><span data-stu-id="51393-125">`NGenKeyword` (0x20) runtime provider</span></span>|<span data-ttu-id="51393-126">정보(4)</span><span class="sxs-lookup"><span data-stu-id="51393-126">Informational (4)</span></span>|

|<span data-ttu-id="51393-127">필드 이름</span><span class="sxs-lookup"><span data-stu-id="51393-127">Field name</span></span>|<span data-ttu-id="51393-128">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51393-128">Data type</span></span>|<span data-ttu-id="51393-129">Description</span><span class="sxs-lookup"><span data-stu-id="51393-129">Description</span></span>|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|<span data-ttu-id="51393-130">메서드의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-130">Unique identifier of a method.</span></span> <span data-ttu-id="51393-131">JIT 도우미 메서드에 대한 이 필드는 메서드의 시작 주소로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="51393-131">For JIT helper methods, this is set to the start address of the method.</span></span>|
|`ModuleID`|`win:UInt64`|<span data-ttu-id="51393-132">이 메서드가 속한 모듈의 식별자입니다(JIT 도우미의 경우 0).</span><span class="sxs-lookup"><span data-stu-id="51393-132">Identifier of the module to which this method belongs (0 for JIT helpers).</span></span>|
|`MethodStartAddress`|`win:UInt64`|<span data-ttu-id="51393-133">메서드의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-133">Start address of the method.</span></span>|
|`MethodSize`|`win:UInt32`|<span data-ttu-id="51393-134">메서드의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-134">Size of the method.</span></span>|
|`MethodToken`|`win:UInt32`|<span data-ttu-id="51393-135">동적 메서드 및 JIT 도우미의 경우 0입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-135">0 for dynamic methods and JIT helpers.</span></span>|
|`MethodFlags`|`win:UInt32`|<span data-ttu-id="51393-136">0x1: 동적 메서드.</span><span class="sxs-lookup"><span data-stu-id="51393-136">0x1: Dynamic method.</span></span><br /><br /> <span data-ttu-id="51393-137">0x2: 제네릭 메서드.</span><span class="sxs-lookup"><span data-stu-id="51393-137">0x2: Generic method.</span></span><br /><br /> <span data-ttu-id="51393-138">0x4: JIT 컴파일된 코드 메서드(이외의 경우 NGEN 네이티브 이미지 코드).</span><span class="sxs-lookup"><span data-stu-id="51393-138">0x4: JIT-compiled code method (otherwise NGEN native image code).</span></span><br /><br /> <span data-ttu-id="51393-139">0x8: 도우미 메서드.</span><span class="sxs-lookup"><span data-stu-id="51393-139">0x8: Helper method.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="51393-140">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-140">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="methodload_v2-event"></a><span data-ttu-id="51393-141">MethodLoad_V2 이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-141">MethodLoad_V2 event</span></span>

|<span data-ttu-id="51393-142">이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-142">Event</span></span>|<span data-ttu-id="51393-143">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="51393-143">Event ID</span></span>|<span data-ttu-id="51393-144">Description</span><span class="sxs-lookup"><span data-stu-id="51393-144">Description</span></span>|
|----------------|---------------|-----------------|
|`MethodLoad_V2`|<span data-ttu-id="51393-145">141</span><span class="sxs-lookup"><span data-stu-id="51393-145">141</span></span>|<span data-ttu-id="51393-146">메서드가 JIT(Just-In-Time) 로드되거나 NGEN 이미지가 로드될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="51393-146">Raised when a method is just-in-time loaded (JIT-loaded) or an NGEN image is loaded.</span></span> <span data-ttu-id="51393-147">동적 및 제네릭 메서드는 메서드 로드에 대해 이 버전을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51393-147">Dynamic and generic methods do not use this version for method loads.</span></span> <span data-ttu-id="51393-148">JIT 도우미는 이 버전을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51393-148">JIT helpers never use this version.</span></span>|

|<span data-ttu-id="51393-149">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="51393-149">Keyword for raising the event</span></span>|<span data-ttu-id="51393-150">수준</span><span class="sxs-lookup"><span data-stu-id="51393-150">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="51393-151">`JITKeyword` (0x10) 런타임 공급자</span><span class="sxs-lookup"><span data-stu-id="51393-151">`JITKeyword` (0x10) runtime provider</span></span>|<span data-ttu-id="51393-152">정보(4)</span><span class="sxs-lookup"><span data-stu-id="51393-152">Informational (4)</span></span>|
|<span data-ttu-id="51393-153">`NGenKeyword` (0x20) 런타임 공급자</span><span class="sxs-lookup"><span data-stu-id="51393-153">`NGenKeyword` (0x20) runtime provider</span></span>|<span data-ttu-id="51393-154">정보(4)</span><span class="sxs-lookup"><span data-stu-id="51393-154">Informational (4)</span></span>|

|<span data-ttu-id="51393-155">필드 이름</span><span class="sxs-lookup"><span data-stu-id="51393-155">Field name</span></span>|<span data-ttu-id="51393-156">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51393-156">Data type</span></span>|<span data-ttu-id="51393-157">Description</span><span class="sxs-lookup"><span data-stu-id="51393-157">Description</span></span>|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|<span data-ttu-id="51393-158">메서드의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-158">Unique identifier of a method.</span></span> <span data-ttu-id="51393-159">JIT 도우미 메서드에 대한 이 필드는 메서드의 시작 주소로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="51393-159">For JIT helper methods, this is set to the start address of the method.</span></span>|
|`ModuleID`|`win:UInt64`|<span data-ttu-id="51393-160">이 메서드가 속한 모듈의 식별자입니다(JIT 도우미의 경우 0).</span><span class="sxs-lookup"><span data-stu-id="51393-160">Identifier of the module to which this method belongs (0 for JIT helpers).</span></span>|
|`MethodStartAddress`|`win:UInt64`|<span data-ttu-id="51393-161">메서드의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-161">Start address of the method.</span></span>|
|`MethodSize`|`win:UInt32`|<span data-ttu-id="51393-162">메서드의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-162">Size of the method.</span></span>|
|`MethodToken`|`win:UInt32`|<span data-ttu-id="51393-163">동적 메서드 및 JIT 도우미의 경우 0입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-163">0 for dynamic methods and JIT helpers.</span></span>|
|`MethodFlags`|`win:UInt32`|<span data-ttu-id="51393-164">0x1: 동적 메서드.</span><span class="sxs-lookup"><span data-stu-id="51393-164">0x1: Dynamic method.</span></span><br /><br /> <span data-ttu-id="51393-165">0x2: 제네릭 메서드.</span><span class="sxs-lookup"><span data-stu-id="51393-165">0x2: Generic method.</span></span><br /><br /> <span data-ttu-id="51393-166">0x4: JIT 컴파일된 코드 메서드(이외의 경우 NGEN 네이티브 이미지 코드).</span><span class="sxs-lookup"><span data-stu-id="51393-166">0x4: JIT-compiled code method (otherwise NGEN native image code).</span></span><br /><br /> <span data-ttu-id="51393-167">0x8: 도우미 메서드.</span><span class="sxs-lookup"><span data-stu-id="51393-167">0x8: Helper method.</span></span>|
|`ReJITID`|`win:UInt64`|<span data-ttu-id="51393-168">메서드의 ReJIT ID입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-168">ReJIT ID of the method.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="51393-169">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-169">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="methodunload_v1-event"></a><span data-ttu-id="51393-170">MethodUnLoad_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-170">MethodUnLoad_V1 event</span></span>

|<span data-ttu-id="51393-171">이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-171">Event</span></span>|<span data-ttu-id="51393-172">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="51393-172">Event ID</span></span>|<span data-ttu-id="51393-173">Description</span><span class="sxs-lookup"><span data-stu-id="51393-173">Description</span></span>|
|----------------|---------------|-----------------|
|`MethodUnLoad_V1`|<span data-ttu-id="51393-174">142</span><span class="sxs-lookup"><span data-stu-id="51393-174">142</span></span>|<span data-ttu-id="51393-175">모듈이 언로드되거나 애플리케이션 도메인이 삭제될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="51393-175">Raised when a module is unloaded, or an application domain is destroyed.</span></span> <span data-ttu-id="51393-176">동적 메서드는 메서드 언로드에 대해 이 버전을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51393-176">Dynamic methods never use this version for method unloads.</span></span>|

|<span data-ttu-id="51393-177">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="51393-177">Keyword for raising the event</span></span>|<span data-ttu-id="51393-178">수준</span><span class="sxs-lookup"><span data-stu-id="51393-178">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="51393-179">`JITKeyword` (0x10)</span><span class="sxs-lookup"><span data-stu-id="51393-179">`JITKeyword` (0x10)</span></span>|<span data-ttu-id="51393-180">정보(4)</span><span class="sxs-lookup"><span data-stu-id="51393-180">Informational (4)</span></span>|
|<span data-ttu-id="51393-181">`NGenKeyword` 0x20</span><span class="sxs-lookup"><span data-stu-id="51393-181">`NGenKeyword` (0x20)</span></span>|<span data-ttu-id="51393-182">정보(4)</span><span class="sxs-lookup"><span data-stu-id="51393-182">Informational (4)</span></span>|

|<span data-ttu-id="51393-183">필드 이름</span><span class="sxs-lookup"><span data-stu-id="51393-183">Field name</span></span>|<span data-ttu-id="51393-184">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51393-184">Data type</span></span>|<span data-ttu-id="51393-185">Description</span><span class="sxs-lookup"><span data-stu-id="51393-185">Description</span></span>|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|<span data-ttu-id="51393-186">메서드의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-186">Unique identifier of a method.</span></span> <span data-ttu-id="51393-187">JIT 도우미 메서드에 대한 이 필드는 메서드의 시작 주소로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="51393-187">For JIT helper methods, this is set to the start address of the method.</span></span>|
|`ModuleID`|`win:UInt64`|<span data-ttu-id="51393-188">이 메서드가 속한 모듈의 식별자입니다(JIT 도우미의 경우 0).</span><span class="sxs-lookup"><span data-stu-id="51393-188">Identifier of the module to which this method belongs (0 for JIT helpers).</span></span>|
|`MethodStartAddress`|`win:UInt64`|<span data-ttu-id="51393-189">메서드의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-189">Start address of the method.</span></span>|
|`MethodSize`|`win:UInt32`|<span data-ttu-id="51393-190">메서드의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-190">Size of the method.</span></span>|
|`MethodToken`|`win:UInt32`|<span data-ttu-id="51393-191">동적 메서드 및 JIT 도우미의 경우 0입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-191">0 for dynamic methods and JIT helpers.</span></span>|
|`MethodFlags`|`win:UInt32`|<span data-ttu-id="51393-192">0x1: 동적 메서드.</span><span class="sxs-lookup"><span data-stu-id="51393-192">0x1: Dynamic method.</span></span><br /><br /> <span data-ttu-id="51393-193">0x2: 제네릭 메서드.</span><span class="sxs-lookup"><span data-stu-id="51393-193">0x2: Generic method.</span></span><br /><br /> <span data-ttu-id="51393-194">0x4: JIT 컴파일된 코드 메서드(이외의 경우 NGEN 네이티브 이미지 코드).</span><span class="sxs-lookup"><span data-stu-id="51393-194">0x4: JIT-compiled code method (otherwise NGEN native image code).</span></span><br /><br /> <span data-ttu-id="51393-195">0x8: 도우미 메서드.</span><span class="sxs-lookup"><span data-stu-id="51393-195">0x8: Helper method.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="51393-196">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-196">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="methodunload_v2-event"></a><span data-ttu-id="51393-197">MethodUnLoad_V2 이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-197">MethodUnLoad_V2 event</span></span>

|<span data-ttu-id="51393-198">이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-198">Event</span></span>|<span data-ttu-id="51393-199">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="51393-199">Event ID</span></span>|<span data-ttu-id="51393-200">Description</span><span class="sxs-lookup"><span data-stu-id="51393-200">Description</span></span>|
|----------------|---------------|-----------------|
|`MethodUnLoad_V2`|<span data-ttu-id="51393-201">142</span><span class="sxs-lookup"><span data-stu-id="51393-201">142</span></span>|<span data-ttu-id="51393-202">모듈이 언로드되거나 애플리케이션 도메인이 삭제될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="51393-202">Raised when a module is unloaded, or an application domain is destroyed.</span></span> <span data-ttu-id="51393-203">동적 메서드는 메서드 언로드에 대해 이 버전을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51393-203">Dynamic methods never use this version for method unloads.</span></span>|

|<span data-ttu-id="51393-204">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="51393-204">Keyword for raising the event</span></span>|<span data-ttu-id="51393-205">수준</span><span class="sxs-lookup"><span data-stu-id="51393-205">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="51393-206">`JITKeyword` (0x10)</span><span class="sxs-lookup"><span data-stu-id="51393-206">`JITKeyword` (0x10)</span></span>|<span data-ttu-id="51393-207">정보(4)</span><span class="sxs-lookup"><span data-stu-id="51393-207">Informational (4)</span></span>|
|<span data-ttu-id="51393-208">`NGenKeyword` 0x20</span><span class="sxs-lookup"><span data-stu-id="51393-208">`NGenKeyword` (0x20)</span></span>|<span data-ttu-id="51393-209">정보(4)</span><span class="sxs-lookup"><span data-stu-id="51393-209">Informational (4)</span></span>|

|<span data-ttu-id="51393-210">필드 이름</span><span class="sxs-lookup"><span data-stu-id="51393-210">Field name</span></span>|<span data-ttu-id="51393-211">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51393-211">Data type</span></span>|<span data-ttu-id="51393-212">Description</span><span class="sxs-lookup"><span data-stu-id="51393-212">Description</span></span>|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|<span data-ttu-id="51393-213">메서드의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-213">Unique identifier of a method.</span></span> <span data-ttu-id="51393-214">JIT 도우미 메서드에 대한 이 필드는 메서드의 시작 주소로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="51393-214">For JIT helper methods, this is set to the start address of the method.</span></span>|
|`ModuleID`|`win:UInt64`|<span data-ttu-id="51393-215">이 메서드가 속한 모듈의 식별자입니다(JIT 도우미의 경우 0).</span><span class="sxs-lookup"><span data-stu-id="51393-215">Identifier of the module to which this method belongs (0 for JIT helpers).</span></span>|
|`MethodStartAddress`|`win:UInt64`|<span data-ttu-id="51393-216">메서드의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-216">Start address of the method.</span></span>|
|`MethodSize`|`win:UInt32`|<span data-ttu-id="51393-217">메서드의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-217">Size of the method.</span></span>|
|`MethodToken`|`win:UInt32`|<span data-ttu-id="51393-218">동적 메서드 및 JIT 도우미의 경우 0입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-218">0 for dynamic methods and JIT helpers.</span></span>|
|`MethodFlags`|`win:UInt32`|<span data-ttu-id="51393-219">0x1: 동적 메서드.</span><span class="sxs-lookup"><span data-stu-id="51393-219">0x1: Dynamic method.</span></span><br /><br /> <span data-ttu-id="51393-220">0x2: 제네릭 메서드.</span><span class="sxs-lookup"><span data-stu-id="51393-220">0x2: Generic method.</span></span><br /><br /> <span data-ttu-id="51393-221">0x4: JIT 컴파일된 코드 메서드(이외의 경우 NGEN 네이티브 이미지 코드).</span><span class="sxs-lookup"><span data-stu-id="51393-221">0x4: JIT-compiled code method (otherwise NGEN native image code).</span></span><br /><br /> <span data-ttu-id="51393-222">0x8: 도우미 메서드.</span><span class="sxs-lookup"><span data-stu-id="51393-222">0x8: Helper method.</span></span>|
|`ReJITID`|`win:UInt64`|<span data-ttu-id="51393-223">메서드의 ReJIT ID입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-223">ReJIT ID of the method.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="51393-224">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-224">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="r2rgetentrypoint-event"></a><span data-ttu-id="51393-225">R2RGetEntryPoint 이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-225">R2RGetEntryPoint event</span></span>

|<span data-ttu-id="51393-226">이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-226">Event</span></span>|<span data-ttu-id="51393-227">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="51393-227">Event ID</span></span>|<span data-ttu-id="51393-228">Description</span><span class="sxs-lookup"><span data-stu-id="51393-228">Description</span></span>|
|----------------|---------------|-----------------|
|`R2RGetEntryPoint`|<span data-ttu-id="51393-229">159</span><span class="sxs-lookup"><span data-stu-id="51393-229">159</span></span>|<span data-ttu-id="51393-230">R2R entry point 조회가 종료 될 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="51393-230">Raised when an R2R entry point lookup ends.</span></span>|

|<span data-ttu-id="51393-231">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="51393-231">Keyword for raising the event</span></span>|<span data-ttu-id="51393-232">수준</span><span class="sxs-lookup"><span data-stu-id="51393-232">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="51393-233">`JITKeyword` (0x10)</span><span class="sxs-lookup"><span data-stu-id="51393-233">`JITKeyword` (0x10)</span></span> |<span data-ttu-id="51393-234">정보(4)</span><span class="sxs-lookup"><span data-stu-id="51393-234">Informational (4)</span></span>|
|<span data-ttu-id="51393-235">`NGenKeyword` 0x20</span><span class="sxs-lookup"><span data-stu-id="51393-235">`NGenKeyword` (0x20)</span></span> |<span data-ttu-id="51393-236">정보(4)</span><span class="sxs-lookup"><span data-stu-id="51393-236">Informational (4)</span></span>|

|<span data-ttu-id="51393-237">필드 이름</span><span class="sxs-lookup"><span data-stu-id="51393-237">Field name</span></span>|<span data-ttu-id="51393-238">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51393-238">Data type</span></span>|<span data-ttu-id="51393-239">Description</span><span class="sxs-lookup"><span data-stu-id="51393-239">Description</span></span>|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|<span data-ttu-id="51393-240">R2R 메서드의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-240">Unique identifier of a R2R method.</span></span>|
|`MethodNamespace`|`win:UnicodeString`|<span data-ttu-id="51393-241">조회 되는 메서드의 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-241">The namespace of method being looked up.</span></span>|
|`MethodName`|`win:UnicodeString`|<span data-ttu-id="51393-242">조회 되는 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-242">The name of the method being looked up.</span></span>|
|`MethodSignature`|`win:UnicodeString`|<span data-ttu-id="51393-243">메서드의 서명입니다(쉼표로 구분된 형식 이름 목록).</span><span class="sxs-lookup"><span data-stu-id="51393-243">Signature of the method (comma-separated list of type names).</span></span>|
|`EntryPoint`|`win:UInt64`|<span data-ttu-id="51393-244">R2R 메서드의 진입점에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-244">The pointer to the entry point of the R2R method</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="51393-245">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-245">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="r2rgetentrypointstart-event"></a><span data-ttu-id="51393-246">R2RGetEntryPointStart 이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-246">R2RGetEntryPointStart event</span></span>

|<span data-ttu-id="51393-247">이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-247">Event</span></span>|<span data-ttu-id="51393-248">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="51393-248">Event ID</span></span>|<span data-ttu-id="51393-249">Description</span><span class="sxs-lookup"><span data-stu-id="51393-249">Description</span></span>|
|----------------|---------------|-----------------|
|`R2RGetEntryPointStart`|<span data-ttu-id="51393-250">160</span><span class="sxs-lookup"><span data-stu-id="51393-250">160</span></span>|<span data-ttu-id="51393-251">R2R 진입점 조회가 시작 될 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="51393-251">Raised when an R2R entry point lookup starts.</span></span>|

|<span data-ttu-id="51393-252">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="51393-252">Keyword for raising the event</span></span>|<span data-ttu-id="51393-253">수준</span><span class="sxs-lookup"><span data-stu-id="51393-253">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="51393-254">`JITKeyword` (0x10)</span><span class="sxs-lookup"><span data-stu-id="51393-254">`JITKeyword` (0x10)</span></span> |<span data-ttu-id="51393-255">정보(4)</span><span class="sxs-lookup"><span data-stu-id="51393-255">Informational (4)</span></span>|
|<span data-ttu-id="51393-256">`NGenKeyword` 0x20</span><span class="sxs-lookup"><span data-stu-id="51393-256">`NGenKeyword` (0x20)</span></span> |<span data-ttu-id="51393-257">정보(4)</span><span class="sxs-lookup"><span data-stu-id="51393-257">Informational (4)</span></span>|

|<span data-ttu-id="51393-258">필드 이름</span><span class="sxs-lookup"><span data-stu-id="51393-258">Field name</span></span>|<span data-ttu-id="51393-259">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51393-259">Data type</span></span>|<span data-ttu-id="51393-260">Description</span><span class="sxs-lookup"><span data-stu-id="51393-260">Description</span></span>|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|<span data-ttu-id="51393-261">R2R 메서드의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-261">Unique identifier of a R2R method.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="51393-262">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-262">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="methodloadverbose_v1-event"></a><span data-ttu-id="51393-263">MethodLoadVerbose_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-263">MethodLoadVerbose_V1 event</span></span>

|<span data-ttu-id="51393-264">이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-264">Event</span></span>|<span data-ttu-id="51393-265">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="51393-265">Event ID</span></span>|<span data-ttu-id="51393-266">Description</span><span class="sxs-lookup"><span data-stu-id="51393-266">Description</span></span>|
|-----------|--------------|-----------------|
|`MethodLoadVerbose_V1`|<span data-ttu-id="51393-267">143</span><span class="sxs-lookup"><span data-stu-id="51393-267">143</span></span>|<span data-ttu-id="51393-268">메서드가 JIT 로드되거나 NGEN 이미지가 로드될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="51393-268">Raised when a method is JIT-loaded or an NGEN image is loaded.</span></span> <span data-ttu-id="51393-269">동적 및 제네릭 메서드는 항상 메서드 로드에 대해 이 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="51393-269">Dynamic and generic methods always use this version for method loads.</span></span> <span data-ttu-id="51393-270">JIT 도우미는 항상 이 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="51393-270">JIT helpers always use this version.</span></span>|

|<span data-ttu-id="51393-271">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="51393-271">Keyword for raising the event</span></span>|<span data-ttu-id="51393-272">수준</span><span class="sxs-lookup"><span data-stu-id="51393-272">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="51393-273">`JITKeyword` (0x10)</span><span class="sxs-lookup"><span data-stu-id="51393-273">`JITKeyword` (0x10)</span></span> |<span data-ttu-id="51393-274">정보(4)</span><span class="sxs-lookup"><span data-stu-id="51393-274">Informational (4)</span></span>|
|<span data-ttu-id="51393-275">`NGenKeyword` 0x20</span><span class="sxs-lookup"><span data-stu-id="51393-275">`NGenKeyword` (0x20)</span></span> |<span data-ttu-id="51393-276">정보(4)</span><span class="sxs-lookup"><span data-stu-id="51393-276">Informational (4)</span></span>|

|<span data-ttu-id="51393-277">필드 이름</span><span class="sxs-lookup"><span data-stu-id="51393-277">Field name</span></span>|<span data-ttu-id="51393-278">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51393-278">Data type</span></span>|<span data-ttu-id="51393-279">Description</span><span class="sxs-lookup"><span data-stu-id="51393-279">Description</span></span>|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|<span data-ttu-id="51393-280">메서드의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-280">Unique identifier of the method.</span></span> <span data-ttu-id="51393-281">JIT 도우미 메서드의 경우 메서드의 시작 주소로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="51393-281">For JIT helper methods, set to the start address of the method.</span></span>|
|`ModuleID`|`win:UInt64`|<span data-ttu-id="51393-282">이 메서드가 속한 모듈의 식별자입니다(JIT 도우미의 경우 0).</span><span class="sxs-lookup"><span data-stu-id="51393-282">Identifier of the module to which this method belongs (0 for JIT helpers).</span></span>|
|`MethodStartAddress`|`win:UInt64`|<span data-ttu-id="51393-283">시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-283">Start address.</span></span>|
|`MethodSize`|`win:UInt32`|<span data-ttu-id="51393-284">메서드 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-284">Method length.</span></span>|
|`MethodToken`|`win:UInt32`|<span data-ttu-id="51393-285">동적 메서드 및 JIT 도우미의 경우 0입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-285">0 for dynamic methods and JIT helpers.</span></span>|
|`MethodFlags`|`win:UInt32`|<span data-ttu-id="51393-286">0x1: 동적 메서드.</span><span class="sxs-lookup"><span data-stu-id="51393-286">0x1: Dynamic method.</span></span><br /><br /> <span data-ttu-id="51393-287">0x2: 제네릭 메서드.</span><span class="sxs-lookup"><span data-stu-id="51393-287">0x2: Generic method.</span></span><br /><br /> <span data-ttu-id="51393-288">0x4: JIT 컴파일된 메서드(이외의 경우 NGen.exe에서 생성됨)</span><span class="sxs-lookup"><span data-stu-id="51393-288">0x4: JIT-compiled method (otherwise, generated by NGen.exe)</span></span><br /><br /> <span data-ttu-id="51393-289">0x8: 도우미 메서드.</span><span class="sxs-lookup"><span data-stu-id="51393-289">0x8: Helper method.</span></span>|
|`MethodNameSpace`|`win:UnicodeString`|<span data-ttu-id="51393-290">메서드와 연결된 전체 네임스페이스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-290">Full namespace name associated with the method.</span></span>|
|`MethodName`|`win:UnicodeString`|<span data-ttu-id="51393-291">메서드와 연결된 전체 클래스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-291">Full class name associated with the method.</span></span>|
|`MethodSignature`|`win:UnicodeString`|<span data-ttu-id="51393-292">메서드의 서명입니다(쉼표로 구분된 형식 이름 목록).</span><span class="sxs-lookup"><span data-stu-id="51393-292">Signature of the method (comma-separated list of type names).</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="51393-293">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-293">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="methodloadverbose_v2-event"></a><span data-ttu-id="51393-294">MethodLoadVerbose_V2 이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-294">MethodLoadVerbose_V2 event</span></span>

|<span data-ttu-id="51393-295">이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-295">Event</span></span>|<span data-ttu-id="51393-296">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="51393-296">Event ID</span></span>|<span data-ttu-id="51393-297">Description</span><span class="sxs-lookup"><span data-stu-id="51393-297">Description</span></span>|
|-----------|--------------|-----------------|
|`MethodLoadVerbose_V1`|<span data-ttu-id="51393-298">143</span><span class="sxs-lookup"><span data-stu-id="51393-298">143</span></span>|<span data-ttu-id="51393-299">메서드가 JIT 로드되거나 NGEN 이미지가 로드될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="51393-299">Raised when a method is JIT-loaded or an NGEN image is loaded.</span></span> <span data-ttu-id="51393-300">동적 및 제네릭 메서드는 항상 메서드 로드에 대해 이 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="51393-300">Dynamic and generic methods always use this version for method loads.</span></span> <span data-ttu-id="51393-301">JIT 도우미는 항상 이 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="51393-301">JIT helpers always use this version.</span></span>|

|<span data-ttu-id="51393-302">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="51393-302">Keyword for raising the event</span></span>|<span data-ttu-id="51393-303">수준</span><span class="sxs-lookup"><span data-stu-id="51393-303">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="51393-304">`JITKeyword` (0x10)</span><span class="sxs-lookup"><span data-stu-id="51393-304">`JITKeyword` (0x10)</span></span> |<span data-ttu-id="51393-305">정보(4)</span><span class="sxs-lookup"><span data-stu-id="51393-305">Informational (4)</span></span>|
|<span data-ttu-id="51393-306">`NGenKeyword` 0x20</span><span class="sxs-lookup"><span data-stu-id="51393-306">`NGenKeyword` (0x20)</span></span> |<span data-ttu-id="51393-307">정보(4)</span><span class="sxs-lookup"><span data-stu-id="51393-307">Informational (4)</span></span>|

|<span data-ttu-id="51393-308">필드 이름</span><span class="sxs-lookup"><span data-stu-id="51393-308">Field name</span></span>|<span data-ttu-id="51393-309">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51393-309">Data type</span></span>|<span data-ttu-id="51393-310">Description</span><span class="sxs-lookup"><span data-stu-id="51393-310">Description</span></span>|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|<span data-ttu-id="51393-311">메서드의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-311">Unique identifier of the method.</span></span> <span data-ttu-id="51393-312">JIT 도우미 메서드의 경우 메서드의 시작 주소로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="51393-312">For JIT helper methods, set to the start address of the method.</span></span>|
|`ModuleID`|`win:UInt64`|<span data-ttu-id="51393-313">이 메서드가 속한 모듈의 식별자입니다(JIT 도우미의 경우 0).</span><span class="sxs-lookup"><span data-stu-id="51393-313">Identifier of the module to which this method belongs (0 for JIT helpers).</span></span>|
|`MethodStartAddress`|`win:UInt64`|<span data-ttu-id="51393-314">시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-314">Start address.</span></span>|
|`MethodSize`|`win:UInt32`|<span data-ttu-id="51393-315">메서드 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-315">Method length.</span></span>|
|`MethodToken`|`win:UInt32`|<span data-ttu-id="51393-316">동적 메서드 및 JIT 도우미의 경우 0입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-316">0 for dynamic methods and JIT helpers.</span></span>|
|`MethodFlags`|`win:UInt32`|<span data-ttu-id="51393-317">0x1: 동적 메서드.</span><span class="sxs-lookup"><span data-stu-id="51393-317">0x1: Dynamic method.</span></span><br /><br /> <span data-ttu-id="51393-318">0x2: 제네릭 메서드.</span><span class="sxs-lookup"><span data-stu-id="51393-318">0x2: Generic method.</span></span><br /><br /> <span data-ttu-id="51393-319">0x4: JIT 컴파일된 메서드(이외의 경우 NGen.exe에서 생성됨)</span><span class="sxs-lookup"><span data-stu-id="51393-319">0x4: JIT-compiled method (otherwise, generated by NGen.exe)</span></span><br /><br /> <span data-ttu-id="51393-320">0x8: 도우미 메서드.</span><span class="sxs-lookup"><span data-stu-id="51393-320">0x8: Helper method.</span></span>|
|`MethodNameSpace`|`win:UnicodeString`|<span data-ttu-id="51393-321">메서드와 연결된 전체 네임스페이스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-321">Full namespace name associated with the method.</span></span>|
|`MethodName`|`win:UnicodeString`|<span data-ttu-id="51393-322">메서드와 연결된 전체 클래스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-322">Full class name associated with the method.</span></span>|
|`MethodSignature`|`win:UnicodeString`|<span data-ttu-id="51393-323">메서드의 서명입니다(쉼표로 구분된 형식 이름 목록).</span><span class="sxs-lookup"><span data-stu-id="51393-323">Signature of the method (comma-separated list of type names).</span></span>|
|`ReJITID`|`win:UInt64`|<span data-ttu-id="51393-324">메서드의 ReJIT ID입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-324">ReJIT ID of the method.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="51393-325">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-325">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="methodunloadverbose_v1-event"></a><span data-ttu-id="51393-326">MethodUnLoadVerbose_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-326">MethodUnLoadVerbose_V1 event</span></span>

|<span data-ttu-id="51393-327">이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-327">Event</span></span>|<span data-ttu-id="51393-328">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="51393-328">Event ID</span></span>|<span data-ttu-id="51393-329">Description</span><span class="sxs-lookup"><span data-stu-id="51393-329">Description</span></span>|
|-----------|--------------|-----------------|
|`MethodUnLoadVerbose_V1`|<span data-ttu-id="51393-330">144</span><span class="sxs-lookup"><span data-stu-id="51393-330">144</span></span>|<span data-ttu-id="51393-331">동적 메서드가 삭제되거나, 모듈이 언로드되거나, 애플리케이션 도메인이 삭제될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="51393-331">Raised when a dynamic method is destroyed, a module is unloaded, or an application domain is destroyed.</span></span> <span data-ttu-id="51393-332">동적 메서드는 항상 메서드 언로드에 대해 이 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="51393-332">Dynamic methods always use this version for method unloads.</span></span>|

|<span data-ttu-id="51393-333">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="51393-333">Keyword for raising the event</span></span>|<span data-ttu-id="51393-334">수준</span><span class="sxs-lookup"><span data-stu-id="51393-334">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="51393-335">`JITKeyword` (0x10)</span><span class="sxs-lookup"><span data-stu-id="51393-335">`JITKeyword` (0x10)</span></span> |<span data-ttu-id="51393-336">정보(4)</span><span class="sxs-lookup"><span data-stu-id="51393-336">Informational (4)</span></span>|
|<span data-ttu-id="51393-337">`NGenKeyword` 0x20</span><span class="sxs-lookup"><span data-stu-id="51393-337">`NGenKeyword` (0x20)</span></span> |<span data-ttu-id="51393-338">정보(4)</span><span class="sxs-lookup"><span data-stu-id="51393-338">Informational (4)</span></span>|

|<span data-ttu-id="51393-339">필드 이름</span><span class="sxs-lookup"><span data-stu-id="51393-339">Field name</span></span>|<span data-ttu-id="51393-340">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51393-340">Data type</span></span>|<span data-ttu-id="51393-341">Description</span><span class="sxs-lookup"><span data-stu-id="51393-341">Description</span></span>|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|<span data-ttu-id="51393-342">메서드의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-342">Unique identifier of the method.</span></span> <span data-ttu-id="51393-343">JIT 도우미 메서드의 경우 메서드의 시작 주소로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="51393-343">For JIT helper methods, set to the start address of the method.</span></span>|
|`ModuleID`|`win:UInt64`|<span data-ttu-id="51393-344">이 메서드가 속한 모듈의 식별자입니다(JIT 도우미의 경우 0).</span><span class="sxs-lookup"><span data-stu-id="51393-344">Identifier of the module to which this method belongs (0 for JIT helpers).</span></span>|
|`MethodStartAddress`|`win:UInt64`|<span data-ttu-id="51393-345">시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-345">Start address.</span></span>|
|`MethodSize`|`win:UInt32`|<span data-ttu-id="51393-346">메서드 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-346">Method length.</span></span>|
|`MethodToken`|`win:UInt32`|<span data-ttu-id="51393-347">동적 메서드 및 JIT 도우미의 경우 0입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-347">0 for dynamic methods and JIT helpers.</span></span>|
|`MethodFlags`|`win:UInt32`|<span data-ttu-id="51393-348">0x1: 동적 메서드.</span><span class="sxs-lookup"><span data-stu-id="51393-348">0x1: Dynamic method.</span></span><br /><br /> <span data-ttu-id="51393-349">0x2: 제네릭 메서드.</span><span class="sxs-lookup"><span data-stu-id="51393-349">0x2: Generic method.</span></span><br /><br /> <span data-ttu-id="51393-350">0x4: JIT 컴파일된 메서드(이외의 경우 NGen.exe에서 생성됨)</span><span class="sxs-lookup"><span data-stu-id="51393-350">0x4: JIT-compiled method (otherwise, generated by NGen.exe)</span></span><br /><br /> <span data-ttu-id="51393-351">0x8: 도우미 메서드.</span><span class="sxs-lookup"><span data-stu-id="51393-351">0x8: Helper method.</span></span>|
|`MethodNameSpace`|`win:UnicodeString`|<span data-ttu-id="51393-352">메서드와 연결된 전체 네임스페이스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-352">Full namespace name associated with the method.</span></span>|
|`MethodName`|`win:UnicodeString`|<span data-ttu-id="51393-353">메서드와 연결된 전체 클래스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-353">Full class name associated with the method.</span></span>|
|`MethodSignature`|`win:UnicodeString`|<span data-ttu-id="51393-354">메서드의 서명입니다(쉼표로 구분된 형식 이름 목록).</span><span class="sxs-lookup"><span data-stu-id="51393-354">Signature of the method (comma-separated list of type names).</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="51393-355">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-355">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="methodunloadverbose_v2-event"></a><span data-ttu-id="51393-356">MethodUnLoadVerbose_V2 이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-356">MethodUnLoadVerbose_V2 event</span></span>

|<span data-ttu-id="51393-357">이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-357">Event</span></span>|<span data-ttu-id="51393-358">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="51393-358">Event ID</span></span>|<span data-ttu-id="51393-359">Description</span><span class="sxs-lookup"><span data-stu-id="51393-359">Description</span></span>|
|-----------|--------------|-----------------|
|`MethodUnLoadVerbose_V2`|<span data-ttu-id="51393-360">144</span><span class="sxs-lookup"><span data-stu-id="51393-360">144</span></span>|<span data-ttu-id="51393-361">동적 메서드가 삭제되거나, 모듈이 언로드되거나, 애플리케이션 도메인이 삭제될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="51393-361">Raised when a dynamic method is destroyed, a module is unloaded, or an application domain is destroyed.</span></span> <span data-ttu-id="51393-362">동적 메서드는 항상 메서드 언로드에 대해 이 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="51393-362">Dynamic methods always use this version for method unloads.</span></span>|

|<span data-ttu-id="51393-363">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="51393-363">Keyword for raising the event</span></span>|<span data-ttu-id="51393-364">수준</span><span class="sxs-lookup"><span data-stu-id="51393-364">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="51393-365">`JITKeyword` (0x10)</span><span class="sxs-lookup"><span data-stu-id="51393-365">`JITKeyword` (0x10)</span></span> |<span data-ttu-id="51393-366">정보(4)</span><span class="sxs-lookup"><span data-stu-id="51393-366">Informational (4)</span></span>|
|<span data-ttu-id="51393-367">`NGenKeyword` 0x20</span><span class="sxs-lookup"><span data-stu-id="51393-367">`NGenKeyword` (0x20)</span></span> |<span data-ttu-id="51393-368">정보(4)</span><span class="sxs-lookup"><span data-stu-id="51393-368">Informational (4)</span></span>|

|<span data-ttu-id="51393-369">필드 이름</span><span class="sxs-lookup"><span data-stu-id="51393-369">Field name</span></span>|<span data-ttu-id="51393-370">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51393-370">Data type</span></span>|<span data-ttu-id="51393-371">Description</span><span class="sxs-lookup"><span data-stu-id="51393-371">Description</span></span>|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|<span data-ttu-id="51393-372">메서드의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-372">Unique identifier of the method.</span></span> <span data-ttu-id="51393-373">JIT 도우미 메서드의 경우 메서드의 시작 주소로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="51393-373">For JIT helper methods, set to the start address of the method.</span></span>|
|`ModuleID`|`win:UInt64`|<span data-ttu-id="51393-374">이 메서드가 속한 모듈의 식별자입니다(JIT 도우미의 경우 0).</span><span class="sxs-lookup"><span data-stu-id="51393-374">Identifier of the module to which this method belongs (0 for JIT helpers).</span></span>|
|`MethodStartAddress`|`win:UInt64`|<span data-ttu-id="51393-375">시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-375">Start address.</span></span>|
|`MethodSize`|`win:UInt32`|<span data-ttu-id="51393-376">메서드 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-376">Method length.</span></span>|
|`MethodToken`|`win:UInt32`|<span data-ttu-id="51393-377">동적 메서드 및 JIT 도우미의 경우 0입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-377">0 for dynamic methods and JIT helpers.</span></span>|
|`MethodFlags`|`win:UInt32`|<span data-ttu-id="51393-378">0x1: 동적 메서드.</span><span class="sxs-lookup"><span data-stu-id="51393-378">0x1: Dynamic method.</span></span><br /><br /> <span data-ttu-id="51393-379">0x2: 제네릭 메서드.</span><span class="sxs-lookup"><span data-stu-id="51393-379">0x2: Generic method.</span></span><br /><br /> <span data-ttu-id="51393-380">0x4: JIT 컴파일된 메서드(이외의 경우 NGen.exe에서 생성됨)</span><span class="sxs-lookup"><span data-stu-id="51393-380">0x4: JIT-compiled method (otherwise, generated by NGen.exe)</span></span><br /><br /> <span data-ttu-id="51393-381">0x8: 도우미 메서드.</span><span class="sxs-lookup"><span data-stu-id="51393-381">0x8: Helper method.</span></span>|
|`MethodNameSpace`|`win:UnicodeString`|<span data-ttu-id="51393-382">메서드와 연결된 전체 네임스페이스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-382">Full namespace name associated with the method.</span></span>|
|`MethodName`|`win:UnicodeString`|<span data-ttu-id="51393-383">메서드와 연결된 전체 클래스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-383">Full class name associated with the method.</span></span>|
|`MethodSignature`|`win:UnicodeString`|<span data-ttu-id="51393-384">메서드의 서명입니다(쉼표로 구분된 형식 이름 목록).</span><span class="sxs-lookup"><span data-stu-id="51393-384">Signature of the method (comma-separated list of type names).</span></span>|
|`ReJITID`|`win:UInt64`|<span data-ttu-id="51393-385">메서드의 ReJIT ID입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-385">ReJIT ID of the method.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="51393-386">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-386">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="methodjittingstarted_v1-event"></a><span data-ttu-id="51393-387">MethodJittingStarted_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-387">MethodJittingStarted_V1 event</span></span>

<span data-ttu-id="51393-388">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="51393-388">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="51393-389">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="51393-389">Keyword for raising the event</span></span>|<span data-ttu-id="51393-390">수준</span><span class="sxs-lookup"><span data-stu-id="51393-390">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="51393-391">`JITKeyword` (0x10)</span><span class="sxs-lookup"><span data-stu-id="51393-391">`JITKeyword` (0x10)</span></span> |<span data-ttu-id="51393-392">자세한 정보 표시(5)</span><span class="sxs-lookup"><span data-stu-id="51393-392">Verbose (5)</span></span>|
|<span data-ttu-id="51393-393">`NGenKeyword` 0x20</span><span class="sxs-lookup"><span data-stu-id="51393-393">`NGenKeyword` (0x20)</span></span> |<span data-ttu-id="51393-394">자세한 정보 표시(5)</span><span class="sxs-lookup"><span data-stu-id="51393-394">Verbose (5)</span></span>|

|<span data-ttu-id="51393-395">이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-395">Event</span></span>|<span data-ttu-id="51393-396">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="51393-396">Event ID</span></span>|<span data-ttu-id="51393-397">Description</span><span class="sxs-lookup"><span data-stu-id="51393-397">Description</span></span>|
|-----------|--------------|-----------------|
|`MethodJittingStarted_V1`|<span data-ttu-id="51393-398">145</span><span class="sxs-lookup"><span data-stu-id="51393-398">145</span></span>|<span data-ttu-id="51393-399">메서드가 JIT로 컴파일되는 동안 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="51393-399">Raised when a method is being JIT-compiled.</span></span>|

|<span data-ttu-id="51393-400">필드 이름</span><span class="sxs-lookup"><span data-stu-id="51393-400">Field name</span></span>|<span data-ttu-id="51393-401">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51393-401">Data type</span></span>|<span data-ttu-id="51393-402">Description</span><span class="sxs-lookup"><span data-stu-id="51393-402">Description</span></span>|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|<span data-ttu-id="51393-403">메서드의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-403">Unique identifier of the method.</span></span>|
|`ModuleID`|`win:UInt64`|<span data-ttu-id="51393-404">이 메서드가 속한 모듈의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-404">Identifier of the module to which this method belongs.</span></span>|
|`MethodToken`|`win:UInt32`|<span data-ttu-id="51393-405">동적 메서드 및 JIT 도우미의 경우 0입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-405">0 for dynamic methods and JIT helpers.</span></span>|
|`MethodILSize`|`win:UInt32`|<span data-ttu-id="51393-406">JIT로 컴파일되는 메서드에 대 한 CIL (공용 중간 언어)의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-406">The size of the Common Intermediate Language (CIL) for the method that is being JIT-compiled.</span></span>|
|`MethodNameSpace`|`win:UnicodeString`|<span data-ttu-id="51393-407">메서드와 연결된 전체 클래스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-407">Full class name associated with the method.</span></span>|
|`MethodName`|`win:UnicodeString`|<span data-ttu-id="51393-408">메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-408">Name of the method.</span></span>|
|`MethodSignature`|`win:UnicodeString`|<span data-ttu-id="51393-409">메서드의 서명입니다(쉼표로 구분된 형식 이름 목록).</span><span class="sxs-lookup"><span data-stu-id="51393-409">Signature of the method (comma-separated list of type names).</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="51393-410">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-410">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="methodjitinliningsucceeded-event"></a><span data-ttu-id="51393-411">MethodJitInliningSucceeded 이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-411">MethodJitInliningSucceeded event</span></span>

|<span data-ttu-id="51393-412">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="51393-412">Keyword for raising the event</span></span>|<span data-ttu-id="51393-413">수준</span><span class="sxs-lookup"><span data-stu-id="51393-413">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="51393-414">`JITTracingKeyword` 0x1000</span><span class="sxs-lookup"><span data-stu-id="51393-414">`JITTracingKeyword` (0x1000)</span></span> |<span data-ttu-id="51393-415">자세한 정보 표시(5)</span><span class="sxs-lookup"><span data-stu-id="51393-415">Verbose (5)</span></span>|

|<span data-ttu-id="51393-416">이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-416">Event</span></span>|<span data-ttu-id="51393-417">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="51393-417">Event ID</span></span>|<span data-ttu-id="51393-418">Description</span><span class="sxs-lookup"><span data-stu-id="51393-418">Description</span></span>|
|-----------|--------------|-----------------|
|`MethodJitInliningSucceeded`|<span data-ttu-id="51393-419">185</span><span class="sxs-lookup"><span data-stu-id="51393-419">185</span></span>|<span data-ttu-id="51393-420">JIT 컴파일러에 의해 메서드가 성공적으로 인라인 될 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="51393-420">Raised when a method is successfully inlined by the JIT compiler.</span></span>|

|<span data-ttu-id="51393-421">필드 이름</span><span class="sxs-lookup"><span data-stu-id="51393-421">Field name</span></span>|<span data-ttu-id="51393-422">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51393-422">Data type</span></span>|<span data-ttu-id="51393-423">Description</span><span class="sxs-lookup"><span data-stu-id="51393-423">Description</span></span>|
|----------------|---------------|-----------------|
|`MethodBeingCompiledNamespace`|`win:UnicodeString`|<span data-ttu-id="51393-424">컴파일되는 메서드의 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-424">Namespace of the method being compiled.</span></span>|
|`MethodBeingCompiledName`|`win:UnicodeString`|<span data-ttu-id="51393-425">컴파일되는 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-425">Name of the method being compiled.</span></span>|
|`MethodBeingCompiledNameSignature`|`win:UnicodeString`|<span data-ttu-id="51393-426">컴파일되는 메서드의 서명입니다 (쉼표로 구분 된 형식 이름 목록).</span><span class="sxs-lookup"><span data-stu-id="51393-426">Signature of the method (comma-separated list of type names) being compiled.</span></span>|
|`InlinerNamespace`|`win:UnicodeString`|<span data-ttu-id="51393-427">인라인 처리자 ("parent") 메서드의 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-427">The namespace of inliner ("parent") method.</span></span>|
|`InlinerName`|`win:UnicodeString`|<span data-ttu-id="51393-428">인라인 처리자 ("parent") 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-428">Name of the inliner ("parent") method.</span></span>|
|`InlinerNameSignature`|`win:UnicodeString`|<span data-ttu-id="51393-429">인라인 처리자 ("parent") 메서드의 서명입니다 (쉼표로 구분 된 형식 이름 목록).</span><span class="sxs-lookup"><span data-stu-id="51393-429">Signature of the inliner ("parent") method (comma-separated list of type names).</span></span>|
|`InlineeNamespace`|`win:UnicodeString`|<span data-ttu-id="51393-430">인라인 대상 ("child") 메서드의 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-430">The namespace of inlinee ("child") method.</span></span>|
|`InlineeName`|`win:UnicodeString`|<span data-ttu-id="51393-431">인라인 대상 ("child") 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-431">Name of the inlinee ("child") method.</span></span>|
|`InlineeNameSignature`|`win:UnicodeString`|<span data-ttu-id="51393-432">인라인 대상 ("child") 메서드의 서명입니다 (쉼표로 구분 된 형식 이름 목록).</span><span class="sxs-lookup"><span data-stu-id="51393-432">Signature of the inlinee ("child") method (comma-separated list of type names).</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="51393-433">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-433">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="methodjitinliningfailed-event"></a><span data-ttu-id="51393-434">MethodJitInliningFailed 이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-434">MethodJitInliningFailed event</span></span>

|<span data-ttu-id="51393-435">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="51393-435">Keyword for raising the event</span></span>|<span data-ttu-id="51393-436">수준</span><span class="sxs-lookup"><span data-stu-id="51393-436">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="51393-437">`JITTracingKeyword` 0x1000</span><span class="sxs-lookup"><span data-stu-id="51393-437">`JITTracingKeyword` (0x1000)</span></span> |<span data-ttu-id="51393-438">자세한 정보 표시(5)</span><span class="sxs-lookup"><span data-stu-id="51393-438">Verbose (5)</span></span>|

|<span data-ttu-id="51393-439">이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-439">Event</span></span>|<span data-ttu-id="51393-440">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="51393-440">Event ID</span></span>|<span data-ttu-id="51393-441">Description</span><span class="sxs-lookup"><span data-stu-id="51393-441">Description</span></span>|
|-----------|--------------|-----------------|
|`MethodJitInliningFailed`|<span data-ttu-id="51393-442">192</span><span class="sxs-lookup"><span data-stu-id="51393-442">192</span></span>|<span data-ttu-id="51393-443">JIT 컴파일러에서 메서드를 인라이닝 하지 못할 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="51393-443">Raised when a method was failed to be inlined by the JIT compiler.</span></span>|

|<span data-ttu-id="51393-444">필드 이름</span><span class="sxs-lookup"><span data-stu-id="51393-444">Field name</span></span>|<span data-ttu-id="51393-445">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51393-445">Data type</span></span>|<span data-ttu-id="51393-446">Description</span><span class="sxs-lookup"><span data-stu-id="51393-446">Description</span></span>|
|----------------|---------------|-----------------|
|`MethodBeingCompiledNamespace`|`win:UnicodeString`|<span data-ttu-id="51393-447">컴파일되는 메서드의 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-447">Namespace of the method being compiled.</span></span>|
|`MethodBeingCompiledName`|`win:UnicodeString`|<span data-ttu-id="51393-448">컴파일되는 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-448">Name of the method being compiled.</span></span>|
|`MethodBeingCompiledNameSignature`|`win:UnicodeString`|<span data-ttu-id="51393-449">컴파일되는 메서드의 서명입니다 (쉼표로 구분 된 형식 이름 목록).</span><span class="sxs-lookup"><span data-stu-id="51393-449">Signature of the method (comma-separated list of type names) being compiled.</span></span>|
|`InlinerNamespace`|`win:UnicodeString`|<span data-ttu-id="51393-450">인라인 처리자 ("parent") 메서드의 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-450">The namespace of inliner ("parent") method.</span></span>|
|`InlinerName`|`win:UnicodeString`|<span data-ttu-id="51393-451">인라인 처리자 ("parent") 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-451">Name of the inliner ("parent") method.</span></span>|
|`InlinerNameSignature`|`win:UnicodeString`|<span data-ttu-id="51393-452">인라인 처리자 ("parent") 메서드의 서명입니다 (쉼표로 구분 된 형식 이름 목록).</span><span class="sxs-lookup"><span data-stu-id="51393-452">Signature of the inliner ("parent") method (comma-separated list of type names).</span></span>|
|`InlineeNamespace`|`win:UnicodeString`|<span data-ttu-id="51393-453">인라인 대상 ("child") 메서드의 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-453">The namespace of inlinee ("child") method.</span></span>|
|`InlineeName`|`win:UnicodeString`|<span data-ttu-id="51393-454">인라인 대상 ("child") 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-454">Name of the inlinee ("child") method.</span></span>|
|`InlineeNameSignature`|`win:UnicodeString`|<span data-ttu-id="51393-455">인라인 대상 ("child") 메서드의 서명입니다 (쉼표로 구분 된 형식 이름 목록).</span><span class="sxs-lookup"><span data-stu-id="51393-455">Signature of the inlinee ("child") method (comma-separated list of type names).</span></span>|
|`FailAlways`|`win:Boolean`|<span data-ttu-id="51393-456">메서드가 not inlinable로 표시 되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="51393-456">Whether the method is marked as not inlinable.</span></span>|
|`FailReason`|`win:UnicodeString`|<span data-ttu-id="51393-457">이유를 인라이닝 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="51393-457">Reason inlining failed.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="51393-458">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-458">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="methodjittailcallsucceeded-event"></a><span data-ttu-id="51393-459">MethodJitTailCallSucceeded 이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-459">MethodJitTailCallSucceeded event</span></span>

|<span data-ttu-id="51393-460">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="51393-460">Keyword for raising the event</span></span>|<span data-ttu-id="51393-461">수준</span><span class="sxs-lookup"><span data-stu-id="51393-461">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="51393-462">`JITTracingKeyword` 0x1000</span><span class="sxs-lookup"><span data-stu-id="51393-462">`JITTracingKeyword` (0x1000)</span></span> |<span data-ttu-id="51393-463">자세한 정보 표시(5)</span><span class="sxs-lookup"><span data-stu-id="51393-463">Verbose (5)</span></span>|

|<span data-ttu-id="51393-464">이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-464">Event</span></span>|<span data-ttu-id="51393-465">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="51393-465">Event ID</span></span>|<span data-ttu-id="51393-466">Description</span><span class="sxs-lookup"><span data-stu-id="51393-466">Description</span></span>|
|-----------|--------------|-----------------|
|`MethodJitTailCallSucceeded`|<span data-ttu-id="51393-467">192</span><span class="sxs-lookup"><span data-stu-id="51393-467">192</span></span>|<span data-ttu-id="51393-468">메서드가 성공적으로 호출 될 수 있는 경우 JIT 컴파일러에 의해 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="51393-468">Raised by the JIT compiler when a method can be successfully tail called.</span></span>|

|<span data-ttu-id="51393-469">필드 이름</span><span class="sxs-lookup"><span data-stu-id="51393-469">Field name</span></span>|<span data-ttu-id="51393-470">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51393-470">Data type</span></span>|<span data-ttu-id="51393-471">Description</span><span class="sxs-lookup"><span data-stu-id="51393-471">Description</span></span>|
|----------------|---------------|-----------------|
|`MethodBeingCompiledNamespace`|`win:UnicodeString`|<span data-ttu-id="51393-472">컴파일되는 메서드의 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-472">Namespace of the method being compiled.</span></span>|
|`MethodBeingCompiledName`|`win:UnicodeString`|<span data-ttu-id="51393-473">컴파일되는 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-473">Name of the method being compiled.</span></span>|
|`MethodBeingCompiledNameSignature`|`win:UnicodeString`|<span data-ttu-id="51393-474">컴파일되는 메서드의 서명입니다 (쉼표로 구분 된 형식 이름 목록).</span><span class="sxs-lookup"><span data-stu-id="51393-474">Signature of the method (comma-separated list of type names) being compiled.</span></span>|
|`CallerNamespace`|`win:UnicodeString`|<span data-ttu-id="51393-475">호출자 메서드의 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-475">Namespace of the caller method.</span></span>|
|`CallerName`|`win:UnicodeString`|<span data-ttu-id="51393-476">호출자 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-476">Name of the caller method.</span></span>|
|`CallerNameSignature`|`win:UnicodeString`|<span data-ttu-id="51393-477">호출자 메서드의 서명입니다 (쉼표로 구분 된 형식 이름 목록).</span><span class="sxs-lookup"><span data-stu-id="51393-477">Signature of the caller method (Comma-separated list of type names).</span></span>|
|`CalleeNamespace`|`win:UnicodeString`|<span data-ttu-id="51393-478">호출 수신자 메서드의 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-478">Namespace of the callee method.</span></span>|
|`CalleeName`|`win:UnicodeString`|<span data-ttu-id="51393-479">호출 수신자 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-479">Name of the callee method.</span></span>|
|`CalleeNameSignature`|`win:UnicodeString`|<span data-ttu-id="51393-480">호출 수신자 메서드의 서명입니다 (쉼표로 구분 된 형식 이름 목록).</span><span class="sxs-lookup"><span data-stu-id="51393-480">Signature of the callee method (Comma-separated list of type names).</span></span>|
|`TailPrefix`|`win:Boolean`|<span data-ttu-id="51393-481">Tail 접두사 명령 인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="51393-481">Whether it is a tail prefix instruction.</span></span>|
|`TailCallType`|`win:UInt32`|<span data-ttu-id="51393-482">마무리 호출의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-482">The type of tail call.</span></span><br/><br/><span data-ttu-id="51393-483">0: 마무리 호출 최적화 (에필로그 + jmp)</span><span class="sxs-lookup"><span data-stu-id="51393-483">0: Optimized tail call (epilog + jmp)</span></span><br/><br/><span data-ttu-id="51393-484">1: 재귀적 마무리 호출 (메서드 마무리 자체 호출)</span><span class="sxs-lookup"><span data-stu-id="51393-484">1: Recursive tail call (method tail calls itself)</span></span><br/><br/><span data-ttu-id="51393-485">2: 도우미 지원 마무리 호출</span><span class="sxs-lookup"><span data-stu-id="51393-485">2: Helper assisted tail call</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="51393-486">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-486">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="methodjittailcallfailed-event"></a><span data-ttu-id="51393-487">MethodJitTailCallFailed 이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-487">MethodJitTailCallFailed event</span></span>

|<span data-ttu-id="51393-488">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="51393-488">Keyword for raising the event</span></span>|<span data-ttu-id="51393-489">수준</span><span class="sxs-lookup"><span data-stu-id="51393-489">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="51393-490">`JITTracingKeyword` 0x1000</span><span class="sxs-lookup"><span data-stu-id="51393-490">`JITTracingKeyword` (0x1000)</span></span> |<span data-ttu-id="51393-491">자세한 정보 표시(5)</span><span class="sxs-lookup"><span data-stu-id="51393-491">Verbose (5)</span></span>|

|<span data-ttu-id="51393-492">이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-492">Event</span></span>|<span data-ttu-id="51393-493">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="51393-493">Event ID</span></span>|<span data-ttu-id="51393-494">Description</span><span class="sxs-lookup"><span data-stu-id="51393-494">Description</span></span>|
|-----------|--------------|-----------------|
|`MethodJitTailCallFailed`|<span data-ttu-id="51393-495">191</span><span class="sxs-lookup"><span data-stu-id="51393-495">191</span></span>|<span data-ttu-id="51393-496">메서드가 tail. 호출에 실패 한 경우 JIT 컴파일러에 의해 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="51393-496">Raised by the JIT compiler when a method was failed to be tail called.</span></span>|

|<span data-ttu-id="51393-497">필드 이름</span><span class="sxs-lookup"><span data-stu-id="51393-497">Field name</span></span>|<span data-ttu-id="51393-498">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51393-498">Data type</span></span>|<span data-ttu-id="51393-499">Description</span><span class="sxs-lookup"><span data-stu-id="51393-499">Description</span></span>|
|----------------|---------------|-----------------|
|`MethodBeingCompiledNamespace`|`win:UnicodeString`|<span data-ttu-id="51393-500">컴파일되는 메서드의 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-500">Namespace of the method being compiled.</span></span>|
|`MethodBeingCompiledName`|`win:UnicodeString`|<span data-ttu-id="51393-501">컴파일되는 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-501">Name of the method being compiled.</span></span>|
|`MethodBeingCompiledNameSignature`|`win:UnicodeString`|<span data-ttu-id="51393-502">컴파일되는 메서드의 서명입니다 (쉼표로 구분 된 형식 이름 목록).</span><span class="sxs-lookup"><span data-stu-id="51393-502">Signature of the method (comma-separated list of type names) being compiled.</span></span>|
|`CallerNamespace`|`win:UnicodeString`|<span data-ttu-id="51393-503">호출자 메서드의 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-503">Namespace of the caller method.</span></span>|
|<span data-ttu-id="51393-504">`CallerNam`e</span><span class="sxs-lookup"><span data-stu-id="51393-504">`CallerNam`e</span></span>|`win:UnicodeString`|<span data-ttu-id="51393-505">호출자 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-505">Name of the caller method.</span></span>|
|`CallerNameSignature`|`win:UnicodeString`|<span data-ttu-id="51393-506">호출자 메서드의 서명입니다 (쉼표로 구분 된 형식 이름 목록).</span><span class="sxs-lookup"><span data-stu-id="51393-506">Signature of the caller method (Comma-separated list of type names).</span></span>|
|`CalleeNamespace`|`win:UnicodeString`|<span data-ttu-id="51393-507">호출 수신자 메서드의 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-507">Namespace of the callee method.</span></span>|
|`CalleeName`|`win:UnicodeString`|<span data-ttu-id="51393-508">호출 수신자 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-508">Name of the callee method.</span></span>|
|`CalleeNameSignature`|`win:UnicodeString`|<span data-ttu-id="51393-509">호출 수신자 메서드의 서명입니다 (쉼표로 구분 된 형식 이름 목록).</span><span class="sxs-lookup"><span data-stu-id="51393-509">Signature of the callee method (Comma-separated list of type names).</span></span>|
|`TailPrefix`|`win:Boolean`|<span data-ttu-id="51393-510">Tail 접두사 명령 인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="51393-510">Whether it is a tail prefix instruction.</span></span>|
|`FailReason`|`win:UnicodeString`|<span data-ttu-id="51393-511">설명 tail 호출이 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="51393-511">Reason tail call failed.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="51393-512">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-512">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="methodiltonativemap-event"></a><span data-ttu-id="51393-513">MethodILToNativeMap 이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-513">MethodILToNativeMap event</span></span>

|<span data-ttu-id="51393-514">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="51393-514">Keyword for raising the event</span></span>|<span data-ttu-id="51393-515">수준</span><span class="sxs-lookup"><span data-stu-id="51393-515">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="51393-516">`JittedMethodILToNativeMapKeyword` (0x20000)</span><span class="sxs-lookup"><span data-stu-id="51393-516">`JittedMethodILToNativeMapKeyword` (0x20000)</span></span> |<span data-ttu-id="51393-517">자세한 정보 표시(5)</span><span class="sxs-lookup"><span data-stu-id="51393-517">Verbose (5)</span></span>|

|<span data-ttu-id="51393-518">이벤트</span><span class="sxs-lookup"><span data-stu-id="51393-518">Event</span></span>|<span data-ttu-id="51393-519">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="51393-519">Event ID</span></span>|<span data-ttu-id="51393-520">Description</span><span class="sxs-lookup"><span data-stu-id="51393-520">Description</span></span>|
|----------------|---------------|-----------------|
|`MethodILToNativeMap`|<span data-ttu-id="51393-521">190</span><span class="sxs-lookup"><span data-stu-id="51393-521">190</span></span>|<span data-ttu-id="51393-522">JIT 컴파일된 메서드에 대 한 IL-네이티브 맵 이벤트를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="51393-522">Maps the IL-to-native map event for JIT-compiled methods.</span></span>|

|<span data-ttu-id="51393-523">필드 이름</span><span class="sxs-lookup"><span data-stu-id="51393-523">Field name</span></span>|<span data-ttu-id="51393-524">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51393-524">Data type</span></span>|<span data-ttu-id="51393-525">Description</span><span class="sxs-lookup"><span data-stu-id="51393-525">Description</span></span>|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|<span data-ttu-id="51393-526">메서드의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-526">Unique identifier of a method.</span></span>|
|`ReJITID`|`win:UInt64`|<span data-ttu-id="51393-527">메서드의 ReJIT ID입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-527">The ReJIT ID of the method.</span></span>|
|`MethodExtent`|`win:UInt8`|<span data-ttu-id="51393-528">Jit 컴파일된 메서드의 익스텐트입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-528">The extent for the jitted method.</span></span>|
|`CountOfMapEntries`|`win:UInt8`|<span data-ttu-id="51393-529">맵 항목 수</span><span class="sxs-lookup"><span data-stu-id="51393-529">Number of map entries</span></span>|
|`ILOffsets`|`win:UInt32`|<span data-ttu-id="51393-530">IL 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-530">The IL offset.</span></span>|
|`NativeOffsets`|`win:UInt32`|<span data-ttu-id="51393-531">네이티브 코드 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-531">The native code offset.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="51393-532">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="51393-532">Unique ID for the instance of CoreCLR.</span></span>|
