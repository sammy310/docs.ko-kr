---
title: ARM(애플리케이션 도메인 리소스 모니터링) ETW 이벤트
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6e1c2a38be6f2c15a118b35925570119b474f096
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040573"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="6f2e1-102">ARM(애플리케이션 도메인 리소스 모니터링) ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="6f2e1-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>

<span data-ttu-id="6f2e1-103">이들 이벤트는 응용 프로그램 도메인 상태에 대한 자세한 진단 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="6f2e1-104">이들 이벤트를 사용하거나 애플리케이션 도메인 리소스 모니터링(ARM) 기능을 사용하여 같은 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>

## <a name="threadcreated-event"></a><span data-ttu-id="6f2e1-105">ThreadCreated 이벤트</span><span class="sxs-lookup"><span data-stu-id="6f2e1-105">ThreadCreated Event</span></span>

<span data-ttu-id="6f2e1-106">이 이벤트는 런다운 공급자에서만 `ThreadDC` 로서 발생합니다( `AppDomainResourceManagementRundownKeyword` 키워드에서).</span><span class="sxs-lookup"><span data-stu-id="6f2e1-106">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="6f2e1-107">이 이벤트는 이 범주의 런다운 공급자에서 발생하는 유일한 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-107">This is the only event that is raised under the rundown provider in this category.</span></span>

<span data-ttu-id="6f2e1-108">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="6f2e1-109">자세한 내용은 [CLR ETW 키워드 및 수준](clr-etw-keywords-and-levels.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-109">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="6f2e1-110">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="6f2e1-110">Keyword for raising the event</span></span>|<span data-ttu-id="6f2e1-111">Level</span><span class="sxs-lookup"><span data-stu-id="6f2e1-111">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="6f2e1-112">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="6f2e1-112">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="6f2e1-113">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="6f2e1-113">Informational(4)</span></span>|
|<span data-ttu-id="6f2e1-114">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="6f2e1-114">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="6f2e1-115">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="6f2e1-115">Informational(4)</span></span>|

<span data-ttu-id="6f2e1-116">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-116">The following table shows the event information:</span></span>

|<span data-ttu-id="6f2e1-117">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="6f2e1-117">Event</span></span>|<span data-ttu-id="6f2e1-118">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="6f2e1-118">Event ID</span></span>|<span data-ttu-id="6f2e1-119">발생 시기</span><span class="sxs-lookup"><span data-stu-id="6f2e1-119">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadCreated`|<span data-ttu-id="6f2e1-120">85</span><span class="sxs-lookup"><span data-stu-id="6f2e1-120">85</span></span>|<span data-ttu-id="6f2e1-121">애플리케이션 도메인에 대한 스레드가 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-121">A thread was created for the application domain.</span></span>|

<span data-ttu-id="6f2e1-122">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-122">The following table shows the event data:</span></span>

|<span data-ttu-id="6f2e1-123">필드 이름</span><span class="sxs-lookup"><span data-stu-id="6f2e1-123">Field name</span></span>|<span data-ttu-id="6f2e1-124">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="6f2e1-124">Data type</span></span>|<span data-ttu-id="6f2e1-125">설명</span><span class="sxs-lookup"><span data-stu-id="6f2e1-125">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="6f2e1-126">ThreadID</span><span class="sxs-lookup"><span data-stu-id="6f2e1-126">ThreadID</span></span>|<span data-ttu-id="6f2e1-127">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6f2e1-127">win:UInt64</span></span>|<span data-ttu-id="6f2e1-128">만들어진 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-128">ID of the thread that was created.</span></span>|
|<span data-ttu-id="6f2e1-129">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="6f2e1-129">AppDomainID</span></span>|<span data-ttu-id="6f2e1-130">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6f2e1-130">win:UInt64</span></span>|<span data-ttu-id="6f2e1-131">스레드 활동이 보고되는 애플리케이션 도메인의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-131">Identifier of the application domain for which thread activity is being reported.</span></span>|
|<span data-ttu-id="6f2e1-132">플래그</span><span class="sxs-lookup"><span data-stu-id="6f2e1-132">Flags</span></span>|<span data-ttu-id="6f2e1-133">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="6f2e1-133">win:UInt32</span></span>|<span data-ttu-id="6f2e1-134">스레드 만들기 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-134">Thread creation flags.</span></span>|
|<span data-ttu-id="6f2e1-135">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="6f2e1-135">ManagedThreadIndex</span></span>|<span data-ttu-id="6f2e1-136">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="6f2e1-136">win:UInt32</span></span>|<span data-ttu-id="6f2e1-137">만들어진 스레드의 관리되는 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-137">Managed index of the thread that was created.</span></span>|
|<span data-ttu-id="6f2e1-138">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="6f2e1-138">OSThreadID</span></span>|<span data-ttu-id="6f2e1-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="6f2e1-139">win:UInt32</span></span>|<span data-ttu-id="6f2e1-140">만들어진 스레드의 운영 체제 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-140">Operating system ID of the thread that was created.</span></span>|
|<span data-ttu-id="6f2e1-141">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="6f2e1-141">ClrInstanceID</span></span>|<span data-ttu-id="6f2e1-142">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="6f2e1-142">win:UInt16</span></span>|<span data-ttu-id="6f2e1-143">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-143">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemallocated-event"></a><span data-ttu-id="6f2e1-144">AppDomainMemAllocated 이벤트</span><span class="sxs-lookup"><span data-stu-id="6f2e1-144">AppDomainMemAllocated Event</span></span>

<span data-ttu-id="6f2e1-145">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-145">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="6f2e1-146">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="6f2e1-146">Keyword for raising the event</span></span>|<span data-ttu-id="6f2e1-147">Level</span><span class="sxs-lookup"><span data-stu-id="6f2e1-147">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="6f2e1-148">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="6f2e1-148">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="6f2e1-149">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="6f2e1-149">Informational(4)</span></span>|

<span data-ttu-id="6f2e1-150">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-150">The following table shows the event information:</span></span>

|<span data-ttu-id="6f2e1-151">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="6f2e1-151">Event</span></span>|<span data-ttu-id="6f2e1-152">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="6f2e1-152">Event ID</span></span>|<span data-ttu-id="6f2e1-153">발생 시기</span><span class="sxs-lookup"><span data-stu-id="6f2e1-153">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemAllocated`|<span data-ttu-id="6f2e1-154">83</span><span class="sxs-lookup"><span data-stu-id="6f2e1-154">83</span></span>|<span data-ttu-id="6f2e1-155">약 4MB의 모든 메모리가 애플리케이션 도메인에서 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-155">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|

<span data-ttu-id="6f2e1-156">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-156">The following table shows the event data:</span></span>

|<span data-ttu-id="6f2e1-157">필드 이름</span><span class="sxs-lookup"><span data-stu-id="6f2e1-157">Field name</span></span>|<span data-ttu-id="6f2e1-158">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="6f2e1-158">Data type</span></span>|<span data-ttu-id="6f2e1-159">설명</span><span class="sxs-lookup"><span data-stu-id="6f2e1-159">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="6f2e1-160">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="6f2e1-160">AppDomainID</span></span>|<span data-ttu-id="6f2e1-161">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6f2e1-161">win:UInt64</span></span>|<span data-ttu-id="6f2e1-162">리소스 사용량이 보고되는 애플리케이션 도메인의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-162">Identifier of the application domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="6f2e1-163">Allocated</span><span class="sxs-lookup"><span data-stu-id="6f2e1-163">Allocated</span></span>|<span data-ttu-id="6f2e1-164">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6f2e1-164">win:UInt64</span></span>|<span data-ttu-id="6f2e1-165">애플리케이션 도메인이 만들어진 후 이 애플리케이션 도메인에서 할당된 총 바이트 수입니다(해제된 메모리 양을 빼지 않음).</span><span class="sxs-lookup"><span data-stu-id="6f2e1-165">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|
|<span data-ttu-id="6f2e1-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="6f2e1-166">ClrInstanceID</span></span>|<span data-ttu-id="6f2e1-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="6f2e1-167">win:UInt16</span></span>|<span data-ttu-id="6f2e1-168">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="6f2e1-169">AppDomainMemSurvived 이벤트</span><span class="sxs-lookup"><span data-stu-id="6f2e1-169">AppDomainMemSurvived Event</span></span>

<span data-ttu-id="6f2e1-170">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-170">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="6f2e1-171">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="6f2e1-171">Keyword for raising the event</span></span>|<span data-ttu-id="6f2e1-172">Level</span><span class="sxs-lookup"><span data-stu-id="6f2e1-172">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="6f2e1-173">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="6f2e1-173">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="6f2e1-174">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="6f2e1-174">Informational(4)</span></span>|

<span data-ttu-id="6f2e1-175">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-175">The following table shows the event information:</span></span>

|<span data-ttu-id="6f2e1-176">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="6f2e1-176">Event</span></span>|<span data-ttu-id="6f2e1-177">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="6f2e1-177">Event ID</span></span>|<span data-ttu-id="6f2e1-178">발생 시기</span><span class="sxs-lookup"><span data-stu-id="6f2e1-178">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemSurvived`|<span data-ttu-id="6f2e1-179">84</span><span class="sxs-lookup"><span data-stu-id="6f2e1-179">84</span></span>|<span data-ttu-id="6f2e1-180">각 가비지 수집이 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-180">Each garbage collection has ended.</span></span>|

<span data-ttu-id="6f2e1-181">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-181">The following table shows the event data:</span></span>

|<span data-ttu-id="6f2e1-182">필드 이름</span><span class="sxs-lookup"><span data-stu-id="6f2e1-182">Field name</span></span>|<span data-ttu-id="6f2e1-183">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="6f2e1-183">Data type</span></span>|<span data-ttu-id="6f2e1-184">설명</span><span class="sxs-lookup"><span data-stu-id="6f2e1-184">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="6f2e1-185">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="6f2e1-185">AppDomainID</span></span>|<span data-ttu-id="6f2e1-186">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6f2e1-186">win:UInt64</span></span>|<span data-ttu-id="6f2e1-187">리소스 사용량이 보고되는 도메인의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-187">Identifier of the domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="6f2e1-188">Survived</span><span class="sxs-lookup"><span data-stu-id="6f2e1-188">Survived</span></span>|<span data-ttu-id="6f2e1-189">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6f2e1-189">win:UInt64</span></span>|<span data-ttu-id="6f2e1-190">마지막 수집 후에도 유지되고 이 애플리케이션 도메인에 저장되는 것으로 알려진 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-190">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="6f2e1-191">이 수는 전체 수집 후에 정확하고 완전하지만 임시 수집 후에는 불완전할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-191">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|
|<span data-ttu-id="6f2e1-192">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="6f2e1-192">ProcessSurvived</span></span>|<span data-ttu-id="6f2e1-193">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6f2e1-193">win:UInt64</span></span>|<span data-ttu-id="6f2e1-194">마지막 수집에서 유지된 총 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-194">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="6f2e1-195">전체 수집 후에 이 수는 관리되는 힙에 실시간으로 저장되는 바이트 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-195">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="6f2e1-196">임시 수집 후에 이 수는 임시 생성에 실시간으로 저장되는 바이트 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-196">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|
|<span data-ttu-id="6f2e1-197">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="6f2e1-197">ClrInstanceID</span></span>|<span data-ttu-id="6f2e1-198">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="6f2e1-198">win:UInt16</span></span>|<span data-ttu-id="6f2e1-199">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-199">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadappdomainenter-event"></a><span data-ttu-id="6f2e1-200">ThreadAppDomainEnter 이벤트</span><span class="sxs-lookup"><span data-stu-id="6f2e1-200">ThreadAppDomainEnter Event</span></span>

<span data-ttu-id="6f2e1-201">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-201">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="6f2e1-202">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="6f2e1-202">Keyword for raising the event</span></span>|<span data-ttu-id="6f2e1-203">Level</span><span class="sxs-lookup"><span data-stu-id="6f2e1-203">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="6f2e1-204">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="6f2e1-204">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="6f2e1-205">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="6f2e1-205">Informational(4)</span></span>|
|<span data-ttu-id="6f2e1-206">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="6f2e1-206">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="6f2e1-207">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="6f2e1-207">Informational(4)</span></span>|

<span data-ttu-id="6f2e1-208">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-208">The following table shows the event information:</span></span>

|<span data-ttu-id="6f2e1-209">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="6f2e1-209">Event</span></span>|<span data-ttu-id="6f2e1-210">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="6f2e1-210">Event ID</span></span>|<span data-ttu-id="6f2e1-211">발생 시기</span><span class="sxs-lookup"><span data-stu-id="6f2e1-211">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadAppDomainEnter`|<span data-ttu-id="6f2e1-212">87</span><span class="sxs-lookup"><span data-stu-id="6f2e1-212">87</span></span>|<span data-ttu-id="6f2e1-213">스레드가 애플리케이션 도메인에 들어갑니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-213">A thread enters an application domain.</span></span>|

<span data-ttu-id="6f2e1-214">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-214">The following table shows the event data:</span></span>

|<span data-ttu-id="6f2e1-215">필드 이름</span><span class="sxs-lookup"><span data-stu-id="6f2e1-215">Field name</span></span>|<span data-ttu-id="6f2e1-216">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="6f2e1-216">Data type</span></span>|<span data-ttu-id="6f2e1-217">설명</span><span class="sxs-lookup"><span data-stu-id="6f2e1-217">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="6f2e1-218">ThreadID</span><span class="sxs-lookup"><span data-stu-id="6f2e1-218">ThreadID</span></span>|<span data-ttu-id="6f2e1-219">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6f2e1-219">win:UInt64</span></span>|<span data-ttu-id="6f2e1-220">스레드 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-220">The thread identifier.</span></span>|
|<span data-ttu-id="6f2e1-221">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="6f2e1-221">AppDomainID</span></span>|<span data-ttu-id="6f2e1-222">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6f2e1-222">win:UInt64</span></span>|<span data-ttu-id="6f2e1-223">애플리케이션 도메인 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-223">The application domain identifier.</span></span>|
|<span data-ttu-id="6f2e1-224">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="6f2e1-224">ClrInstanceID</span></span>|<span data-ttu-id="6f2e1-225">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="6f2e1-225">win:UInt16</span></span>|<span data-ttu-id="6f2e1-226">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-226">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadterminated-event"></a><span data-ttu-id="6f2e1-227">ThreadTerminated 이벤트</span><span class="sxs-lookup"><span data-stu-id="6f2e1-227">ThreadTerminated Event</span></span>

<span data-ttu-id="6f2e1-228">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-228">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="6f2e1-229">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="6f2e1-229">Keyword for raising the event</span></span>|<span data-ttu-id="6f2e1-230">Level</span><span class="sxs-lookup"><span data-stu-id="6f2e1-230">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="6f2e1-231">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="6f2e1-231">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="6f2e1-232">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="6f2e1-232">Informational(4)</span></span>|
|<span data-ttu-id="6f2e1-233">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="6f2e1-233">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="6f2e1-234">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="6f2e1-234">Informational(4)</span></span>|

<span data-ttu-id="6f2e1-235">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-235">The following table shows the event information:</span></span>

|<span data-ttu-id="6f2e1-236">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="6f2e1-236">Event</span></span>|<span data-ttu-id="6f2e1-237">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="6f2e1-237">Event ID</span></span>|<span data-ttu-id="6f2e1-238">발생 시기</span><span class="sxs-lookup"><span data-stu-id="6f2e1-238">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadTerminated`|<span data-ttu-id="6f2e1-239">86</span><span class="sxs-lookup"><span data-stu-id="6f2e1-239">86</span></span>|<span data-ttu-id="6f2e1-240">스레드가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-240">A thread terminates.</span></span>|

<span data-ttu-id="6f2e1-241">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-241">The following table shows the event data:</span></span>

|<span data-ttu-id="6f2e1-242">필드 이름</span><span class="sxs-lookup"><span data-stu-id="6f2e1-242">Field name</span></span>|<span data-ttu-id="6f2e1-243">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="6f2e1-243">Data type</span></span>|<span data-ttu-id="6f2e1-244">설명</span><span class="sxs-lookup"><span data-stu-id="6f2e1-244">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="6f2e1-245">ThreadID</span><span class="sxs-lookup"><span data-stu-id="6f2e1-245">ThreadID</span></span>|<span data-ttu-id="6f2e1-246">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6f2e1-246">win:UInt64</span></span>|<span data-ttu-id="6f2e1-247">스레드 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-247">The thread identifier.</span></span>|
|<span data-ttu-id="6f2e1-248">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="6f2e1-248">AppDomainID</span></span>|<span data-ttu-id="6f2e1-249">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6f2e1-249">win:UInt64</span></span>|<span data-ttu-id="6f2e1-250">애플리케이션 도메인 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-250">The application domain identifier.</span></span>|
|<span data-ttu-id="6f2e1-251">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="6f2e1-251">ClrInstanceID</span></span>|<span data-ttu-id="6f2e1-252">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="6f2e1-252">win:UInt16</span></span>|<span data-ttu-id="6f2e1-253">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2e1-253">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="see-also"></a><span data-ttu-id="6f2e1-254">참조</span><span class="sxs-lookup"><span data-stu-id="6f2e1-254">See also</span></span>

- [<span data-ttu-id="6f2e1-255">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="6f2e1-255">CLR ETW Events</span></span>](clr-etw-events.md)
