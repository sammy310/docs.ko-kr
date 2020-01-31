---
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
ms.openlocfilehash: 2ed32449c4a133e6e72ec44f9cb57f49de22164a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778239"
---
# <a name="cordebugplatform-enumeration"></a><span data-ttu-id="896ea-102">CorDebugPlatform 열거형</span><span class="sxs-lookup"><span data-stu-id="896ea-102">CorDebugPlatform Enumeration</span></span>
<span data-ttu-id="896ea-103">[ICorDebugDataTarget:: GetPlatform](icordebugdatatarget-getplatform-method.md) 메서드에서 사용 하는 대상 플랫폼 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="896ea-103">Provides target platform values that are used by the [ICorDebugDataTarget::GetPlatform](icordebugdatatarget-getplatform-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="896ea-104">구문</span><span class="sxs-lookup"><span data-stu-id="896ea-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="896ea-105">Members</span><span class="sxs-lookup"><span data-stu-id="896ea-105">Members</span></span>  
  
|<span data-ttu-id="896ea-106">Member</span><span class="sxs-lookup"><span data-stu-id="896ea-106">Member</span></span>|<span data-ttu-id="896ea-107">설명</span><span class="sxs-lookup"><span data-stu-id="896ea-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="896ea-108">CORDB_PLATFORM_WINDOWS_X86</span><span class="sxs-lookup"><span data-stu-id="896ea-108">CORDB_PLATFORM_WINDOWS_X86</span></span>|<span data-ttu-id="896ea-109">대상 플랫폼이 Intel x86 하드웨어에서 실행되는 Windows입니다.</span><span class="sxs-lookup"><span data-stu-id="896ea-109">The target platform is Windows running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="896ea-110">CORDB_PLATFORM_WINDOWS_AMD64</span><span class="sxs-lookup"><span data-stu-id="896ea-110">CORDB_PLATFORM_WINDOWS_AMD64</span></span>|<span data-ttu-id="896ea-111">대상 플랫폼이 AMD64 또는 Intel EM64T 하드웨어에서 실행되는 64비트 Windows입니다.</span><span class="sxs-lookup"><span data-stu-id="896ea-111">The target platform is 64 bit Windows running on AMD64 or Intel EM64T hardware.</span></span>|  
|<span data-ttu-id="896ea-112">CORDB_PLATFORM_WINDOWS_IA64</span><span class="sxs-lookup"><span data-stu-id="896ea-112">CORDB_PLATFORM_WINDOWS_IA64</span></span>|<span data-ttu-id="896ea-113">대상 플랫폼이 Intel IA-64 하드웨어에서 실행되는 32비트 Windows입니다.</span><span class="sxs-lookup"><span data-stu-id="896ea-113">The target platform is 32 bit Windows running on Intel IA-64 hardware.</span></span>|  
|<span data-ttu-id="896ea-114">CORDB_PLATFORM_MAC_PPC</span><span class="sxs-lookup"><span data-stu-id="896ea-114">CORDB_PLATFORM_MAC_PPC</span></span>|<span data-ttu-id="896ea-115">대상 플랫폼은 PowerPC 하드웨어에서 실행 되는 Macintosh 운영 체제입니다.</span><span class="sxs-lookup"><span data-stu-id="896ea-115">The target platform is the Macintosh operating system running on PowerPC hardware.</span></span>|  
|<span data-ttu-id="896ea-116">CORDB_PLATFORM_MAC_X86</span><span class="sxs-lookup"><span data-stu-id="896ea-116">CORDB_PLATFORM_MAC_X86</span></span>|<span data-ttu-id="896ea-117">대상 플랫폼은 Intel x86 하드웨어에서 실행 되는 Macintosh 운영 체제입니다.</span><span class="sxs-lookup"><span data-stu-id="896ea-117">The target platform is the Macintosh operating system running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="896ea-118">CORDB_PLATFORM_WINDOWS_ARM</span><span class="sxs-lookup"><span data-stu-id="896ea-118">CORDB_PLATFORM_WINDOWS_ARM</span></span>|<span data-ttu-id="896ea-119">대상 플랫폼은 Windows ARM 하드웨어에서 실행 되는 Macintosh 운영 체제입니다.</span><span class="sxs-lookup"><span data-stu-id="896ea-119">The target platform is the Macintosh operating system running on Windows ARM hardware.</span></span>|  
|<span data-ttu-id="896ea-120">CORDB_PLATFORM_MAC_AMD64</span><span class="sxs-lookup"><span data-stu-id="896ea-120">CORDB_PLATFORM_MAC_AMD64</span></span>|<span data-ttu-id="896ea-121">대상 플랫폼은 AMD64 하드웨어에서 실행 되는 Macintosh 운영 체제입니다.</span><span class="sxs-lookup"><span data-stu-id="896ea-121">The target platform is the Macintosh operating system running on AMD64 hardware.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="896ea-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="896ea-122">Requirements</span></span>  
 <span data-ttu-id="896ea-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="896ea-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="896ea-124">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="896ea-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="896ea-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="896ea-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="896ea-126">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="896ea-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
 <span data-ttu-id="896ea-127">`CORDB_PLATFORM_WINDOWS_ARM` 및 `CORDB_PLATFORM_MAC_AMD64` 멤버는 .NET Framework 4.5.2 이상 버전에서 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="896ea-127">The `CORDB_PLATFORM_WINDOWS_ARM` and `CORDB_PLATFORM_MAC_AMD64` members are available in the .NET Framework 4.5.2 and later versions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="896ea-128">참조</span><span class="sxs-lookup"><span data-stu-id="896ea-128">See also</span></span>

- [<span data-ttu-id="896ea-129">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="896ea-129">Debugging Enumerations</span></span>](debugging-enumerations.md)
