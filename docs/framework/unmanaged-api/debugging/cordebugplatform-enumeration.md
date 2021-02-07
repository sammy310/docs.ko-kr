---
description: '다음에 대 한 자세한 정보: CorDebugPlatform 열거형'
title: CorDebugPlatform 열거형
ms.date: 03/30/2017
api_name:
- CorDebugPlatformEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugPlatformEnum
helpviewer_keywords:
- CorDebugPlatformEnum enumeration [.NET Framework debugging]
ms.assetid: c5444816-7378-4521-afd3-bf5e4b5303d5
topic_type:
- apiref
ms.openlocfilehash: d6a78ec00f99ff34158f784e039372c8937e6d16
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661859"
---
# <a name="cordebugplatform-enumeration"></a><span data-ttu-id="e2400-103">CorDebugPlatform 열거형</span><span class="sxs-lookup"><span data-stu-id="e2400-103">CorDebugPlatform Enumeration</span></span>

<span data-ttu-id="e2400-104">[ICorDebugDataTarget:: GetPlatform](icordebugdatatarget-getplatform-method.md) 메서드에서 사용 하는 대상 플랫폼 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2400-104">Provides target platform values that are used by the [ICorDebugDataTarget::GetPlatform](icordebugdatatarget-getplatform-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2400-105">구문</span><span class="sxs-lookup"><span data-stu-id="e2400-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugPlatform  
{  
    CORDB_PLATFORM_WINDOWS_X86,    // Windows on Intel x86  
    CORDB_PLATFORM_WINDOWS_AMD64,  // Windows x64 (AMD64, Intel EM64T)  
    CORDB_PLATFORM_WINDOWS_IA64,   // Windows on Intel IA-64  
    CORDB_PLATFORM_MAC_PPC,        // Macintosh OS on PowerPC  
    CORDB_PLATFORM_MAC_X86,        // Macintosh OS on Intel x86  
    CORDB_PLATFORM_WINDOWS_ARM,    // Windows on ARM  
    CORDB_PLATFORM_MAC_AMD64       // MacOS on Intel x64  
} CorDebugPlatform;  
```  
  
## <a name="members"></a><span data-ttu-id="e2400-106">구성원</span><span class="sxs-lookup"><span data-stu-id="e2400-106">Members</span></span>  
  
|<span data-ttu-id="e2400-107">멤버</span><span class="sxs-lookup"><span data-stu-id="e2400-107">Member</span></span>|<span data-ttu-id="e2400-108">설명</span><span class="sxs-lookup"><span data-stu-id="e2400-108">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e2400-109">CORDB_PLATFORM_WINDOWS_X86</span><span class="sxs-lookup"><span data-stu-id="e2400-109">CORDB_PLATFORM_WINDOWS_X86</span></span>|<span data-ttu-id="e2400-110">대상 플랫폼이 Intel x86 하드웨어에서 실행되는 Windows입니다.</span><span class="sxs-lookup"><span data-stu-id="e2400-110">The target platform is Windows running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="e2400-111">CORDB_PLATFORM_WINDOWS_AMD64</span><span class="sxs-lookup"><span data-stu-id="e2400-111">CORDB_PLATFORM_WINDOWS_AMD64</span></span>|<span data-ttu-id="e2400-112">대상 플랫폼이 AMD64 또는 Intel EM64T 하드웨어에서 실행되는 64비트 Windows입니다.</span><span class="sxs-lookup"><span data-stu-id="e2400-112">The target platform is 64 bit Windows running on AMD64 or Intel EM64T hardware.</span></span>|  
|<span data-ttu-id="e2400-113">CORDB_PLATFORM_WINDOWS_IA64</span><span class="sxs-lookup"><span data-stu-id="e2400-113">CORDB_PLATFORM_WINDOWS_IA64</span></span>|<span data-ttu-id="e2400-114">대상 플랫폼이 Intel IA-64 하드웨어에서 실행되는 32비트 Windows입니다.</span><span class="sxs-lookup"><span data-stu-id="e2400-114">The target platform is 32 bit Windows running on Intel IA-64 hardware.</span></span>|  
|<span data-ttu-id="e2400-115">CORDB_PLATFORM_MAC_PPC</span><span class="sxs-lookup"><span data-stu-id="e2400-115">CORDB_PLATFORM_MAC_PPC</span></span>|<span data-ttu-id="e2400-116">대상 플랫폼은 PowerPC 하드웨어에서 실행 되는 Macintosh 운영 체제입니다.</span><span class="sxs-lookup"><span data-stu-id="e2400-116">The target platform is the Macintosh operating system running on PowerPC hardware.</span></span>|  
|<span data-ttu-id="e2400-117">CORDB_PLATFORM_MAC_X86</span><span class="sxs-lookup"><span data-stu-id="e2400-117">CORDB_PLATFORM_MAC_X86</span></span>|<span data-ttu-id="e2400-118">대상 플랫폼은 Intel x86 하드웨어에서 실행 되는 Macintosh 운영 체제입니다.</span><span class="sxs-lookup"><span data-stu-id="e2400-118">The target platform is the Macintosh operating system running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="e2400-119">CORDB_PLATFORM_WINDOWS_ARM</span><span class="sxs-lookup"><span data-stu-id="e2400-119">CORDB_PLATFORM_WINDOWS_ARM</span></span>|<span data-ttu-id="e2400-120">대상 플랫폼은 Windows ARM 하드웨어에서 실행 되는 Macintosh 운영 체제입니다.</span><span class="sxs-lookup"><span data-stu-id="e2400-120">The target platform is the Macintosh operating system running on Windows ARM hardware.</span></span>|  
|<span data-ttu-id="e2400-121">CORDB_PLATFORM_MAC_AMD64</span><span class="sxs-lookup"><span data-stu-id="e2400-121">CORDB_PLATFORM_MAC_AMD64</span></span>|<span data-ttu-id="e2400-122">대상 플랫폼은 AMD64 하드웨어에서 실행 되는 Macintosh 운영 체제입니다.</span><span class="sxs-lookup"><span data-stu-id="e2400-122">The target platform is the Macintosh operating system running on AMD64 hardware.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e2400-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e2400-123">Requirements</span></span>  

 <span data-ttu-id="e2400-124">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2400-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2400-125">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2400-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2400-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2400-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2400-127">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2400-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
 <span data-ttu-id="e2400-128">`CORDB_PLATFORM_WINDOWS_ARM` 및 `CORDB_PLATFORM_MAC_AMD64` 멤버는 .NET Framework 4.5.2 이상 버전에서 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="e2400-128">The `CORDB_PLATFORM_WINDOWS_ARM` and `CORDB_PLATFORM_MAC_AMD64` members are available in the .NET Framework 4.5.2 and later versions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2400-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e2400-129">See also</span></span>

- [<span data-ttu-id="e2400-130">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="e2400-130">Debugging Enumerations</span></span>](debugging-enumerations.md)
