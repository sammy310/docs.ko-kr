---
title: 보안 ETW 이벤트
description: .NET에서 강력한 이름 확인 및 Authenticode 확인 중에 발생 하는 보안 ETW 이벤트를 이해 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
ms.openlocfilehash: 2fd2d450223cd16a7791b8f6c67afe6bcb954eb3
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474217"
---
# <a name="security-etw-events"></a><span data-ttu-id="01af9-103">보안 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="01af9-103">Security ETW Events</span></span>

<span data-ttu-id="01af9-104">보안 이벤트는 강력한 이름 확인 및 Authenticode 확인 중에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="01af9-104">Security events are raised during strong name verification and Authenticode verification.</span></span>  

## <a name="strongnameverificationstart_v1-and-strongnameverificationstop_v1-events"></a><span data-ttu-id="01af9-105">StrongNameVerificationStart_V1 및 StrongNameVerificationStop_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="01af9-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="01af9-106">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="01af9-106">The following table shows the keyword and level.</span></span> <span data-ttu-id="01af9-107">자세한 내용은 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="01af9-107">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="01af9-108">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="01af9-108">Keyword for raising the event</span></span>|<span data-ttu-id="01af9-109">수준</span><span class="sxs-lookup"><span data-stu-id="01af9-109">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="01af9-110">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="01af9-110">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="01af9-111">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="01af9-111">Informational(4)</span></span>|  
  
 <span data-ttu-id="01af9-112">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="01af9-112">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="01af9-113">이벤트</span><span class="sxs-lookup"><span data-stu-id="01af9-113">Event</span></span>|<span data-ttu-id="01af9-114">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="01af9-114">Event ID</span></span>|<span data-ttu-id="01af9-115">발생 시기</span><span class="sxs-lookup"><span data-stu-id="01af9-115">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="01af9-116">181</span><span class="sxs-lookup"><span data-stu-id="01af9-116">181</span></span>|<span data-ttu-id="01af9-117">강력한 이름 확인의 시작입니다.</span><span class="sxs-lookup"><span data-stu-id="01af9-117">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="01af9-118">182</span><span class="sxs-lookup"><span data-stu-id="01af9-118">182</span></span>|<span data-ttu-id="01af9-119">강력한 이름 확인의 끝입니다.</span><span class="sxs-lookup"><span data-stu-id="01af9-119">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="01af9-120">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="01af9-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="01af9-121">필드 이름</span><span class="sxs-lookup"><span data-stu-id="01af9-121">Field name</span></span>|<span data-ttu-id="01af9-122">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="01af9-122">Data type</span></span>|<span data-ttu-id="01af9-123">Description</span><span class="sxs-lookup"><span data-stu-id="01af9-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="01af9-124">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="01af9-124">VerificationFlags</span></span>|<span data-ttu-id="01af9-125">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="01af9-125">win:UInt32</span></span>|<span data-ttu-id="01af9-126">확인 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="01af9-126">The verification flags.</span></span>|  
|<span data-ttu-id="01af9-127">오류 코드</span><span class="sxs-lookup"><span data-stu-id="01af9-127">ErrorCode</span></span>|<span data-ttu-id="01af9-128">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="01af9-128">win:UInt32</span></span>|<span data-ttu-id="01af9-129">HResult 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="01af9-129">The HResult error code.</span></span>|  
|<span data-ttu-id="01af9-130">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="01af9-130">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="01af9-131">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="01af9-131">win:UnicodeString</span></span>|<span data-ttu-id="01af9-132">정규화된 어셈블리 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="01af9-132">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="01af9-133">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="01af9-133">ClrInstanceID</span></span>|<span data-ttu-id="01af9-134">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="01af9-134">win:UInt16</span></span>|<span data-ttu-id="01af9-135">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="01af9-135">Unique ID for the instance of CLR or CoreCLR.</span></span>|  

## <a name="authenticodeverificationstart_v1-and-authenticodeverificationstop_v1-events"></a><span data-ttu-id="01af9-136">AuthenticodeVerificationStart_V1 및 AuthenticodeVerificationStop_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="01af9-136">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="01af9-137">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="01af9-137">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="01af9-138">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="01af9-138">Keyword for raising the event</span></span>|<span data-ttu-id="01af9-139">수준</span><span class="sxs-lookup"><span data-stu-id="01af9-139">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="01af9-140">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="01af9-140">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="01af9-141">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="01af9-141">Informational(4)</span></span>|  
  
 <span data-ttu-id="01af9-142">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="01af9-142">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="01af9-143">이벤트</span><span class="sxs-lookup"><span data-stu-id="01af9-143">Event</span></span>|<span data-ttu-id="01af9-144">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="01af9-144">Event ID</span></span>|<span data-ttu-id="01af9-145">발생 시기</span><span class="sxs-lookup"><span data-stu-id="01af9-145">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="01af9-146">183</span><span class="sxs-lookup"><span data-stu-id="01af9-146">183</span></span>|<span data-ttu-id="01af9-147">Authenticode 확인의 시작입니다.</span><span class="sxs-lookup"><span data-stu-id="01af9-147">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="01af9-148">184</span><span class="sxs-lookup"><span data-stu-id="01af9-148">184</span></span>|<span data-ttu-id="01af9-149">Authenticode 확인의 끝입니다.</span><span class="sxs-lookup"><span data-stu-id="01af9-149">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="01af9-150">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="01af9-150">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="01af9-151">필드 이름</span><span class="sxs-lookup"><span data-stu-id="01af9-151">Field name</span></span>|<span data-ttu-id="01af9-152">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="01af9-152">Data type</span></span>|<span data-ttu-id="01af9-153">Description</span><span class="sxs-lookup"><span data-stu-id="01af9-153">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="01af9-154">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="01af9-154">VerificationFlags</span></span>|<span data-ttu-id="01af9-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="01af9-155">win:UInt32</span></span>|<span data-ttu-id="01af9-156">확인 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="01af9-156">The verification flags.</span></span>|  
|<span data-ttu-id="01af9-157">오류 코드</span><span class="sxs-lookup"><span data-stu-id="01af9-157">ErrorCode</span></span>|<span data-ttu-id="01af9-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="01af9-158">win:UInt32</span></span>|<span data-ttu-id="01af9-159">HResult 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="01af9-159">The HResult error code.</span></span>|  
|<span data-ttu-id="01af9-160">ModulePath</span><span class="sxs-lookup"><span data-stu-id="01af9-160">ModulePath</span></span>|<span data-ttu-id="01af9-161">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="01af9-161">win:UnicodeString</span></span>|<span data-ttu-id="01af9-162">모듈 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="01af9-162">The module path.</span></span>|  
|<span data-ttu-id="01af9-163">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="01af9-163">ClrInstanceID</span></span>|<span data-ttu-id="01af9-164">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="01af9-164">win:UInt16</span></span>|<span data-ttu-id="01af9-165">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="01af9-165">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="01af9-166">참고 항목</span><span class="sxs-lookup"><span data-stu-id="01af9-166">See also</span></span>

- [<span data-ttu-id="01af9-167">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="01af9-167">CLR ETW Events</span></span>](clr-etw-events.md)
