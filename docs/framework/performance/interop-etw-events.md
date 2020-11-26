---
title: Interop ETW 이벤트
description: .NET에서 캐싱을 & MSIL (Microsoft 중간 언어) 스텁 생성에 대 한 정보를 캡처하는 interop ETW (Windows 용 이벤트 추적) 이벤트를 검토 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- interop events [.NET Framework]
- ETW, interop events (CLR)
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
ms.openlocfilehash: 8e92a1492d0295fb71473843752cb4c6184d3604
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242190"
---
# <a name="interop-etw-events"></a><span data-ttu-id="c09f9-103">Interop ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="c09f9-103">Interop ETW Events</span></span>

<span data-ttu-id="c09f9-104">Interop 이벤트는 MSIL(Microsoft Intermediate Language) 스텁 생성 및 캐싱에 대한 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="c09f9-104">Interop events capture information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  

## <a name="ilstubgenerated-event"></a><span data-ttu-id="c09f9-105">ILStubGenerated 이벤트</span><span class="sxs-lookup"><span data-stu-id="c09f9-105">ILStubGenerated Event</span></span>

<span data-ttu-id="c09f9-106">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c09f9-106">The following table shows the keyword and level.</span></span> <span data-ttu-id="c09f9-107">자세한 내용은 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c09f9-107">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="c09f9-108">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="c09f9-108">Keyword for raising the event</span></span>|<span data-ttu-id="c09f9-109">Level</span><span class="sxs-lookup"><span data-stu-id="c09f9-109">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="c09f9-110">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="c09f9-110">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="c09f9-111">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="c09f9-111">Informational(4)</span></span>|  
  
 <span data-ttu-id="c09f9-112">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c09f9-112">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c09f9-113">이벤트</span><span class="sxs-lookup"><span data-stu-id="c09f9-113">Event</span></span>|<span data-ttu-id="c09f9-114">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c09f9-114">Event ID</span></span>|<span data-ttu-id="c09f9-115">발생 시기</span><span class="sxs-lookup"><span data-stu-id="c09f9-115">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|<span data-ttu-id="c09f9-116">88</span><span class="sxs-lookup"><span data-stu-id="c09f9-116">88</span></span>|<span data-ttu-id="c09f9-117">MSIL 스텁이 생성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c09f9-117">The MSIL stub has been generated.</span></span>|  
  
 <span data-ttu-id="c09f9-118">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c09f9-118">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="c09f9-119">필드 이름</span><span class="sxs-lookup"><span data-stu-id="c09f9-119">Field name</span></span>|<span data-ttu-id="c09f9-120">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c09f9-120">Data type</span></span>|<span data-ttu-id="c09f9-121">Description</span><span class="sxs-lookup"><span data-stu-id="c09f9-121">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c09f9-122">ModuleID</span><span class="sxs-lookup"><span data-stu-id="c09f9-122">ModuleID</span></span>|<span data-ttu-id="c09f9-123">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c09f9-123">win:UInt16</span></span>|<span data-ttu-id="c09f9-124">모듈 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="c09f9-124">The module identifier.</span></span>|  
|<span data-ttu-id="c09f9-125">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="c09f9-125">StubMethodID</span></span>|<span data-ttu-id="c09f9-126">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c09f9-126">win:UInt64</span></span>|<span data-ttu-id="c09f9-127">스텁 메서드 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="c09f9-127">The stub method identifier.</span></span>|  
|<span data-ttu-id="c09f9-128">StubFlags</span><span class="sxs-lookup"><span data-stu-id="c09f9-128">StubFlags</span></span>|<span data-ttu-id="c09f9-129">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c09f9-129">win:UInt64</span></span>|<span data-ttu-id="c09f9-130">스텁에 대한 플래그:</span><span class="sxs-lookup"><span data-stu-id="c09f9-130">The flags for the stub:</span></span><br /><br /> <span data-ttu-id="c09f9-131">0x1 - 역방향 interop</span><span class="sxs-lookup"><span data-stu-id="c09f9-131">0x1 - Reverse interop.</span></span><br /><br /> <span data-ttu-id="c09f9-132">0x2 - COM interop</span><span class="sxs-lookup"><span data-stu-id="c09f9-132">0x2 - COM interop.</span></span><br /><br /> <span data-ttu-id="c09f9-133">0x4 - NGen.exe에서 생성한 스텁</span><span class="sxs-lookup"><span data-stu-id="c09f9-133">0x4 - Stub generated by NGen.exe.</span></span><br /><br /> <span data-ttu-id="c09f9-134">0x8 - 대리자</span><span class="sxs-lookup"><span data-stu-id="c09f9-134">0x8 - Delegate.</span></span><br /><br /> <span data-ttu-id="c09f9-135">0x10-변수 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="c09f9-135">0x10 - Variable argument.</span></span><br /><br /> <span data-ttu-id="c09f9-136">0x20 - 비관리 호출 수신자</span><span class="sxs-lookup"><span data-stu-id="c09f9-136">0x20 - Unmanaged callee.</span></span>|  
|<span data-ttu-id="c09f9-137">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="c09f9-137">ManagedInteropMethodToken</span></span>|<span data-ttu-id="c09f9-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c09f9-138">win:UInt32</span></span>|<span data-ttu-id="c09f9-139">관리되는 interop 메서드의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="c09f9-139">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="c09f9-140">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="c09f9-140">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="c09f9-141">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="c09f9-141">win:UnicodeString</span></span>|<span data-ttu-id="c09f9-142">관리되는 interop 메서드의 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c09f9-142">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="c09f9-143">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="c09f9-143">ManagedInteropMethodName</span></span>|<span data-ttu-id="c09f9-144">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="c09f9-144">win:UnicodeString</span></span>|<span data-ttu-id="c09f9-145">관리되는 interop 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c09f9-145">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="c09f9-146">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="c09f9-146">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="c09f9-147">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="c09f9-147">win:UnicodeString</span></span>|<span data-ttu-id="c09f9-148">관리되는 interop 메서드의 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="c09f9-148">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="c09f9-149">NativeMethodSignature</span><span class="sxs-lookup"><span data-stu-id="c09f9-149">NativeMethodSignature</span></span>|<span data-ttu-id="c09f9-150">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="c09f9-150">win:UnicodeString</span></span>|<span data-ttu-id="c09f9-151">네이티브 메서드 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="c09f9-151">The native method signature.</span></span>|  
|<span data-ttu-id="c09f9-152">StubMethodSignature</span><span class="sxs-lookup"><span data-stu-id="c09f9-152">StubMethodSignature</span></span>|<span data-ttu-id="c09f9-153">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="c09f9-153">win:UnicodeString</span></span>|<span data-ttu-id="c09f9-154">스텁 메서드 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="c09f9-154">The stub method signature.</span></span>|  
|<span data-ttu-id="c09f9-155">StubMethodILCode</span><span class="sxs-lookup"><span data-stu-id="c09f9-155">StubMethodILCode</span></span>|<span data-ttu-id="c09f9-156">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="c09f9-156">win:UnicodeString</span></span>|<span data-ttu-id="c09f9-157">스텁 메서드의 MSIL 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c09f9-157">The MSIL code for the stub method.</span></span>|  
|<span data-ttu-id="c09f9-158">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c09f9-158">ClrInstanceID</span></span>|<span data-ttu-id="c09f9-159">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c09f9-159">win:UInt16</span></span>|<span data-ttu-id="c09f9-160">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c09f9-160">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="ilstubcachehit-event"></a><span data-ttu-id="c09f9-161">ILStubCacheHit 이벤트</span><span class="sxs-lookup"><span data-stu-id="c09f9-161">ILStubCacheHit Event</span></span>  

<span data-ttu-id="c09f9-162">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c09f9-162">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="c09f9-163">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="c09f9-163">Keyword for raising the event</span></span>|<span data-ttu-id="c09f9-164">Level</span><span class="sxs-lookup"><span data-stu-id="c09f9-164">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="c09f9-165">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="c09f9-165">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="c09f9-166">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="c09f9-166">Informational(4)</span></span>|  
  
 <span data-ttu-id="c09f9-167">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c09f9-167">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c09f9-168">이벤트</span><span class="sxs-lookup"><span data-stu-id="c09f9-168">Event</span></span>|<span data-ttu-id="c09f9-169">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c09f9-169">Event ID</span></span>|<span data-ttu-id="c09f9-170">발생 시기</span><span class="sxs-lookup"><span data-stu-id="c09f9-170">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|<span data-ttu-id="c09f9-171">89</span><span class="sxs-lookup"><span data-stu-id="c09f9-171">89</span></span>|<span data-ttu-id="c09f9-172">MSIL 캐시가 액세스되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c09f9-172">The MSIL cache has been accessed.</span></span>|  
  
 <span data-ttu-id="c09f9-173">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c09f9-173">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="c09f9-174">필드 이름</span><span class="sxs-lookup"><span data-stu-id="c09f9-174">Field name</span></span>|<span data-ttu-id="c09f9-175">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c09f9-175">Data type</span></span>|<span data-ttu-id="c09f9-176">Description</span><span class="sxs-lookup"><span data-stu-id="c09f9-176">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c09f9-177">ModuleID</span><span class="sxs-lookup"><span data-stu-id="c09f9-177">ModuleID</span></span>|<span data-ttu-id="c09f9-178">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c09f9-178">win:UInt16</span></span>|<span data-ttu-id="c09f9-179">모듈 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="c09f9-179">The module identifier.</span></span>|  
|<span data-ttu-id="c09f9-180">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="c09f9-180">StubMethodID</span></span>|<span data-ttu-id="c09f9-181">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c09f9-181">win:UInt64</span></span>|<span data-ttu-id="c09f9-182">스텁 메서드 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="c09f9-182">The stub method identifier.</span></span>|  
|<span data-ttu-id="c09f9-183">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="c09f9-183">ManagedInteropMethodToken</span></span>|<span data-ttu-id="c09f9-184">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c09f9-184">win:UInt32</span></span>|<span data-ttu-id="c09f9-185">관리되는 interop 메서드의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="c09f9-185">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="c09f9-186">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="c09f9-186">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="c09f9-187">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="c09f9-187">win:UnicodeString</span></span>|<span data-ttu-id="c09f9-188">관리되는 interop 메서드의 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c09f9-188">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="c09f9-189">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="c09f9-189">ManagedInteropMethodName</span></span>|<span data-ttu-id="c09f9-190">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="c09f9-190">win:UnicodeString</span></span>|<span data-ttu-id="c09f9-191">관리되는 interop 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c09f9-191">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="c09f9-192">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="c09f9-192">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="c09f9-193">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="c09f9-193">win:UnicodeString</span></span>|<span data-ttu-id="c09f9-194">관리되는 interop 메서드의 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="c09f9-194">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="c09f9-195">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c09f9-195">ClrInstanceID</span></span>|<span data-ttu-id="c09f9-196">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c09f9-196">win:UInt16</span></span>|<span data-ttu-id="c09f9-197">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c09f9-197">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c09f9-198">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c09f9-198">See also</span></span>

- [<span data-ttu-id="c09f9-199">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="c09f9-199">CLR ETW Events</span></span>](clr-etw-events.md)
