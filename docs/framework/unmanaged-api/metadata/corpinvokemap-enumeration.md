---
title: CorPinvokeMap 열거형
ms.date: 03/30/2017
api_name:
- CorPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPinvokeMap
helpviewer_keywords:
- CorPinvokeMap enumeration [.NET Framework metadata]
ms.assetid: f14f986e-f6ce-42bc-aa23-18150c46d28c
topic_type:
- apiref
ms.openlocfilehash: 8216dc3030b18428ab52fbf8385d392f81057aa0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176151"
---
# <a name="corpinvokemap-enumeration"></a><span data-ttu-id="f83ca-102">CorPinvokeMap 열거형</span><span class="sxs-lookup"><span data-stu-id="f83ca-102">CorPinvokeMap Enumeration</span></span>
<span data-ttu-id="f83ca-103">PInvoke 호출에 대한 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f83ca-103">Specifies options for a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f83ca-104">구문</span><span class="sxs-lookup"><span data-stu-id="f83ca-104">Syntax</span></span>  
  
```cpp  
typedef enum  CorPinvokeMap {  
  
    pmNoMangle          = 0x0001,  
  
    pmCharSetMask       = 0x0006,  
    pmCharSetNotSpec    = 0x0000,  
    pmCharSetAnsi       = 0x0002,  
    pmCharSetUnicode    = 0x0004,  
    pmCharSetAuto       = 0x0006,  
  
    pmBestFitUseAssem   = 0x0000,  
    pmBestFitEnabled    = 0x0010,  
    pmBestFitDisabled   = 0x0020,  
    pmBestFitMask       = 0x0030,  
  
    pmThrowOnUnmappableCharUseAssem   = 0x0000,  
    pmThrowOnUnmappableCharEnabled    = 0x1000,  
    pmThrowOnUnmappableCharDisabled   = 0x2000,  
    pmThrowOnUnmappableCharMask       = 0x3000,  
  
    pmSupportsLastError = 0x0040,
  
    pmCallConvMask      = 0x0700,  
    pmCallConvWinapi    = 0x0100,  
    pmCallConvCdecl     = 0x0200,  
    pmCallConvStdcall   = 0x0300,  
    pmCallConvThiscall  = 0x0400,  
    pmCallConvFastcall  = 0x0500,  
  
    pmMaxValue          = 0xFFFF  
  
} CorPinvokeMap;  
```  
  
## <a name="members"></a><span data-ttu-id="f83ca-105">구성원</span><span class="sxs-lookup"><span data-stu-id="f83ca-105">Members</span></span>  
  
|<span data-ttu-id="f83ca-106">멤버</span><span class="sxs-lookup"><span data-stu-id="f83ca-106">Member</span></span>|<span data-ttu-id="f83ca-107">Description</span><span class="sxs-lookup"><span data-stu-id="f83ca-107">Description</span></span>|  
|------------|-----------------|  
|`pmNoMangle`|<span data-ttu-id="f83ca-108">지정된 대로 각 멤버 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f83ca-108">Use each member name as specified.</span></span>|  
|`pmCharSetMask`|<span data-ttu-id="f83ca-109">예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f83ca-109">Reserved.</span></span>|  
|`pmCharSetNotSpec`|<span data-ttu-id="f83ca-110">예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f83ca-110">Reserved.</span></span>|  
|`pmCharSetAnsi`|<span data-ttu-id="f83ca-111">문자열을 다중 바이트 문자열로 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="f83ca-111">Marshal strings as multiple-byte character strings.</span></span>|  
|`pmCharSetUnicode`|<span data-ttu-id="f83ca-112">문자열을 유니코드 2바이트 문자로 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="f83ca-112">Marshal strings as Unicode 2-byte characters.</span></span>|  
|`pmCharSetAuto`|<span data-ttu-id="f83ca-113">문자열을 대상 운영 체제에 맞게 자동으로 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="f83ca-113">Automatically marshal strings appropriately for the target operating system.</span></span> <span data-ttu-id="f83ca-114">기본값은 Windows NT, Windows 2000, Windows XP 및 Windows Server 2003 제품군의 유니코드입니다. 기본값은 윈도우 98 및 윈도우 나에 ANSI입니다.</span><span class="sxs-lookup"><span data-stu-id="f83ca-114">The default is Unicode on Windows NT, Windows 2000, Windows XP, and the Windows Server 2003 family; the default is ANSI on Windows 98 and Windows Me.</span></span>|  
|`pmBestFitUseAssem`|<span data-ttu-id="f83ca-115">예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f83ca-115">Reserved.</span></span>|  
|`pmBestFitEnabled`|<span data-ttu-id="f83ca-116">ANSI 문자 집합에서 정확히 일치하지 않는 유니코드 문자의 최적 매핑을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f83ca-116">Perform best-fit mapping of Unicode characters that lack an exact match in the ANSI character set.</span></span>|  
|`pmBestFitDisabled`|<span data-ttu-id="f83ca-117">유니코드 문자의 최적 매핑을 수행하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="f83ca-117">Do not perform best-fit mapping of Unicode characters.</span></span> <span data-ttu-id="f83ca-118">이 경우, 모든 마플럼할 수 없는 문자는 '?'로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="f83ca-118">In this case, all unmappable characters will be replaced by a ‘?’.</span></span>|  
|`pmBestFitMask`|<span data-ttu-id="f83ca-119">예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f83ca-119">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharUseAssem`|<span data-ttu-id="f83ca-120">예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f83ca-120">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharEnabled`|<span data-ttu-id="f83ca-121">인터옵 마샬러가 마플수 없는 캐릭터를 만났을 때 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="f83ca-121">Throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharDisabled`|<span data-ttu-id="f83ca-122">인터롭 마샬러가 마플수 없는 캐릭터를 만났을 때 예외를 던지지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="f83ca-122">Do not throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharMask`|<span data-ttu-id="f83ca-123">Reserved</span><span class="sxs-lookup"><span data-stu-id="f83ca-123">Reserved</span></span>|  
|`pmSupportsLastError`|<span data-ttu-id="f83ca-124">어트리뷰션된 메서드에서 반환하기 전에 호출 한 호출이 Win32 `SetLastError` 함수를 호출할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="f83ca-124">Allow the callee to call the Win32 `SetLastError` function before returning from the attributed method.</span></span>|  
|`pmCallConvMask`|<span data-ttu-id="f83ca-125">Reserved</span><span class="sxs-lookup"><span data-stu-id="f83ca-125">Reserved</span></span>|  
|`pmCallConvWinapi`|<span data-ttu-id="f83ca-126">기본 플랫폼 호출 규칙을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f83ca-126">Use the default platform calling convention.</span></span> <span data-ttu-id="f83ca-127">예를 들어 Windows에서 기본값은 `StdCall` Windows CE .NET입니다. `Cdecl`</span><span class="sxs-lookup"><span data-stu-id="f83ca-127">For example, on Windows the default is `StdCall` and on Windows CE .NET it is `Cdecl`.</span></span>|  
|`pmCallConvCdecl`|<span data-ttu-id="f83ca-128">`Cdecl` 호출 규칙을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f83ca-128">Use the `Cdecl` calling convention.</span></span> <span data-ttu-id="f83ca-129">이 경우 호출자는 스택을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="f83ca-129">In this case, the caller cleans the stack.</span></span> <span data-ttu-id="f83ca-130">이렇게 하면 호출 `varargs` 함수(즉, 변수 수의 매개 변수를 허용하는 함수)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f83ca-130">This enables calling functions with `varargs` (that is, functions that accept a variable number of parameters).</span></span>|  
|`pmCallConvStdcall`|<span data-ttu-id="f83ca-131">`StdCall` 호출 규칙을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f83ca-131">Use the `StdCall` calling convention.</span></span> <span data-ttu-id="f83ca-132">이 경우 캘리클은 스택을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="f83ca-132">In this case, the callee cleans the stack.</span></span> <span data-ttu-id="f83ca-133">이는 플랫폼 호출을 사용하여 관리되지 않는 함수를 호출하는 기본 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="f83ca-133">This is the default convention for calling unmanaged functions with platform invoke.</span></span>|  
|`pmCallConvThiscall`|<span data-ttu-id="f83ca-134">`ThisCall` 호출 규칙을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f83ca-134">Use the `ThisCall` calling convention.</span></span> <span data-ttu-id="f83ca-135">이 경우 첫 번째 매개 `this` 변수는 포인터이며 레지스터 ECX에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f83ca-135">In this case, the first parameter is the `this` pointer and is stored in register ECX.</span></span> <span data-ttu-id="f83ca-136">다른 매개 변수는 스택에 푸시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f83ca-136">Other parameters are pushed on the stack.</span></span> <span data-ttu-id="f83ca-137">`ThisCall` 호출 규칙은 관리되지 않는 DLL에서 내보낸 클래스의 메서드를 호출하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f83ca-137">The `ThisCall` calling convention is used to call methods on classes exported from an unmanaged DLL.</span></span>|  
|`pmCallConvFastcall`|<span data-ttu-id="f83ca-138">예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f83ca-138">Reserved.</span></span>|  
|`pmMaxValue`|<span data-ttu-id="f83ca-139">예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f83ca-139">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f83ca-140">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f83ca-140">Requirements</span></span>  
 <span data-ttu-id="f83ca-141">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f83ca-141">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f83ca-142">**헤더:** 코르Hdr.h</span><span class="sxs-lookup"><span data-stu-id="f83ca-142">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f83ca-143">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f83ca-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f83ca-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f83ca-144">See also</span></span>

- [<span data-ttu-id="f83ca-145">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="f83ca-145">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
