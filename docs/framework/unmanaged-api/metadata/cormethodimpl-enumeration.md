---
title: CorMethodImpl 열거형
ms.date: 03/30/2017
api_name:
- CorMethodImpl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodImpl
helpviewer_keywords:
- CorMethodImpl enumeration [.NET Framework metadata]
ms.assetid: ffbb3caf-20da-4a4b-8983-77376e72b990
topic_type:
- apiref
ms.openlocfilehash: a76a7a2d4ad68e367e38e175377aff40ce399346
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450200"
---
# <a name="cormethodimpl-enumeration"></a><span data-ttu-id="e2d69-102">CorMethodImpl 열거형</span><span class="sxs-lookup"><span data-stu-id="e2d69-102">CorMethodImpl Enumeration</span></span>
<span data-ttu-id="e2d69-103">메서드 구현 기능을 설명하는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d69-103">Contains values that describe method implementation features.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2d69-104">구문</span><span class="sxs-lookup"><span data-stu-id="e2d69-104">Syntax</span></span>  
  
```cpp  
typedef enum CorMethodImpl {  
  
    miCodeTypeMask      =   0x0003,  
    miIL                =   0x0000,  
    miNative            =   0x0001,  
    miOPTIL             =   0x0002,  
    miRuntime           =   0x0003,  
  
    miManagedMask       =   0x0004,  
    miUnmanaged         =   0x0004,  
    miManaged           =   0x0000,  
  
    miForwardRef        =   0x0010,  
    miPreserveSig       =   0x0080,  
  
    miInternalCall      =   0x1000,  
    miSynchronized      =   0x0020,  
    miNoInlining        =   0x0008,  
    miAggressiveInlining =  0x0100,  
    miNoOptimization     =  0x0040,  
    miMaxMethodImplVal  =   0xffff  
  
} CorMethodImpl;  
```  
  
## <a name="members"></a><span data-ttu-id="e2d69-105">멤버</span><span class="sxs-lookup"><span data-stu-id="e2d69-105">Members</span></span>  
  
|<span data-ttu-id="e2d69-106">멤버</span><span class="sxs-lookup"><span data-stu-id="e2d69-106">Member</span></span>|<span data-ttu-id="e2d69-107">설명</span><span class="sxs-lookup"><span data-stu-id="e2d69-107">Description</span></span>|  
|------------|-----------------|  
|`miCodeTypeMask`|<span data-ttu-id="e2d69-108">Flags that describe code type.</span><span class="sxs-lookup"><span data-stu-id="e2d69-108">Flags that describe code type.</span></span>|  
|`miIL`|<span data-ttu-id="e2d69-109">Specifies that the method implementation is Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="e2d69-109">Specifies that the method implementation is Microsoft intermediate language (MSIL).</span></span>|  
|`miNative`|<span data-ttu-id="e2d69-110">메서드 구현이 네이티브임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d69-110">Specifies that the method implementation is native.</span></span>|  
|`miOPTIL`|<span data-ttu-id="e2d69-111">Specifies that the method implementation is OPTIL.</span><span class="sxs-lookup"><span data-stu-id="e2d69-111">Specifies that the method implementation is OPTIL.</span></span>|  
|`miRuntime`|<span data-ttu-id="e2d69-112">Specifies that the method implementation is provided by the common language runtime.</span><span class="sxs-lookup"><span data-stu-id="e2d69-112">Specifies that the method implementation is provided by the common language runtime.</span></span>|  
|`miManagedMask`|<span data-ttu-id="e2d69-113">Flags that indicate whether the code is managed or unmanaged.</span><span class="sxs-lookup"><span data-stu-id="e2d69-113">Flags that indicate whether the code is managed or unmanaged.</span></span>|  
|`miUnmanaged`|<span data-ttu-id="e2d69-114">Specifies that the method implementation is unmanaged.</span><span class="sxs-lookup"><span data-stu-id="e2d69-114">Specifies that the method implementation is unmanaged.</span></span>|  
|`miManaged`|<span data-ttu-id="e2d69-115">Specifies that the method implementation is managed.</span><span class="sxs-lookup"><span data-stu-id="e2d69-115">Specifies that the method implementation is managed.</span></span>|  
|`miForwardRef`|<span data-ttu-id="e2d69-116">Specifies that the method is defined.</span><span class="sxs-lookup"><span data-stu-id="e2d69-116">Specifies that the method is defined.</span></span> <span data-ttu-id="e2d69-117">This flag is used primarily in merge scenarios.</span><span class="sxs-lookup"><span data-stu-id="e2d69-117">This flag is used primarily in merge scenarios.</span></span>|  
|`miPreserveSig`|<span data-ttu-id="e2d69-118">Specifies that the method signature cannot be mangled for an HRESULT conversion.</span><span class="sxs-lookup"><span data-stu-id="e2d69-118">Specifies that the method signature cannot be mangled for an HRESULT conversion.</span></span>|  
|`miInternalCall`|<span data-ttu-id="e2d69-119">Reserved for internal use by the common language runtime.</span><span class="sxs-lookup"><span data-stu-id="e2d69-119">Reserved for internal use by the common language runtime.</span></span>|  
|`miSynchronized`|<span data-ttu-id="e2d69-120">Specifies that the method is single-threaded through its body.</span><span class="sxs-lookup"><span data-stu-id="e2d69-120">Specifies that the method is single-threaded through its body.</span></span>|  
|`miNoInlining`|<span data-ttu-id="e2d69-121">메서드를 인라인될 수 없도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d69-121">Specifies that the method cannot be inlined.</span></span>|  
|`miAggressiveInlining`|<span data-ttu-id="e2d69-122">Specifies that the method should be inlined if possible.</span><span class="sxs-lookup"><span data-stu-id="e2d69-122">Specifies that the method should be inlined if possible.</span></span>|  
|`miNoOptimization`|<span data-ttu-id="e2d69-123">Specifies that the method should not be optimized.</span><span class="sxs-lookup"><span data-stu-id="e2d69-123">Specifies that the method should not be optimized.</span></span>|  
|`miMaxMethodImplVal`|<span data-ttu-id="e2d69-124">The maximum valid value for a `CorMethodImpl`.</span><span class="sxs-lookup"><span data-stu-id="e2d69-124">The maximum valid value for a `CorMethodImpl`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e2d69-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e2d69-125">Requirements</span></span>  
 <span data-ttu-id="e2d69-126">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2d69-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2d69-127">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="e2d69-127">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="e2d69-128">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2d69-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2d69-129">참조</span><span class="sxs-lookup"><span data-stu-id="e2d69-129">See also</span></span>

- [<span data-ttu-id="e2d69-130">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="e2d69-130">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
