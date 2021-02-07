---
description: '자세한 정보: CreateAssemblyEnum 함수'
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
ms.openlocfilehash: 47177fcf0cd9e1b492fa89b9fb80c5cdaaced689
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761144"
---
# <a name="createassemblyenum-function"></a><span data-ttu-id="ed3f9-103">CreateAssemblyEnum 함수</span><span class="sxs-lookup"><span data-stu-id="ed3f9-103">CreateAssemblyEnum Function</span></span>

<span data-ttu-id="ed3f9-104">지정 된 [IAssemblyName](iassemblyname-interface.md)를 사용 하 여 어셈블리의 개체를 열거할 수 있는 [iassemblyenum](iassemblyenum-interface.md) 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ed3f9-104">Gets a pointer to an [IAssemblyEnum](iassemblyenum-interface.md) instance that can enumerate the objects in the assembly with the specified [IAssemblyName](iassemblyname-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed3f9-105">구문</span><span class="sxs-lookup"><span data-stu-id="ed3f9-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed3f9-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ed3f9-106">Parameters</span></span>  

 `pEnum`  
 <span data-ttu-id="ed3f9-107">제한이 요청 된 포인터를 포함 하는 메모리 위치에 대 한 포인터 `IAssemblyEnum` 입니다.</span><span class="sxs-lookup"><span data-stu-id="ed3f9-107">[out] Pointer to a memory location that contains the requested `IAssemblyEnum` pointer.</span></span>  
  
 `pUnkReserved`  
 <span data-ttu-id="ed3f9-108">진행 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ed3f9-108">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="ed3f9-109">`pUnkReserved` 는 null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3f9-109">`pUnkReserved` must be a null reference.</span></span>  
  
 `pName`  
 <span data-ttu-id="ed3f9-110">진행 `IAssemblyName` 요청 된 어셈블리의입니다.</span><span class="sxs-lookup"><span data-stu-id="ed3f9-110">[in] The `IAssemblyName` of the requested assembly.</span></span> <span data-ttu-id="ed3f9-111">이 이름은 열거형을 필터링 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed3f9-111">This name is used to filter the enumeration.</span></span> <span data-ttu-id="ed3f9-112">전역 어셈블리 캐시의 모든 어셈블리를 열거 하는 것은 null 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed3f9-112">It can be null to enumerate all assemblies in the global assembly cache.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ed3f9-113">진행 열거자의 동작을 수정 하기 위한 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="ed3f9-113">[in] Flags for modifying the enumerator's behavior.</span></span> <span data-ttu-id="ed3f9-114">이 매개 변수는 [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) 열거형에서 정확히 1 비트를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3f9-114">This parameter contains exactly one bit from the [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) enumeration.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="ed3f9-115">진행 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ed3f9-115">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="ed3f9-116">`pvReserved` 는 null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3f9-116">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed3f9-117">설명</span><span class="sxs-lookup"><span data-stu-id="ed3f9-117">Remarks</span></span>  

 <span data-ttu-id="ed3f9-118">`dwFlags`매개 변수는 열거형에서 정확히 1 비트를 포함 합니다 `ASM_CACHE_FLAGS` .</span><span class="sxs-lookup"><span data-stu-id="ed3f9-118">The `dwFlags` parameter contains exactly one bit from the `ASM_CACHE_FLAGS` enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed3f9-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ed3f9-119">Requirements</span></span>  

 <span data-ttu-id="ed3f9-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed3f9-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed3f9-121">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="ed3f9-121">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ed3f9-122">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed3f9-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ed3f9-123">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed3f9-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed3f9-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed3f9-124">See also</span></span>

- [<span data-ttu-id="ed3f9-125">IAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ed3f9-125">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
- [<span data-ttu-id="ed3f9-126">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ed3f9-126">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="ed3f9-127">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="ed3f9-127">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
