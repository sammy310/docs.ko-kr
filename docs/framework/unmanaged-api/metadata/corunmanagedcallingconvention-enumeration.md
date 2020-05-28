---
title: CorUnmanagedCallingConvention 열거형
ms.date: 03/30/2017
api_name:
- CorUnmanagedCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorUnmanagedCallingConvention
helpviewer_keywords:
- CorUnmanagedCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 83058790-160b-4703-a5eb-74b66acbdfa9
topic_type:
- apiref
ms.openlocfilehash: b4c521489f38360d45c2cf8ff3780e057299f0b4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008952"
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="bae44-102">CorUnmanagedCallingConvention 열거형</span><span class="sxs-lookup"><span data-stu-id="bae44-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="bae44-103">비관리 코드에 대 한 호출 규칙을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae44-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bae44-104">구문</span><span class="sxs-lookup"><span data-stu-id="bae44-104">Syntax</span></span>  
  
```cpp  
typedef enum CorUnmanagedCallingConvention {  
  
    IMAGE_CEE_UNMANAGED_CALLCONV_C         = 0x1,  
    IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL   = 0x2,  
    IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL  = 0x3,  
    IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL  = 0x4,  
  
    IMAGE_CEE_CS_CALLCONV_C                = 0x1,  
    IMAGE_CEE_CS_CALLCONV_STDCALL          = 0x2,  
    IMAGE_CEE_CS_CALLCONV_THISCALL         = 0x3,  
    IMAGE_CEE_CS_CALLCONV_FASTCALL         = 0x4  
  
} CorUnmanagedCallingConvention;  
```  
  
## <a name="members"></a><span data-ttu-id="bae44-105">멤버</span><span class="sxs-lookup"><span data-stu-id="bae44-105">Members</span></span>  
  
|<span data-ttu-id="bae44-106">멤버</span><span class="sxs-lookup"><span data-stu-id="bae44-106">Member</span></span>|<span data-ttu-id="bae44-107">설명</span><span class="sxs-lookup"><span data-stu-id="bae44-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="bae44-108">C 언어 호출 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="bae44-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="bae44-109">표준 호출 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="bae44-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="bae44-110">"This" 호출 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="bae44-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="bae44-111">"Fast" 호출 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="bae44-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="bae44-112">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bae44-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="bae44-113">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bae44-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="bae44-114">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bae44-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="bae44-115">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bae44-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bae44-116">설명</span><span class="sxs-lookup"><span data-stu-id="bae44-116">Remarks</span></span>  
 <span data-ttu-id="bae44-117">CLR은 .NET Framework 버전 1.0의 "fast" 호출 규칙을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bae44-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bae44-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bae44-118">Requirements</span></span>  
 <span data-ttu-id="bae44-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bae44-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bae44-120">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="bae44-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="bae44-121">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bae44-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bae44-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bae44-122">See also</span></span>

- [<span data-ttu-id="bae44-123">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="bae44-123">Metadata Enumerations</span></span>](metadata-enumerations.md)
