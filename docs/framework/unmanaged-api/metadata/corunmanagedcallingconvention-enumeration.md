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
ms.openlocfilehash: ff308a81282a1cc14c35583daf9cbb057149e556
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59178453"
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="614ad-102">CorUnmanagedCallingConvention 열거형</span><span class="sxs-lookup"><span data-stu-id="614ad-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="614ad-103">비관리 코드에 대 한 호출 규칙을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="614ad-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="614ad-104">구문</span><span class="sxs-lookup"><span data-stu-id="614ad-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="614ad-105">멤버</span><span class="sxs-lookup"><span data-stu-id="614ad-105">Members</span></span>  
  
|<span data-ttu-id="614ad-106">멤버</span><span class="sxs-lookup"><span data-stu-id="614ad-106">Member</span></span>|<span data-ttu-id="614ad-107">설명</span><span class="sxs-lookup"><span data-stu-id="614ad-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="614ad-108">C 언어 호출 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="614ad-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="614ad-109">표준 호출 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="614ad-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="614ad-110">"This" 호출 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="614ad-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="614ad-111">"고속" 호출 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="614ad-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="614ad-112">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="614ad-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="614ad-113">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="614ad-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="614ad-114">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="614ad-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="614ad-115">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="614ad-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="614ad-116">설명</span><span class="sxs-lookup"><span data-stu-id="614ad-116">Remarks</span></span>  
 <span data-ttu-id="614ad-117">CLR은.NET Framework 버전 1.0의에서 "고속" 호출 규칙을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="614ad-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="614ad-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="614ad-118">Requirements</span></span>  
 <span data-ttu-id="614ad-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="614ad-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="614ad-120">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="614ad-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="614ad-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="614ad-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="614ad-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="614ad-122">See also</span></span>

- [<span data-ttu-id="614ad-123">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="614ad-123">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
