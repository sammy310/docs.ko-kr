---
title: Interop ETW 이벤트
ms.date: 03/30/2017
helpviewer_keywords:
- interop events [.NET Framework]
- ETW, interop events (CLR)
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5db68cdce0db4f8f4d85e9d1dd03720bf235d865
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974927"
---
# <a name="interop-etw-events"></a><span data-ttu-id="ac6b3-102">Interop ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="ac6b3-102">Interop ETW Events</span></span>
<span data-ttu-id="ac6b3-103">Interop 이벤트는 MSIL(Microsoft Intermediate Language) 스텁 생성 및 캐싱에 대한 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b3-103">Interop events capture information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  

## <a name="ilstubgenerated-event"></a><span data-ttu-id="ac6b3-104">ILStubGenerated 이벤트</span><span class="sxs-lookup"><span data-stu-id="ac6b3-104">ILStubGenerated Event</span></span>

<span data-ttu-id="ac6b3-105">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b3-105">The following table shows the keyword and level.</span></span> <span data-ttu-id="ac6b3-106">자세한 내용은 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ac6b3-106">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="ac6b3-107">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="ac6b3-107">Keyword for raising the event</span></span>|<span data-ttu-id="ac6b3-108">Level</span><span class="sxs-lookup"><span data-stu-id="ac6b3-108">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ac6b3-109">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="ac6b3-109">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="ac6b3-110">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="ac6b3-110">Informational(4)</span></span>|  
  
 <span data-ttu-id="ac6b3-111">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b3-111">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="ac6b3-112">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="ac6b3-112">Event</span></span>|<span data-ttu-id="ac6b3-113">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="ac6b3-113">Event ID</span></span>|<span data-ttu-id="ac6b3-114">발생 시기</span><span class="sxs-lookup"><span data-stu-id="ac6b3-114">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|<span data-ttu-id="ac6b3-115">88</span><span class="sxs-lookup"><span data-stu-id="ac6b3-115">88</span></span>|<span data-ttu-id="ac6b3-116">MSIL 스텁이 생성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b3-116">The MSIL stub has been generated.</span></span>|  
  
 <span data-ttu-id="ac6b3-117">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b3-117">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="ac6b3-118">필드 이름</span><span class="sxs-lookup"><span data-stu-id="ac6b3-118">Field name</span></span>|<span data-ttu-id="ac6b3-119">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ac6b3-119">Data type</span></span>|<span data-ttu-id="ac6b3-120">설명</span><span class="sxs-lookup"><span data-stu-id="ac6b3-120">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="ac6b3-121">ModuleID</span><span class="sxs-lookup"><span data-stu-id="ac6b3-121">ModuleID</span></span>|<span data-ttu-id="ac6b3-122">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ac6b3-122">win:UInt16</span></span>|<span data-ttu-id="ac6b3-123">모듈 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b3-123">The module identifier.</span></span>|  
|<span data-ttu-id="ac6b3-124">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="ac6b3-124">StubMethodID</span></span>|<span data-ttu-id="ac6b3-125">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ac6b3-125">win:UInt64</span></span>|<span data-ttu-id="ac6b3-126">스텁 메서드 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b3-126">The stub method identifier.</span></span>|  
|<span data-ttu-id="ac6b3-127">StubFlags</span><span class="sxs-lookup"><span data-stu-id="ac6b3-127">StubFlags</span></span>|<span data-ttu-id="ac6b3-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ac6b3-128">win:UInt64</span></span>|<span data-ttu-id="ac6b3-129">스텁에 대한 플래그:</span><span class="sxs-lookup"><span data-stu-id="ac6b3-129">The flags for the stub:</span></span><br /><br /> <span data-ttu-id="ac6b3-130">0x1 - 역방향 interop</span><span class="sxs-lookup"><span data-stu-id="ac6b3-130">0x1 - Reverse interop.</span></span><br /><br /> <span data-ttu-id="ac6b3-131">0x2 - COM interop</span><span class="sxs-lookup"><span data-stu-id="ac6b3-131">0x2 - COM interop.</span></span><br /><br /> <span data-ttu-id="ac6b3-132">0x4 - NGen.exe에서 생성한 스텁</span><span class="sxs-lookup"><span data-stu-id="ac6b3-132">0x4 - Stub generated by NGen.exe.</span></span><br /><br /> <span data-ttu-id="ac6b3-133">0x8 - 대리자</span><span class="sxs-lookup"><span data-stu-id="ac6b3-133">0x8 - Delegate.</span></span><br /><br /> <span data-ttu-id="ac6b3-134">0x10-변수 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b3-134">0x10 - Variable argument.</span></span><br /><br /> <span data-ttu-id="ac6b3-135">0x20 - 비관리 호출 수신자</span><span class="sxs-lookup"><span data-stu-id="ac6b3-135">0x20 - Unmanaged callee.</span></span>|  
|<span data-ttu-id="ac6b3-136">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="ac6b3-136">ManagedInteropMethodToken</span></span>|<span data-ttu-id="ac6b3-137">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ac6b3-137">win:UInt32</span></span>|<span data-ttu-id="ac6b3-138">관리되는 interop 메서드의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b3-138">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="ac6b3-139">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="ac6b3-139">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="ac6b3-140">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="ac6b3-140">win:UnicodeString</span></span>|<span data-ttu-id="ac6b3-141">관리되는 interop 메서드의 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b3-141">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="ac6b3-142">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="ac6b3-142">ManagedInteropMethodName</span></span>|<span data-ttu-id="ac6b3-143">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="ac6b3-143">win:UnicodeString</span></span>|<span data-ttu-id="ac6b3-144">관리되는 interop 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b3-144">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="ac6b3-145">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="ac6b3-145">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="ac6b3-146">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="ac6b3-146">win:UnicodeString</span></span>|<span data-ttu-id="ac6b3-147">관리되는 interop 메서드의 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b3-147">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="ac6b3-148">NativeMethodSignature</span><span class="sxs-lookup"><span data-stu-id="ac6b3-148">NativeMethodSignature</span></span>|<span data-ttu-id="ac6b3-149">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="ac6b3-149">win:UnicodeString</span></span>|<span data-ttu-id="ac6b3-150">네이티브 메서드 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b3-150">The native method signature.</span></span>|  
|<span data-ttu-id="ac6b3-151">StubMethodSignature</span><span class="sxs-lookup"><span data-stu-id="ac6b3-151">StubMethodSignature</span></span>|<span data-ttu-id="ac6b3-152">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="ac6b3-152">win:UnicodeString</span></span>|<span data-ttu-id="ac6b3-153">스텁 메서드 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b3-153">The stub method signature.</span></span>|  
|<span data-ttu-id="ac6b3-154">StubMethodILCode</span><span class="sxs-lookup"><span data-stu-id="ac6b3-154">StubMethodILCode</span></span>|<span data-ttu-id="ac6b3-155">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="ac6b3-155">win:UnicodeString</span></span>|<span data-ttu-id="ac6b3-156">스텁 메서드의 MSIL 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b3-156">The MSIL code for the stub method.</span></span>|  
|<span data-ttu-id="ac6b3-157">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ac6b3-157">ClrInstanceID</span></span>|<span data-ttu-id="ac6b3-158">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ac6b3-158">win:UInt16</span></span>|<span data-ttu-id="ac6b3-159">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b3-159">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="ilstubcachehit-event"></a><span data-ttu-id="ac6b3-160">ILStubCacheHit 이벤트</span><span class="sxs-lookup"><span data-stu-id="ac6b3-160">ILStubCacheHit Event</span></span>  

<span data-ttu-id="ac6b3-161">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b3-161">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="ac6b3-162">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="ac6b3-162">Keyword for raising the event</span></span>|<span data-ttu-id="ac6b3-163">Level</span><span class="sxs-lookup"><span data-stu-id="ac6b3-163">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ac6b3-164">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="ac6b3-164">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="ac6b3-165">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="ac6b3-165">Informational(4)</span></span>|  
  
 <span data-ttu-id="ac6b3-166">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b3-166">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="ac6b3-167">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="ac6b3-167">Event</span></span>|<span data-ttu-id="ac6b3-168">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="ac6b3-168">Event ID</span></span>|<span data-ttu-id="ac6b3-169">발생 시기</span><span class="sxs-lookup"><span data-stu-id="ac6b3-169">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|<span data-ttu-id="ac6b3-170">89</span><span class="sxs-lookup"><span data-stu-id="ac6b3-170">89</span></span>|<span data-ttu-id="ac6b3-171">MSIL 캐시가 액세스되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b3-171">The MSIL cache has been accessed.</span></span>|  
  
 <span data-ttu-id="ac6b3-172">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b3-172">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="ac6b3-173">필드 이름</span><span class="sxs-lookup"><span data-stu-id="ac6b3-173">Field name</span></span>|<span data-ttu-id="ac6b3-174">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ac6b3-174">Data type</span></span>|<span data-ttu-id="ac6b3-175">설명</span><span class="sxs-lookup"><span data-stu-id="ac6b3-175">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="ac6b3-176">ModuleID</span><span class="sxs-lookup"><span data-stu-id="ac6b3-176">ModuleID</span></span>|<span data-ttu-id="ac6b3-177">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ac6b3-177">win:UInt16</span></span>|<span data-ttu-id="ac6b3-178">모듈 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b3-178">The module identifier.</span></span>|  
|<span data-ttu-id="ac6b3-179">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="ac6b3-179">StubMethodID</span></span>|<span data-ttu-id="ac6b3-180">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ac6b3-180">win:UInt64</span></span>|<span data-ttu-id="ac6b3-181">스텁 메서드 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b3-181">The stub method identifier.</span></span>|  
|<span data-ttu-id="ac6b3-182">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="ac6b3-182">ManagedInteropMethodToken</span></span>|<span data-ttu-id="ac6b3-183">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ac6b3-183">win:UInt32</span></span>|<span data-ttu-id="ac6b3-184">관리되는 interop 메서드의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b3-184">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="ac6b3-185">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="ac6b3-185">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="ac6b3-186">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="ac6b3-186">win:UnicodeString</span></span>|<span data-ttu-id="ac6b3-187">관리되는 interop 메서드의 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b3-187">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="ac6b3-188">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="ac6b3-188">ManagedInteropMethodName</span></span>|<span data-ttu-id="ac6b3-189">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="ac6b3-189">win:UnicodeString</span></span>|<span data-ttu-id="ac6b3-190">관리되는 interop 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b3-190">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="ac6b3-191">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="ac6b3-191">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="ac6b3-192">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="ac6b3-192">win:UnicodeString</span></span>|<span data-ttu-id="ac6b3-193">관리되는 interop 메서드의 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b3-193">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="ac6b3-194">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ac6b3-194">ClrInstanceID</span></span>|<span data-ttu-id="ac6b3-195">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ac6b3-195">win:UInt16</span></span>|<span data-ttu-id="ac6b3-196">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b3-196">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ac6b3-197">참조</span><span class="sxs-lookup"><span data-stu-id="ac6b3-197">See also</span></span>

- [<span data-ttu-id="ac6b3-198">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="ac6b3-198">CLR ETW Events</span></span>](clr-etw-events.md)
