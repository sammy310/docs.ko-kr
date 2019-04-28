---
title: CreateAssemblyEnum 함수
ms.date: 03/30/2017
api_name:
- CreateAssemblyEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyEnum
helpviewer_keywords:
- CreateAssemblyEnum function [.NET Framework fusion]
ms.assetid: 3506df38-6cea-42f6-946e-4287863bcfb3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0c5dabd4145098941e9e8a7e36fa3215c26713d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771880"
---
# <a name="createassemblyenum-function"></a><span data-ttu-id="e0d15-102">CreateAssemblyEnum 함수</span><span class="sxs-lookup"><span data-stu-id="e0d15-102">CreateAssemblyEnum Function</span></span>
<span data-ttu-id="e0d15-103">포인터를 가져는 [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) 지정 된 어셈블리의 개체를 열거할 수 있는 인스턴스 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e0d15-103">Gets a pointer to an [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) instance that can enumerate the objects in the assembly with the specified [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0d15-104">구문</span><span class="sxs-lookup"><span data-stu-id="e0d15-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0d15-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e0d15-105">Parameters</span></span>  
 `pEnum`  
 <span data-ttu-id="e0d15-106">[out] 요청 된 요소가 있는 메모리 위치에 대 한 포인터 `IAssemblyEnum` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e0d15-106">[out] Pointer to a memory location that contains the requested `IAssemblyEnum` pointer.</span></span>  
  
 `pUnkReserved`  
 <span data-ttu-id="e0d15-107">[in] 향후 확장성을 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0d15-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="e0d15-108">`pUnkReserved` null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0d15-108">`pUnkReserved` must be a null reference.</span></span>  
  
 `pName`  
 <span data-ttu-id="e0d15-109">[in] `IAssemblyName` 요청된 된 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="e0d15-109">[in] The `IAssemblyName` of the requested assembly.</span></span> <span data-ttu-id="e0d15-110">이 이름은 열거형 필터링에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0d15-110">This name is used to filter the enumeration.</span></span> <span data-ttu-id="e0d15-111">전역 어셈블리 캐시의 모든 어셈블리를 열거 하는 null 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0d15-111">It can be null to enumerate all assemblies in the global assembly cache.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e0d15-112">[in] 열거자의 동작을 수정 하기 위한 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="e0d15-112">[in] Flags for modifying the enumerator's behavior.</span></span> <span data-ttu-id="e0d15-113">이 매개 변수에서 정확히 하나의 비트가 포함 된 [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="e0d15-113">This parameter contains exactly one bit from the [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) enumeration.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="e0d15-114">[in] 향후 확장성을 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0d15-114">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="e0d15-115">`pvReserved` null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0d15-115">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0d15-116">설명</span><span class="sxs-lookup"><span data-stu-id="e0d15-116">Remarks</span></span>  
 <span data-ttu-id="e0d15-117">합니다 `dwFlags` 매개 변수에서 정확히 하나의 비트가 포함 된 `ASM_CACHE_FLAGS` 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="e0d15-117">The `dwFlags` parameter contains exactly one bit from the `ASM_CACHE_FLAGS` enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0d15-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e0d15-118">Requirements</span></span>  
 <span data-ttu-id="e0d15-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0d15-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0d15-120">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="e0d15-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e0d15-121">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e0d15-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e0d15-122">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0d15-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0d15-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="e0d15-123">See also</span></span>

- [<span data-ttu-id="e0d15-124">IAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e0d15-124">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
- [<span data-ttu-id="e0d15-125">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e0d15-125">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="e0d15-126">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="e0d15-126">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
