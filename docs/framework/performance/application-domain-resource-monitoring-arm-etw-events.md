---
title: ARM(애플리케이션 도메인 리소스 모니터링) ETW 이벤트
description: '.NET의 ARM (응용 프로그램 도메인 리소스 모니터링) ETW 이벤트 (예: ThreadCreated, AppDomainMemAllocated, AppDomainMemSurvived 등)에 대해 읽어 보십시오.'
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
ms.openlocfilehash: d118b3196b019a804df5399464cb86f7492c61b0
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309783"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="7bf2f-103">ARM(애플리케이션 도메인 리소스 모니터링) ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="7bf2f-103">Application Domain Resource Monitoring (ARM) ETW Events</span></span>

<span data-ttu-id="7bf2f-104">이들 이벤트는 응용 프로그램 도메인 상태에 대한 자세한 진단 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-104">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="7bf2f-105">이들 이벤트를 사용하거나 애플리케이션 도메인 리소스 모니터링(ARM) 기능을 사용하여 같은 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-105">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>

## <a name="threadcreated-event"></a><span data-ttu-id="7bf2f-106">ThreadCreated 이벤트</span><span class="sxs-lookup"><span data-stu-id="7bf2f-106">ThreadCreated Event</span></span>

<span data-ttu-id="7bf2f-107">이 이벤트는 런다운 공급자에서만 `ThreadDC` 로서 발생합니다( `AppDomainResourceManagementRundownKeyword` 키워드에서).</span><span class="sxs-lookup"><span data-stu-id="7bf2f-107">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="7bf2f-108">이 이벤트는 이 범주의 런다운 공급자에서 발생하는 유일한 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-108">This is the only event that is raised under the rundown provider in this category.</span></span>

<span data-ttu-id="7bf2f-109">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-109">The following table shows the keyword and level.</span></span> <span data-ttu-id="7bf2f-110">자세한 내용은 [CLR ETW 키워드 및 수준](clr-etw-keywords-and-levels.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-110">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="7bf2f-111">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="7bf2f-111">Keyword for raising the event</span></span>|<span data-ttu-id="7bf2f-112">수준</span><span class="sxs-lookup"><span data-stu-id="7bf2f-112">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="7bf2f-113">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="7bf2f-113">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="7bf2f-114">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="7bf2f-114">Informational(4)</span></span>|
|<span data-ttu-id="7bf2f-115">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="7bf2f-115">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="7bf2f-116">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="7bf2f-116">Informational(4)</span></span>|

<span data-ttu-id="7bf2f-117">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-117">The following table shows the event information:</span></span>

|<span data-ttu-id="7bf2f-118">Event</span><span class="sxs-lookup"><span data-stu-id="7bf2f-118">Event</span></span>|<span data-ttu-id="7bf2f-119">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="7bf2f-119">Event ID</span></span>|<span data-ttu-id="7bf2f-120">발생 시기</span><span class="sxs-lookup"><span data-stu-id="7bf2f-120">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadCreated`|<span data-ttu-id="7bf2f-121">85</span><span class="sxs-lookup"><span data-stu-id="7bf2f-121">85</span></span>|<span data-ttu-id="7bf2f-122">애플리케이션 도메인에 대한 스레드가 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-122">A thread was created for the application domain.</span></span>|

<span data-ttu-id="7bf2f-123">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-123">The following table shows the event data:</span></span>

|<span data-ttu-id="7bf2f-124">필드 이름</span><span class="sxs-lookup"><span data-stu-id="7bf2f-124">Field name</span></span>|<span data-ttu-id="7bf2f-125">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7bf2f-125">Data type</span></span>|<span data-ttu-id="7bf2f-126">Description</span><span class="sxs-lookup"><span data-stu-id="7bf2f-126">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="7bf2f-127">ThreadID</span><span class="sxs-lookup"><span data-stu-id="7bf2f-127">ThreadID</span></span>|<span data-ttu-id="7bf2f-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7bf2f-128">win:UInt64</span></span>|<span data-ttu-id="7bf2f-129">만들어진 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-129">ID of the thread that was created.</span></span>|
|<span data-ttu-id="7bf2f-130">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="7bf2f-130">AppDomainID</span></span>|<span data-ttu-id="7bf2f-131">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7bf2f-131">win:UInt64</span></span>|<span data-ttu-id="7bf2f-132">스레드 활동이 보고되는 애플리케이션 도메인의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-132">Identifier of the application domain for which thread activity is being reported.</span></span>|
|<span data-ttu-id="7bf2f-133">플래그</span><span class="sxs-lookup"><span data-stu-id="7bf2f-133">Flags</span></span>|<span data-ttu-id="7bf2f-134">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7bf2f-134">win:UInt32</span></span>|<span data-ttu-id="7bf2f-135">스레드 만들기 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-135">Thread creation flags.</span></span>|
|<span data-ttu-id="7bf2f-136">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="7bf2f-136">ManagedThreadIndex</span></span>|<span data-ttu-id="7bf2f-137">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7bf2f-137">win:UInt32</span></span>|<span data-ttu-id="7bf2f-138">만들어진 스레드의 관리되는 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-138">Managed index of the thread that was created.</span></span>|
|<span data-ttu-id="7bf2f-139">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="7bf2f-139">OSThreadID</span></span>|<span data-ttu-id="7bf2f-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7bf2f-140">win:UInt32</span></span>|<span data-ttu-id="7bf2f-141">만들어진 스레드의 운영 체제 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-141">Operating system ID of the thread that was created.</span></span>|
|<span data-ttu-id="7bf2f-142">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="7bf2f-142">ClrInstanceID</span></span>|<span data-ttu-id="7bf2f-143">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="7bf2f-143">win:UInt16</span></span>|<span data-ttu-id="7bf2f-144">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-144">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemallocated-event"></a><span data-ttu-id="7bf2f-145">AppDomainMemAllocated 이벤트</span><span class="sxs-lookup"><span data-stu-id="7bf2f-145">AppDomainMemAllocated Event</span></span>

<span data-ttu-id="7bf2f-146">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-146">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="7bf2f-147">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="7bf2f-147">Keyword for raising the event</span></span>|<span data-ttu-id="7bf2f-148">수준</span><span class="sxs-lookup"><span data-stu-id="7bf2f-148">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="7bf2f-149">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="7bf2f-149">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="7bf2f-150">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="7bf2f-150">Informational(4)</span></span>|

<span data-ttu-id="7bf2f-151">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-151">The following table shows the event information:</span></span>

|<span data-ttu-id="7bf2f-152">Event</span><span class="sxs-lookup"><span data-stu-id="7bf2f-152">Event</span></span>|<span data-ttu-id="7bf2f-153">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="7bf2f-153">Event ID</span></span>|<span data-ttu-id="7bf2f-154">발생 시기</span><span class="sxs-lookup"><span data-stu-id="7bf2f-154">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemAllocated`|<span data-ttu-id="7bf2f-155">83</span><span class="sxs-lookup"><span data-stu-id="7bf2f-155">83</span></span>|<span data-ttu-id="7bf2f-156">약 4MB의 모든 메모리가 애플리케이션 도메인에서 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-156">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|

<span data-ttu-id="7bf2f-157">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-157">The following table shows the event data:</span></span>

|<span data-ttu-id="7bf2f-158">필드 이름</span><span class="sxs-lookup"><span data-stu-id="7bf2f-158">Field name</span></span>|<span data-ttu-id="7bf2f-159">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7bf2f-159">Data type</span></span>|<span data-ttu-id="7bf2f-160">Description</span><span class="sxs-lookup"><span data-stu-id="7bf2f-160">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="7bf2f-161">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="7bf2f-161">AppDomainID</span></span>|<span data-ttu-id="7bf2f-162">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7bf2f-162">win:UInt64</span></span>|<span data-ttu-id="7bf2f-163">리소스 사용량이 보고되는 애플리케이션 도메인의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-163">Identifier of the application domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="7bf2f-164">Allocated</span><span class="sxs-lookup"><span data-stu-id="7bf2f-164">Allocated</span></span>|<span data-ttu-id="7bf2f-165">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7bf2f-165">win:UInt64</span></span>|<span data-ttu-id="7bf2f-166">애플리케이션 도메인이 만들어진 후 이 애플리케이션 도메인에서 할당된 총 바이트 수입니다(해제된 메모리 양을 빼지 않음).</span><span class="sxs-lookup"><span data-stu-id="7bf2f-166">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|
|<span data-ttu-id="7bf2f-167">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="7bf2f-167">ClrInstanceID</span></span>|<span data-ttu-id="7bf2f-168">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="7bf2f-168">win:UInt16</span></span>|<span data-ttu-id="7bf2f-169">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-169">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="7bf2f-170">AppDomainMemSurvived 이벤트</span><span class="sxs-lookup"><span data-stu-id="7bf2f-170">AppDomainMemSurvived Event</span></span>

<span data-ttu-id="7bf2f-171">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-171">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="7bf2f-172">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="7bf2f-172">Keyword for raising the event</span></span>|<span data-ttu-id="7bf2f-173">수준</span><span class="sxs-lookup"><span data-stu-id="7bf2f-173">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="7bf2f-174">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="7bf2f-174">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="7bf2f-175">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="7bf2f-175">Informational(4)</span></span>|

<span data-ttu-id="7bf2f-176">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-176">The following table shows the event information:</span></span>

|<span data-ttu-id="7bf2f-177">Event</span><span class="sxs-lookup"><span data-stu-id="7bf2f-177">Event</span></span>|<span data-ttu-id="7bf2f-178">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="7bf2f-178">Event ID</span></span>|<span data-ttu-id="7bf2f-179">발생 시기</span><span class="sxs-lookup"><span data-stu-id="7bf2f-179">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemSurvived`|<span data-ttu-id="7bf2f-180">84</span><span class="sxs-lookup"><span data-stu-id="7bf2f-180">84</span></span>|<span data-ttu-id="7bf2f-181">각 가비지 수집이 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-181">Each garbage collection has ended.</span></span>|

<span data-ttu-id="7bf2f-182">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-182">The following table shows the event data:</span></span>

|<span data-ttu-id="7bf2f-183">필드 이름</span><span class="sxs-lookup"><span data-stu-id="7bf2f-183">Field name</span></span>|<span data-ttu-id="7bf2f-184">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7bf2f-184">Data type</span></span>|<span data-ttu-id="7bf2f-185">Description</span><span class="sxs-lookup"><span data-stu-id="7bf2f-185">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="7bf2f-186">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="7bf2f-186">AppDomainID</span></span>|<span data-ttu-id="7bf2f-187">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7bf2f-187">win:UInt64</span></span>|<span data-ttu-id="7bf2f-188">리소스 사용량이 보고되는 도메인의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-188">Identifier of the domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="7bf2f-189">Survived</span><span class="sxs-lookup"><span data-stu-id="7bf2f-189">Survived</span></span>|<span data-ttu-id="7bf2f-190">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7bf2f-190">win:UInt64</span></span>|<span data-ttu-id="7bf2f-191">마지막 수집 후에도 유지되고 이 애플리케이션 도메인에 저장되는 것으로 알려진 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-191">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="7bf2f-192">이 수는 전체 수집 후에 정확하고 완전하지만 임시 수집 후에는 불완전할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-192">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|
|<span data-ttu-id="7bf2f-193">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="7bf2f-193">ProcessSurvived</span></span>|<span data-ttu-id="7bf2f-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7bf2f-194">win:UInt64</span></span>|<span data-ttu-id="7bf2f-195">마지막 수집에서 유지된 총 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-195">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="7bf2f-196">전체 수집 후에 이 수는 관리되는 힙에 실시간으로 저장되는 바이트 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-196">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="7bf2f-197">임시 수집 후에 이 수는 임시 생성에 실시간으로 저장되는 바이트 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-197">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|
|<span data-ttu-id="7bf2f-198">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="7bf2f-198">ClrInstanceID</span></span>|<span data-ttu-id="7bf2f-199">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="7bf2f-199">win:UInt16</span></span>|<span data-ttu-id="7bf2f-200">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-200">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadappdomainenter-event"></a><span data-ttu-id="7bf2f-201">ThreadAppDomainEnter 이벤트</span><span class="sxs-lookup"><span data-stu-id="7bf2f-201">ThreadAppDomainEnter Event</span></span>

<span data-ttu-id="7bf2f-202">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-202">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="7bf2f-203">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="7bf2f-203">Keyword for raising the event</span></span>|<span data-ttu-id="7bf2f-204">수준</span><span class="sxs-lookup"><span data-stu-id="7bf2f-204">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="7bf2f-205">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="7bf2f-205">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="7bf2f-206">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="7bf2f-206">Informational(4)</span></span>|
|<span data-ttu-id="7bf2f-207">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="7bf2f-207">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="7bf2f-208">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="7bf2f-208">Informational(4)</span></span>|

<span data-ttu-id="7bf2f-209">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-209">The following table shows the event information:</span></span>

|<span data-ttu-id="7bf2f-210">Event</span><span class="sxs-lookup"><span data-stu-id="7bf2f-210">Event</span></span>|<span data-ttu-id="7bf2f-211">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="7bf2f-211">Event ID</span></span>|<span data-ttu-id="7bf2f-212">발생 시기</span><span class="sxs-lookup"><span data-stu-id="7bf2f-212">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadAppDomainEnter`|<span data-ttu-id="7bf2f-213">87</span><span class="sxs-lookup"><span data-stu-id="7bf2f-213">87</span></span>|<span data-ttu-id="7bf2f-214">스레드가 애플리케이션 도메인에 들어갑니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-214">A thread enters an application domain.</span></span>|

<span data-ttu-id="7bf2f-215">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-215">The following table shows the event data:</span></span>

|<span data-ttu-id="7bf2f-216">필드 이름</span><span class="sxs-lookup"><span data-stu-id="7bf2f-216">Field name</span></span>|<span data-ttu-id="7bf2f-217">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7bf2f-217">Data type</span></span>|<span data-ttu-id="7bf2f-218">Description</span><span class="sxs-lookup"><span data-stu-id="7bf2f-218">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="7bf2f-219">ThreadID</span><span class="sxs-lookup"><span data-stu-id="7bf2f-219">ThreadID</span></span>|<span data-ttu-id="7bf2f-220">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7bf2f-220">win:UInt64</span></span>|<span data-ttu-id="7bf2f-221">스레드 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-221">The thread identifier.</span></span>|
|<span data-ttu-id="7bf2f-222">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="7bf2f-222">AppDomainID</span></span>|<span data-ttu-id="7bf2f-223">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7bf2f-223">win:UInt64</span></span>|<span data-ttu-id="7bf2f-224">애플리케이션 도메인 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-224">The application domain identifier.</span></span>|
|<span data-ttu-id="7bf2f-225">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="7bf2f-225">ClrInstanceID</span></span>|<span data-ttu-id="7bf2f-226">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="7bf2f-226">win:UInt16</span></span>|<span data-ttu-id="7bf2f-227">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-227">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadterminated-event"></a><span data-ttu-id="7bf2f-228">ThreadTerminated 이벤트</span><span class="sxs-lookup"><span data-stu-id="7bf2f-228">ThreadTerminated Event</span></span>

<span data-ttu-id="7bf2f-229">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-229">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="7bf2f-230">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="7bf2f-230">Keyword for raising the event</span></span>|<span data-ttu-id="7bf2f-231">수준</span><span class="sxs-lookup"><span data-stu-id="7bf2f-231">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="7bf2f-232">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="7bf2f-232">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="7bf2f-233">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="7bf2f-233">Informational(4)</span></span>|
|<span data-ttu-id="7bf2f-234">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="7bf2f-234">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="7bf2f-235">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="7bf2f-235">Informational(4)</span></span>|

<span data-ttu-id="7bf2f-236">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-236">The following table shows the event information:</span></span>

|<span data-ttu-id="7bf2f-237">Event</span><span class="sxs-lookup"><span data-stu-id="7bf2f-237">Event</span></span>|<span data-ttu-id="7bf2f-238">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="7bf2f-238">Event ID</span></span>|<span data-ttu-id="7bf2f-239">발생 시기</span><span class="sxs-lookup"><span data-stu-id="7bf2f-239">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadTerminated`|<span data-ttu-id="7bf2f-240">86</span><span class="sxs-lookup"><span data-stu-id="7bf2f-240">86</span></span>|<span data-ttu-id="7bf2f-241">스레드가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-241">A thread terminates.</span></span>|

<span data-ttu-id="7bf2f-242">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-242">The following table shows the event data:</span></span>

|<span data-ttu-id="7bf2f-243">필드 이름</span><span class="sxs-lookup"><span data-stu-id="7bf2f-243">Field name</span></span>|<span data-ttu-id="7bf2f-244">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7bf2f-244">Data type</span></span>|<span data-ttu-id="7bf2f-245">Description</span><span class="sxs-lookup"><span data-stu-id="7bf2f-245">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="7bf2f-246">ThreadID</span><span class="sxs-lookup"><span data-stu-id="7bf2f-246">ThreadID</span></span>|<span data-ttu-id="7bf2f-247">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7bf2f-247">win:UInt64</span></span>|<span data-ttu-id="7bf2f-248">스레드 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-248">The thread identifier.</span></span>|
|<span data-ttu-id="7bf2f-249">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="7bf2f-249">AppDomainID</span></span>|<span data-ttu-id="7bf2f-250">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7bf2f-250">win:UInt64</span></span>|<span data-ttu-id="7bf2f-251">애플리케이션 도메인 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-251">The application domain identifier.</span></span>|
|<span data-ttu-id="7bf2f-252">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="7bf2f-252">ClrInstanceID</span></span>|<span data-ttu-id="7bf2f-253">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="7bf2f-253">win:UInt16</span></span>|<span data-ttu-id="7bf2f-254">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2f-254">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="see-also"></a><span data-ttu-id="7bf2f-255">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7bf2f-255">See also</span></span>

- [<span data-ttu-id="7bf2f-256">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="7bf2f-256">CLR ETW Events</span></span>](clr-etw-events.md)
