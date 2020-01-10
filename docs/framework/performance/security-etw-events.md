---
title: 보안 ETW 이벤트
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
ms.openlocfilehash: c443bda8cdc2c6b32760e9dcba8b81a29d81660b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715933"
---
# <a name="security-etw-events"></a><span data-ttu-id="5140c-102">보안 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="5140c-102">Security ETW Events</span></span>

<span data-ttu-id="5140c-103">보안 이벤트는 강력한 이름 확인 및 Authenticode 확인 중에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="5140c-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  

## <a name="strongnameverificationstart_v1-and-strongnameverificationstop_v1-events"></a><span data-ttu-id="5140c-104">StrongNameVerificationStart_V1 및 StrongNameVerificationStop_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="5140c-104">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="5140c-105">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5140c-105">The following table shows the keyword and level.</span></span> <span data-ttu-id="5140c-106">자세한 내용은 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5140c-106">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="5140c-107">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="5140c-107">Keyword for raising the event</span></span>|<span data-ttu-id="5140c-108">수준</span><span class="sxs-lookup"><span data-stu-id="5140c-108">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="5140c-109">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="5140c-109">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="5140c-110">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="5140c-110">Informational(4)</span></span>|  
  
 <span data-ttu-id="5140c-111">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5140c-111">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="5140c-112">Event</span><span class="sxs-lookup"><span data-stu-id="5140c-112">Event</span></span>|<span data-ttu-id="5140c-113">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="5140c-113">Event ID</span></span>|<span data-ttu-id="5140c-114">발생 시기</span><span class="sxs-lookup"><span data-stu-id="5140c-114">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="5140c-115">181</span><span class="sxs-lookup"><span data-stu-id="5140c-115">181</span></span>|<span data-ttu-id="5140c-116">강력한 이름 확인의 시작입니다.</span><span class="sxs-lookup"><span data-stu-id="5140c-116">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="5140c-117">182</span><span class="sxs-lookup"><span data-stu-id="5140c-117">182</span></span>|<span data-ttu-id="5140c-118">강력한 이름 확인의 끝입니다.</span><span class="sxs-lookup"><span data-stu-id="5140c-118">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="5140c-119">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5140c-119">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="5140c-120">필드 이름</span><span class="sxs-lookup"><span data-stu-id="5140c-120">Field name</span></span>|<span data-ttu-id="5140c-121">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5140c-121">Data type</span></span>|<span data-ttu-id="5140c-122">설명</span><span class="sxs-lookup"><span data-stu-id="5140c-122">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="5140c-123">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="5140c-123">VerificationFlags</span></span>|<span data-ttu-id="5140c-124">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="5140c-124">win:UInt32</span></span>|<span data-ttu-id="5140c-125">확인 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="5140c-125">The verification flags.</span></span>|  
|<span data-ttu-id="5140c-126">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="5140c-126">ErrorCode</span></span>|<span data-ttu-id="5140c-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="5140c-127">win:UInt32</span></span>|<span data-ttu-id="5140c-128">HResult 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="5140c-128">The HResult error code.</span></span>|  
|<span data-ttu-id="5140c-129">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="5140c-129">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="5140c-130">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="5140c-130">win:UnicodeString</span></span>|<span data-ttu-id="5140c-131">정규화된 어셈블리 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5140c-131">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="5140c-132">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="5140c-132">ClrInstanceID</span></span>|<span data-ttu-id="5140c-133">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="5140c-133">win:UInt16</span></span>|<span data-ttu-id="5140c-134">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5140c-134">Unique ID for the instance of CLR or CoreCLR.</span></span>|  

## <a name="authenticodeverificationstart_v1-and-authenticodeverificationstop_v1-events"></a><span data-ttu-id="5140c-135">AuthenticodeVerificationStart_V1 및 AuthenticodeVerificationStop_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="5140c-135">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="5140c-136">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5140c-136">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="5140c-137">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="5140c-137">Keyword for raising the event</span></span>|<span data-ttu-id="5140c-138">수준</span><span class="sxs-lookup"><span data-stu-id="5140c-138">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="5140c-139">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="5140c-139">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="5140c-140">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="5140c-140">Informational(4)</span></span>|  
  
 <span data-ttu-id="5140c-141">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5140c-141">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="5140c-142">Event</span><span class="sxs-lookup"><span data-stu-id="5140c-142">Event</span></span>|<span data-ttu-id="5140c-143">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="5140c-143">Event ID</span></span>|<span data-ttu-id="5140c-144">발생 시기</span><span class="sxs-lookup"><span data-stu-id="5140c-144">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="5140c-145">183</span><span class="sxs-lookup"><span data-stu-id="5140c-145">183</span></span>|<span data-ttu-id="5140c-146">Authenticode 확인의 시작입니다.</span><span class="sxs-lookup"><span data-stu-id="5140c-146">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="5140c-147">184</span><span class="sxs-lookup"><span data-stu-id="5140c-147">184</span></span>|<span data-ttu-id="5140c-148">Authenticode 확인의 끝입니다.</span><span class="sxs-lookup"><span data-stu-id="5140c-148">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="5140c-149">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5140c-149">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="5140c-150">필드 이름</span><span class="sxs-lookup"><span data-stu-id="5140c-150">Field name</span></span>|<span data-ttu-id="5140c-151">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5140c-151">Data type</span></span>|<span data-ttu-id="5140c-152">설명</span><span class="sxs-lookup"><span data-stu-id="5140c-152">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="5140c-153">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="5140c-153">VerificationFlags</span></span>|<span data-ttu-id="5140c-154">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="5140c-154">win:UInt32</span></span>|<span data-ttu-id="5140c-155">확인 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="5140c-155">The verification flags.</span></span>|  
|<span data-ttu-id="5140c-156">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="5140c-156">ErrorCode</span></span>|<span data-ttu-id="5140c-157">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="5140c-157">win:UInt32</span></span>|<span data-ttu-id="5140c-158">HResult 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="5140c-158">The HResult error code.</span></span>|  
|<span data-ttu-id="5140c-159">ModulePath</span><span class="sxs-lookup"><span data-stu-id="5140c-159">ModulePath</span></span>|<span data-ttu-id="5140c-160">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="5140c-160">win:UnicodeString</span></span>|<span data-ttu-id="5140c-161">모듈 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="5140c-161">The module path.</span></span>|  
|<span data-ttu-id="5140c-162">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="5140c-162">ClrInstanceID</span></span>|<span data-ttu-id="5140c-163">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="5140c-163">win:UInt16</span></span>|<span data-ttu-id="5140c-164">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5140c-164">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5140c-165">참조</span><span class="sxs-lookup"><span data-stu-id="5140c-165">See also</span></span>

- [<span data-ttu-id="5140c-166">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="5140c-166">CLR ETW Events</span></span>](clr-etw-events.md)
