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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9206fbde13f457d4b2e2941ee744d645c6df9774
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781990"
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="c5a48-102">CorUnmanagedCallingConvention 열거형</span><span class="sxs-lookup"><span data-stu-id="c5a48-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="c5a48-103">비관리 코드에 대 한 호출 규칙을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a48-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5a48-104">구문</span><span class="sxs-lookup"><span data-stu-id="c5a48-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="c5a48-105">멤버</span><span class="sxs-lookup"><span data-stu-id="c5a48-105">Members</span></span>  
  
|<span data-ttu-id="c5a48-106">멤버</span><span class="sxs-lookup"><span data-stu-id="c5a48-106">Member</span></span>|<span data-ttu-id="c5a48-107">Description</span><span class="sxs-lookup"><span data-stu-id="c5a48-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="c5a48-108">C 언어 호출 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a48-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="c5a48-109">표준 호출 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a48-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="c5a48-110">"This" 호출 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a48-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="c5a48-111">"고속" 호출 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a48-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="c5a48-112">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a48-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="c5a48-113">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a48-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="c5a48-114">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a48-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="c5a48-115">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a48-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5a48-116">설명</span><span class="sxs-lookup"><span data-stu-id="c5a48-116">Remarks</span></span>  
 <span data-ttu-id="c5a48-117">CLR은.NET Framework 버전 1.0의에서 "고속" 호출 규칙을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a48-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5a48-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c5a48-118">Requirements</span></span>  
 <span data-ttu-id="c5a48-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c5a48-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5a48-120">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="c5a48-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c5a48-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5a48-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5a48-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="c5a48-122">See also</span></span>

- [<span data-ttu-id="c5a48-123">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="c5a48-123">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
