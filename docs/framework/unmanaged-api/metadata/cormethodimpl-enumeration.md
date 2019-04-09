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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2138dd32cf39db7b7c8989ba5827178d1a1e46c7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117237"
---
# <a name="cormethodimpl-enumeration"></a><span data-ttu-id="0912d-102">CorMethodImpl 열거형</span><span class="sxs-lookup"><span data-stu-id="0912d-102">CorMethodImpl Enumeration</span></span>
<span data-ttu-id="0912d-103">메서드 구현 기능을 설명하는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0912d-103">Contains values that describe method implementation features.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0912d-104">구문</span><span class="sxs-lookup"><span data-stu-id="0912d-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="0912d-105">멤버</span><span class="sxs-lookup"><span data-stu-id="0912d-105">Members</span></span>  
  
|<span data-ttu-id="0912d-106">멤버</span><span class="sxs-lookup"><span data-stu-id="0912d-106">Member</span></span>|<span data-ttu-id="0912d-107">설명</span><span class="sxs-lookup"><span data-stu-id="0912d-107">Description</span></span>|  
|------------|-----------------|  
|`miCodeTypeMask`|<span data-ttu-id="0912d-108">코드 형식을 설명 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="0912d-108">Flags that describe code type.</span></span>|  
|`miIL`|<span data-ttu-id="0912d-109">메서드 구현이 MSIL (Microsoft intermediate language) 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0912d-109">Specifies that the method implementation is Microsoft intermediate language (MSIL).</span></span>|  
|`miNative`|<span data-ttu-id="0912d-110">메서드 구현이 네이티브임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0912d-110">Specifies that the method implementation is native.</span></span>|  
|`miOPTIL`|<span data-ttu-id="0912d-111">메서드 구현이 OPTIL 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0912d-111">Specifies that the method implementation is OPTIL.</span></span>|  
|`miRuntime`|<span data-ttu-id="0912d-112">공용 언어 런타임에 의해 메서드 구현이 제공 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0912d-112">Specifies that the method implementation is provided by the common language runtime.</span></span>|  
|`miManagedMask`|<span data-ttu-id="0912d-113">코드의 관리 되지 않는 관리 되는 여부를 나타내는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="0912d-113">Flags that indicate whether the code is managed or unmanaged.</span></span>|  
|`miUnmanaged`|<span data-ttu-id="0912d-114">메서드 구현이 관리 되지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0912d-114">Specifies that the method implementation is unmanaged.</span></span>|  
|`miManaged`|<span data-ttu-id="0912d-115">메서드 구현이 해당 관리를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0912d-115">Specifies that the method implementation is managed.</span></span>|  
|`miForwardRef`|<span data-ttu-id="0912d-116">메서드가 정의 된 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0912d-116">Specifies that the method is defined.</span></span> <span data-ttu-id="0912d-117">이 플래그는 병합 시나리오에 주로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0912d-117">This flag is used primarily in merge scenarios.</span></span>|  
|`miPreserveSig`|<span data-ttu-id="0912d-118">HRESULT 변환에 대 한 메서드 시그니처를 손상 될 수 없습니다 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0912d-118">Specifies that the method signature cannot be mangled for an HRESULT conversion.</span></span>|  
|`miInternalCall`|<span data-ttu-id="0912d-119">공용 언어 런타임에서 내부 용도로 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0912d-119">Reserved for internal use by the common language runtime.</span></span>|  
|`miSynchronized`|<span data-ttu-id="0912d-120">메서드 본문을 통해 단일 스레드 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0912d-120">Specifies that the method is single-threaded through its body.</span></span>|  
|`miNoInlining`|<span data-ttu-id="0912d-121">메서드를 인라인될 수 없도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0912d-121">Specifies that the method cannot be inlined.</span></span>|  
|`miAggressiveInlining`|<span data-ttu-id="0912d-122">메서드는 인라인 되어야 합니다 가능 하면를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0912d-122">Specifies that the method should be inlined if possible.</span></span>|  
|`miNoOptimization`|<span data-ttu-id="0912d-123">메서드를 최적화 되지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0912d-123">Specifies that the method should not be optimized.</span></span>|  
|`miMaxMethodImplVal`|<span data-ttu-id="0912d-124">에 대 한 최대 유효 값을 `CorMethodImpl`입니다.</span><span class="sxs-lookup"><span data-stu-id="0912d-124">The maximum valid value for a `CorMethodImpl`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0912d-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0912d-125">Requirements</span></span>  
 <span data-ttu-id="0912d-126">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0912d-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0912d-127">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="0912d-127">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="0912d-128">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="0912d-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0912d-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="0912d-129">See also</span></span>

- [<span data-ttu-id="0912d-130">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="0912d-130">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
