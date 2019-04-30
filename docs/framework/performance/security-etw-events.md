---
title: 보안 ETW 이벤트
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11a19dce496423883e5fed62375c6db8ed5efdb1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949203"
---
# <a name="security-etw-events"></a><span data-ttu-id="f73bb-102">보안 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="f73bb-102">Security ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="f73bb-103">보안 이벤트는 강력한 이름 확인 및 Authenticode 확인 중에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f73bb-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  
  
 <span data-ttu-id="f73bb-104">이 범주는 다음 이벤트로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f73bb-104">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="f73bb-105">StrongNameVerificationStart_V1 및 StrongNameVerificationStop_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="f73bb-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
- [<span data-ttu-id="f73bb-106">AuthenticodeVerificationStart_V1 및 AuthenticodeVerificationStop_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="f73bb-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstartv1-and-strongnameverificationstopv1-events"></a><span data-ttu-id="f73bb-107">StrongNameVerificationStart_V1 및 StrongNameVerificationStop_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="f73bb-107">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="f73bb-108">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f73bb-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="f73bb-109">자세한 내용은 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f73bb-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="f73bb-110">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="f73bb-110">Keyword for raising the event</span></span>|<span data-ttu-id="f73bb-111">수준</span><span class="sxs-lookup"><span data-stu-id="f73bb-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f73bb-112">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="f73bb-112">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="f73bb-113">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="f73bb-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="f73bb-114">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f73bb-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f73bb-115">이벤트</span><span class="sxs-lookup"><span data-stu-id="f73bb-115">Event</span></span>|<span data-ttu-id="f73bb-116">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="f73bb-116">Event ID</span></span>|<span data-ttu-id="f73bb-117">발생 시기</span><span class="sxs-lookup"><span data-stu-id="f73bb-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="f73bb-118">181</span><span class="sxs-lookup"><span data-stu-id="f73bb-118">181</span></span>|<span data-ttu-id="f73bb-119">강력한 이름 확인의 시작입니다.</span><span class="sxs-lookup"><span data-stu-id="f73bb-119">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="f73bb-120">182</span><span class="sxs-lookup"><span data-stu-id="f73bb-120">182</span></span>|<span data-ttu-id="f73bb-121">강력한 이름 확인의 끝입니다.</span><span class="sxs-lookup"><span data-stu-id="f73bb-121">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="f73bb-122">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f73bb-122">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="f73bb-123">필드 이름</span><span class="sxs-lookup"><span data-stu-id="f73bb-123">Field name</span></span>|<span data-ttu-id="f73bb-124">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="f73bb-124">Data type</span></span>|<span data-ttu-id="f73bb-125">설명</span><span class="sxs-lookup"><span data-stu-id="f73bb-125">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f73bb-126">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="f73bb-126">VerificationFlags</span></span>|<span data-ttu-id="f73bb-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f73bb-127">win:UInt32</span></span>|<span data-ttu-id="f73bb-128">확인 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="f73bb-128">The verification flags.</span></span>|  
|<span data-ttu-id="f73bb-129">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="f73bb-129">ErrorCode</span></span>|<span data-ttu-id="f73bb-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f73bb-130">win:UInt32</span></span>|<span data-ttu-id="f73bb-131">HResult 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="f73bb-131">The HResult error code.</span></span>|  
|<span data-ttu-id="f73bb-132">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="f73bb-132">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="f73bb-133">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="f73bb-133">win:UnicodeString</span></span>|<span data-ttu-id="f73bb-134">정규화된 어셈블리 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f73bb-134">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="f73bb-135">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f73bb-135">ClrInstanceID</span></span>|<span data-ttu-id="f73bb-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f73bb-136">win:UInt16</span></span>|<span data-ttu-id="f73bb-137">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f73bb-137">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="f73bb-138">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="f73bb-138">Back to top</span></span>](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstartv1-and-authenticodeverificationstopv1-events"></a><span data-ttu-id="f73bb-139">AuthenticodeVerificationStart_V1 및 AuthenticodeVerificationStop_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="f73bb-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="f73bb-140">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f73bb-140">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="f73bb-141">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="f73bb-141">Keyword for raising the event</span></span>|<span data-ttu-id="f73bb-142">수준</span><span class="sxs-lookup"><span data-stu-id="f73bb-142">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f73bb-143">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="f73bb-143">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="f73bb-144">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="f73bb-144">Informational(4)</span></span>|  
  
 <span data-ttu-id="f73bb-145">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f73bb-145">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f73bb-146">이벤트</span><span class="sxs-lookup"><span data-stu-id="f73bb-146">Event</span></span>|<span data-ttu-id="f73bb-147">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="f73bb-147">Event ID</span></span>|<span data-ttu-id="f73bb-148">발생 시기</span><span class="sxs-lookup"><span data-stu-id="f73bb-148">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="f73bb-149">183</span><span class="sxs-lookup"><span data-stu-id="f73bb-149">183</span></span>|<span data-ttu-id="f73bb-150">Authenticode 확인의 시작입니다.</span><span class="sxs-lookup"><span data-stu-id="f73bb-150">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="f73bb-151">184</span><span class="sxs-lookup"><span data-stu-id="f73bb-151">184</span></span>|<span data-ttu-id="f73bb-152">Authenticode 확인의 끝입니다.</span><span class="sxs-lookup"><span data-stu-id="f73bb-152">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="f73bb-153">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f73bb-153">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="f73bb-154">필드 이름</span><span class="sxs-lookup"><span data-stu-id="f73bb-154">Field name</span></span>|<span data-ttu-id="f73bb-155">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="f73bb-155">Data type</span></span>|<span data-ttu-id="f73bb-156">설명</span><span class="sxs-lookup"><span data-stu-id="f73bb-156">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f73bb-157">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="f73bb-157">VerificationFlags</span></span>|<span data-ttu-id="f73bb-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f73bb-158">win:UInt32</span></span>|<span data-ttu-id="f73bb-159">확인 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="f73bb-159">The verification flags.</span></span>|  
|<span data-ttu-id="f73bb-160">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="f73bb-160">ErrorCode</span></span>|<span data-ttu-id="f73bb-161">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f73bb-161">win:UInt32</span></span>|<span data-ttu-id="f73bb-162">HResult 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="f73bb-162">The HResult error code.</span></span>|  
|<span data-ttu-id="f73bb-163">ModulePath</span><span class="sxs-lookup"><span data-stu-id="f73bb-163">ModulePath</span></span>|<span data-ttu-id="f73bb-164">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="f73bb-164">win:UnicodeString</span></span>|<span data-ttu-id="f73bb-165">모듈 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="f73bb-165">The module path.</span></span>|  
|<span data-ttu-id="f73bb-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f73bb-166">ClrInstanceID</span></span>|<span data-ttu-id="f73bb-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f73bb-167">win:UInt16</span></span>|<span data-ttu-id="f73bb-168">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f73bb-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f73bb-169">참고자료</span><span class="sxs-lookup"><span data-stu-id="f73bb-169">See also</span></span>

- [<span data-ttu-id="f73bb-170">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="f73bb-170">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
