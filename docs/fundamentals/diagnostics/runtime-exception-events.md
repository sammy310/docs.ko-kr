---
title: 예외 런타임 이벤트
description: 예외 및 예외 처리와 관련 된 진단 정보를 수집 하는 .NET 런타임 이벤트를 참조 하세요.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- exception events (CoreCLR)
- exception handling events (CoreCLR)
- ETW, EventPipe, LTTng exception events (CoreCLR)
ms.openlocfilehash: f4f63c8469f9c734b872ddaec8d1d7f7f0427576
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96594105"
---
# <a name="net-runtime-exception-events"></a><span data-ttu-id="d0920-103">.NET 런타임 예외 이벤트</span><span class="sxs-lookup"><span data-stu-id="d0920-103">.NET runtime exception events</span></span>

<span data-ttu-id="d0920-104">이러한 런타임 이벤트는 throw 되는 예외에 대 한 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-104">These runtime events capture information about exceptions that are thrown.</span></span> <span data-ttu-id="d0920-105">진단 목적으로 이러한 이벤트를 사용 하는 방법에 대 한 자세한 내용은 [.net 응용 프로그램 로깅 및 추적](../../core/diagnostics/logging-tracing.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d0920-105">For more information about how to use these events for diagnostic purposes, see [logging and tracing .NET applications](../../core/diagnostics/logging-tracing.md)</span></span>

## <a name="exceptionthrown_v1-event"></a><span data-ttu-id="d0920-106">ExceptionThrown_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="d0920-106">ExceptionThrown_V1 event</span></span>

|<span data-ttu-id="d0920-107">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d0920-107">Keyword for raising the event</span></span>|<span data-ttu-id="d0920-108">수준</span><span class="sxs-lookup"><span data-stu-id="d0920-108">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d0920-109">`ExceptionKeyword`(0x8000)</span><span class="sxs-lookup"><span data-stu-id="d0920-109">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="d0920-110">오류 (1)</span><span class="sxs-lookup"><span data-stu-id="d0920-110">Error (1)</span></span>|

 <span data-ttu-id="d0920-111">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-111">The following table shows event information.</span></span>

|<span data-ttu-id="d0920-112">이벤트</span><span class="sxs-lookup"><span data-stu-id="d0920-112">Event</span></span>|<span data-ttu-id="d0920-113">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d0920-113">Event ID</span></span>|<span data-ttu-id="d0920-114">발생 시기</span><span class="sxs-lookup"><span data-stu-id="d0920-114">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionThrown_V1`|<span data-ttu-id="d0920-115">80</span><span class="sxs-lookup"><span data-stu-id="d0920-115">80</span></span>|<span data-ttu-id="d0920-116">관리되는 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-116">A managed exception is thrown.</span></span>|

|<span data-ttu-id="d0920-117">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d0920-117">Field name</span></span>|<span data-ttu-id="d0920-118">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d0920-118">Data type</span></span>|<span data-ttu-id="d0920-119">Description</span><span class="sxs-lookup"><span data-stu-id="d0920-119">Description</span></span>|
|----------------|---------------|-----------------|
|`ExceptionType`|`win:UnicodeString`|<span data-ttu-id="d0920-120">예외 형식, 예: `System.NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="d0920-120">Type of the exception; for example, `System.NullReferenceException`.</span></span>|
|`ExceptionMessage`|`win:UnicodeString`|<span data-ttu-id="d0920-121">실제 예외 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-121">Actual exception message.</span></span>|
|`EIPCodeThrow`|`win:Pointer`|<span data-ttu-id="d0920-122">예외가 발생한 명령 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-122">Instruction pointer where exception occurred.</span></span>|
|`ExceptionHR`|`win:UInt32`|<span data-ttu-id="d0920-123">예외 [HRESULT](/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a)입니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-123">Exception [HRESULT](/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).</span></span>|
|`ExceptionFlags`|`win:UInt16`|<span data-ttu-id="d0920-124">`0x01`: HasInnerException.</span><span class="sxs-lookup"><span data-stu-id="d0920-124">`0x01`: HasInnerException.</span></span><br /><br /> <span data-ttu-id="d0920-125">`0x02`: IsNestedException.</span><span class="sxs-lookup"><span data-stu-id="d0920-125">`0x02`: IsNestedException.</span></span><br /><br /> <span data-ttu-id="d0920-126">`0x04`: IsRethrownException.</span><span class="sxs-lookup"><span data-stu-id="d0920-126">`0x04`: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="d0920-127">`0x08`: IsCorruptedStateException (프로세스 상태가 손상 되었음을 나타냅니다. [손상 된 상태 예외 처리](/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)를 참조 하세요.)</span><span class="sxs-lookup"><span data-stu-id="d0920-127">`0x08`: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).</span></span><br /><br /> <span data-ttu-id="d0920-128">`0x10`: IsCLSCompliant (에서 파생 되는 예외는 <xref:System.Exception> cls 규격입니다. 그렇지 않으면 cls 규격이 아닙니다.)</span><span class="sxs-lookup"><span data-stu-id="d0920-128">`0x10`: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="d0920-129">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-129">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="exceptioncatchstart-event"></a><span data-ttu-id="d0920-130">ExceptionCatchStart 이벤트</span><span class="sxs-lookup"><span data-stu-id="d0920-130">ExceptionCatchStart event</span></span>

<span data-ttu-id="d0920-131">이 이벤트는 관리 되는 예외 catch 처리기가 시작 될 때 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-131">This event is emitted when a managed exception catch handler begins.</span></span>

|<span data-ttu-id="d0920-132">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d0920-132">Keyword for raising the event</span></span>|<span data-ttu-id="d0920-133">수준</span><span class="sxs-lookup"><span data-stu-id="d0920-133">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d0920-134">`ExceptionKeyword`(0x8000)</span><span class="sxs-lookup"><span data-stu-id="d0920-134">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="d0920-135">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d0920-135">Informational (4)</span></span>|

 <span data-ttu-id="d0920-136">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-136">The following table shows event information.</span></span>

|<span data-ttu-id="d0920-137">이벤트</span><span class="sxs-lookup"><span data-stu-id="d0920-137">Event</span></span>|<span data-ttu-id="d0920-138">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d0920-138">Event ID</span></span>|<span data-ttu-id="d0920-139">발생 시기</span><span class="sxs-lookup"><span data-stu-id="d0920-139">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionCatchStart`|<span data-ttu-id="d0920-140">250</span><span class="sxs-lookup"><span data-stu-id="d0920-140">250</span></span>|<span data-ttu-id="d0920-141">관리 되는 예외는 런타임에 의해 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-141">A managed exception is handled by the runtime.</span></span>|

|<span data-ttu-id="d0920-142">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d0920-142">Field name</span></span>|<span data-ttu-id="d0920-143">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d0920-143">Data type</span></span>|<span data-ttu-id="d0920-144">Description</span><span class="sxs-lookup"><span data-stu-id="d0920-144">Description</span></span>|
|----------------|---------------|-----------------|
|`EIPCodeThrow`|`win:Pointer`|<span data-ttu-id="d0920-145">예외가 발생한 명령 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-145">Instruction pointer where exception occurred.</span></span>|
|`MethodID`|`win:Pointer`|<span data-ttu-id="d0920-146">예외가 발생 한 메서드의 메서드 설명자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-146">Pointer to the method descriptor on the method where exception occurred.</span></span>|
|`MethodName`|`win:UnicodeString`|<span data-ttu-id="d0920-147">예외가 발생 한 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-147">Name of the method where exception occurred.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="d0920-148">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-148">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="exceptioncatchstop-event"></a><span data-ttu-id="d0920-149">ExceptionCatchStop 이벤트</span><span class="sxs-lookup"><span data-stu-id="d0920-149">ExceptionCatchStop event</span></span>

<span data-ttu-id="d0920-150">이 이벤트는 관리 되는 예외 catch 처리기가 종료 될 때 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-150">This event is emitted when a managed exception catch handler ends.</span></span>

|<span data-ttu-id="d0920-151">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d0920-151">Keyword for raising the event</span></span>|<span data-ttu-id="d0920-152">수준</span><span class="sxs-lookup"><span data-stu-id="d0920-152">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d0920-153">`ExceptionKeyword`(0x8000)</span><span class="sxs-lookup"><span data-stu-id="d0920-153">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="d0920-154">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d0920-154">Informational (4)</span></span>|

 <span data-ttu-id="d0920-155">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-155">The following table shows event information.</span></span>

|<span data-ttu-id="d0920-156">이벤트</span><span class="sxs-lookup"><span data-stu-id="d0920-156">Event</span></span>|<span data-ttu-id="d0920-157">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d0920-157">Event ID</span></span>|<span data-ttu-id="d0920-158">발생 시기</span><span class="sxs-lookup"><span data-stu-id="d0920-158">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionCatchStop`|<span data-ttu-id="d0920-159">251</span><span class="sxs-lookup"><span data-stu-id="d0920-159">251</span></span>|<span data-ttu-id="d0920-160">관리 되는 예외 catch 처리기가 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-160">A managed exception catch handler is done.</span></span>|

## <a name="exceptionfinallystart-event"></a><span data-ttu-id="d0920-161">ExceptionFinallyStart 이벤트</span><span class="sxs-lookup"><span data-stu-id="d0920-161">ExceptionFinallyStart event</span></span>

<span data-ttu-id="d0920-162">이 이벤트는 관리 되는 예외 finally 처리기가 시작 될 때 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-162">This event is emitted when a managed exception finally handler begins.</span></span>

|<span data-ttu-id="d0920-163">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d0920-163">Keyword for raising the event</span></span>|<span data-ttu-id="d0920-164">수준</span><span class="sxs-lookup"><span data-stu-id="d0920-164">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d0920-165">`ExceptionKeyword`(0x8000)</span><span class="sxs-lookup"><span data-stu-id="d0920-165">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="d0920-166">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d0920-166">Informational (4)</span></span>|

 <span data-ttu-id="d0920-167">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-167">The following table shows event information.</span></span>

|<span data-ttu-id="d0920-168">이벤트</span><span class="sxs-lookup"><span data-stu-id="d0920-168">Event</span></span>|<span data-ttu-id="d0920-169">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d0920-169">Event ID</span></span>|<span data-ttu-id="d0920-170">발생 시기</span><span class="sxs-lookup"><span data-stu-id="d0920-170">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionFinallyStart`|<span data-ttu-id="d0920-171">252</span><span class="sxs-lookup"><span data-stu-id="d0920-171">252</span></span>|<span data-ttu-id="d0920-172">관리 되는 예외는 런타임에 의해 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-172">A managed exception is handled by the runtime.</span></span>|

|<span data-ttu-id="d0920-173">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d0920-173">Field name</span></span>|<span data-ttu-id="d0920-174">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d0920-174">Data type</span></span>|<span data-ttu-id="d0920-175">Description</span><span class="sxs-lookup"><span data-stu-id="d0920-175">Description</span></span>|
|----------------|---------------|-----------------|
|`EIPCodeThrow`|`win:Pointer`|<span data-ttu-id="d0920-176">예외가 발생한 명령 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-176">Instruction pointer where exception occurred.</span></span>|
|`MethodID`|`win:Pointer`|<span data-ttu-id="d0920-177">예외가 발생 한 메서드의 메서드 설명자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-177">Pointer to the method descriptor on the method where exception occurred.</span></span>|
|`MethodName`|`win:UnicodeString`|<span data-ttu-id="d0920-178">예외가 발생 한 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-178">Name of the method where exception occurred.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="d0920-179">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-179">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="exceptionfinallystop-event"></a><span data-ttu-id="d0920-180">ExceptionFinallyStop 이벤트</span><span class="sxs-lookup"><span data-stu-id="d0920-180">ExceptionFinallyStop event</span></span>

<span data-ttu-id="d0920-181">이 이벤트는 관리 되는 예외 catch 처리기가 종료 될 때 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-181">This event is emitted when a managed exception catch handler ends.</span></span>

|<span data-ttu-id="d0920-182">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d0920-182">Keyword for raising the event</span></span>|<span data-ttu-id="d0920-183">수준</span><span class="sxs-lookup"><span data-stu-id="d0920-183">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d0920-184">`ExceptionKeyword`(0x8000)</span><span class="sxs-lookup"><span data-stu-id="d0920-184">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="d0920-185">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d0920-185">Informational (4)</span></span>|

 <span data-ttu-id="d0920-186">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-186">The following table shows event information.</span></span>

|<span data-ttu-id="d0920-187">이벤트</span><span class="sxs-lookup"><span data-stu-id="d0920-187">Event</span></span>|<span data-ttu-id="d0920-188">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d0920-188">Event ID</span></span>|<span data-ttu-id="d0920-189">발생 시기</span><span class="sxs-lookup"><span data-stu-id="d0920-189">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionFinallyStop`|<span data-ttu-id="d0920-190">253</span><span class="sxs-lookup"><span data-stu-id="d0920-190">253</span></span>|<span data-ttu-id="d0920-191">관리 되는 예외 finally 처리기가 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-191">A managed exception finally handler is done.</span></span>|

## <a name="exceptionfilterstart-event"></a><span data-ttu-id="d0920-192">ExceptionFilterStart 이벤트</span><span class="sxs-lookup"><span data-stu-id="d0920-192">ExceptionFilterStart event</span></span>

<span data-ttu-id="d0920-193">이 이벤트는 관리 되는 예외 필터링이 시작 될 때 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-193">This event is emitted when a managed exception filtering begins.</span></span>

|<span data-ttu-id="d0920-194">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d0920-194">Keyword for raising the event</span></span>|<span data-ttu-id="d0920-195">수준</span><span class="sxs-lookup"><span data-stu-id="d0920-195">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d0920-196">`ExceptionKeyword`(0x8000)</span><span class="sxs-lookup"><span data-stu-id="d0920-196">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="d0920-197">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d0920-197">Informational (4)</span></span>|

 <span data-ttu-id="d0920-198">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-198">The following table shows event information.</span></span>

|<span data-ttu-id="d0920-199">이벤트</span><span class="sxs-lookup"><span data-stu-id="d0920-199">Event</span></span>|<span data-ttu-id="d0920-200">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d0920-200">Event ID</span></span>|<span data-ttu-id="d0920-201">발생 시기</span><span class="sxs-lookup"><span data-stu-id="d0920-201">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionFilterStart`|<span data-ttu-id="d0920-202">254</span><span class="sxs-lookup"><span data-stu-id="d0920-202">254</span></span>|<span data-ttu-id="d0920-203">관리 되는 예외 필터링이 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-203">A managed exception filtering begins.</span></span>|

|<span data-ttu-id="d0920-204">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d0920-204">Field name</span></span>|<span data-ttu-id="d0920-205">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d0920-205">Data type</span></span>|<span data-ttu-id="d0920-206">Description</span><span class="sxs-lookup"><span data-stu-id="d0920-206">Description</span></span>|
|----------------|---------------|-----------------|
|`EIPCodeThrow`|`win:Pointer`|<span data-ttu-id="d0920-207">예외가 발생한 명령 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-207">Instruction pointer where exception occurred.</span></span>|
|`MethodID`|`win:Pointer`|<span data-ttu-id="d0920-208">예외가 발생 한 메서드의 메서드 설명자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-208">Pointer to the method descriptor on the method where exception occurred.</span></span>|
|`MethodName`|`win:UnicodeString`|<span data-ttu-id="d0920-209">예외가 발생 한 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-209">Name of the method where exception occurred.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="d0920-210">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-210">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="exceptionfilterstop-event"></a><span data-ttu-id="d0920-211">ExceptionFilterStop 이벤트</span><span class="sxs-lookup"><span data-stu-id="d0920-211">ExceptionFilterStop event</span></span>

<span data-ttu-id="d0920-212">이 이벤트는 관리 되는 예외 필터링이 종료 될 때 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-212">This event is emitted when a managed exception filtering ends.</span></span>

|<span data-ttu-id="d0920-213">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d0920-213">Keyword for raising the event</span></span>|<span data-ttu-id="d0920-214">수준</span><span class="sxs-lookup"><span data-stu-id="d0920-214">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d0920-215">`ExceptionKeyword`(0x8000)</span><span class="sxs-lookup"><span data-stu-id="d0920-215">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="d0920-216">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d0920-216">Informational (4)</span></span>|

 <span data-ttu-id="d0920-217">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-217">The following table shows event information.</span></span>

|<span data-ttu-id="d0920-218">이벤트</span><span class="sxs-lookup"><span data-stu-id="d0920-218">Event</span></span>|<span data-ttu-id="d0920-219">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d0920-219">Event ID</span></span>|<span data-ttu-id="d0920-220">발생 시기</span><span class="sxs-lookup"><span data-stu-id="d0920-220">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionFilteringStart`|<span data-ttu-id="d0920-221">255</span><span class="sxs-lookup"><span data-stu-id="d0920-221">255</span></span>|<span data-ttu-id="d0920-222">관리 되는 예외 필터링이 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-222">A managed exception filtering ends.</span></span>|

## <a name="exceptionthrownstop-event"></a><span data-ttu-id="d0920-223">ExceptionThrownStop 이벤트</span><span class="sxs-lookup"><span data-stu-id="d0920-223">ExceptionThrownStop event</span></span>

<span data-ttu-id="d0920-224">이 이벤트는 런타임에 throw 된 관리 되는 예외를 처리할 때 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-224">This event is emitted when the runtime is done handling a managed exception that was thrown.</span></span>

|<span data-ttu-id="d0920-225">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d0920-225">Keyword for raising the event</span></span>|<span data-ttu-id="d0920-226">수준</span><span class="sxs-lookup"><span data-stu-id="d0920-226">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d0920-227">`ExceptionKeyword`(0x8000)</span><span class="sxs-lookup"><span data-stu-id="d0920-227">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="d0920-228">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d0920-228">Informational (4)</span></span>|
  
 <span data-ttu-id="d0920-229">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-229">The following table shows event information.</span></span>

|<span data-ttu-id="d0920-230">이벤트</span><span class="sxs-lookup"><span data-stu-id="d0920-230">Event</span></span>|<span data-ttu-id="d0920-231">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d0920-231">Event ID</span></span>|<span data-ttu-id="d0920-232">발생 시기</span><span class="sxs-lookup"><span data-stu-id="d0920-232">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionThrownStop`|<span data-ttu-id="d0920-233">256</span><span class="sxs-lookup"><span data-stu-id="d0920-233">256</span></span>|<span data-ttu-id="d0920-234">관리 되는 예외 필터링이 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0920-234">A managed exception filtering ends.</span></span>|
