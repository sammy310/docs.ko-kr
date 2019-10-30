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
ms.openlocfilehash: 0e54027806cef07fad4740c3bf5226fd26c72570
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108773"
---
# <a name="createassemblyenum-function"></a><span data-ttu-id="332cd-102">CreateAssemblyEnum 함수</span><span class="sxs-lookup"><span data-stu-id="332cd-102">CreateAssemblyEnum Function</span></span>
<span data-ttu-id="332cd-103">지정 된 [IAssemblyName](iassemblyname-interface.md)를 사용 하 여 어셈블리의 개체를 열거할 수 있는 [iassemblyenum](iassemblyenum-interface.md) 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="332cd-103">Gets a pointer to an [IAssemblyEnum](iassemblyenum-interface.md) instance that can enumerate the objects in the assembly with the specified [IAssemblyName](iassemblyname-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="332cd-104">구문</span><span class="sxs-lookup"><span data-stu-id="332cd-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="332cd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="332cd-105">Parameters</span></span>  
 `pEnum`  
 <span data-ttu-id="332cd-106">제한이 요청 된 `IAssemblyEnum` 포인터를 포함 하는 메모리 위치에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="332cd-106">[out] Pointer to a memory location that contains the requested `IAssemblyEnum` pointer.</span></span>  
  
 `pUnkReserved`  
 <span data-ttu-id="332cd-107">진행 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="332cd-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="332cd-108">`pUnkReserved`은 null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="332cd-108">`pUnkReserved` must be a null reference.</span></span>  
  
 `pName`  
 <span data-ttu-id="332cd-109">진행 요청 된 어셈블리의 `IAssemblyName`입니다.</span><span class="sxs-lookup"><span data-stu-id="332cd-109">[in] The `IAssemblyName` of the requested assembly.</span></span> <span data-ttu-id="332cd-110">이 이름은 열거형을 필터링 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="332cd-110">This name is used to filter the enumeration.</span></span> <span data-ttu-id="332cd-111">전역 어셈블리 캐시의 모든 어셈블리를 열거 하는 것은 null 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="332cd-111">It can be null to enumerate all assemblies in the global assembly cache.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="332cd-112">진행 열거자의 동작을 수정 하기 위한 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="332cd-112">[in] Flags for modifying the enumerator's behavior.</span></span> <span data-ttu-id="332cd-113">이 매개 변수는 [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) 열거형에서 정확히 한 비트를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="332cd-113">This parameter contains exactly one bit from the [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) enumeration.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="332cd-114">진행 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="332cd-114">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="332cd-115">`pvReserved`은 null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="332cd-115">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="332cd-116">주의</span><span class="sxs-lookup"><span data-stu-id="332cd-116">Remarks</span></span>  
 <span data-ttu-id="332cd-117">`dwFlags` 매개 변수는 `ASM_CACHE_FLAGS` 열거에서 정확히 1 비트를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="332cd-117">The `dwFlags` parameter contains exactly one bit from the `ASM_CACHE_FLAGS` enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="332cd-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="332cd-118">Requirements</span></span>  
 <span data-ttu-id="332cd-119">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="332cd-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="332cd-120">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="332cd-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="332cd-121">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="332cd-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="332cd-122">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="332cd-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="332cd-123">참조</span><span class="sxs-lookup"><span data-stu-id="332cd-123">See also</span></span>

- [<span data-ttu-id="332cd-124">IAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="332cd-124">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
- [<span data-ttu-id="332cd-125">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="332cd-125">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="332cd-126">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="332cd-126">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
