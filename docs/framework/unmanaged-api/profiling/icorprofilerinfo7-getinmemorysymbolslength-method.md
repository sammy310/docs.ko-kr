---
title: ICorProfilerInfo7::GetInMemorySymbolsLength Method
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type:
- COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03c70b97e7af9fdc76c579c5940e2436232f6bc2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748656"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a><span data-ttu-id="42c5b-102">ICorProfilerInfo7::GetInMemorySymbolsLength Method</span><span class="sxs-lookup"><span data-stu-id="42c5b-102">ICorProfilerInfo7::GetInMemorySymbolsLength Method</span></span>
<span data-ttu-id="42c5b-103">[.NET Framework 4.6.1 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="42c5b-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="42c5b-104">메모리 내 기호 스트림의 길이 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="42c5b-104">Returns the length of an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42c5b-105">구문</span><span class="sxs-lookup"><span data-stu-id="42c5b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42c5b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="42c5b-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="42c5b-107">[in] 메모리 스트림이 포함 된 모듈의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="42c5b-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 <span data-ttu-id="42c5b-108">pCountSymbolBytes</span><span class="sxs-lookup"><span data-stu-id="42c5b-108">pCountSymbolBytes</span></span>  
 <span data-ttu-id="42c5b-109">[out] 에 대 한 포인터를 `DWORD` 메서드는 반환 될 때 바이트 스트림의 길이 포함 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="42c5b-109">[out] A pointer to a `DWORD` value that, when the method returns, contains the length of the stream in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42c5b-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="42c5b-110">Return Value</span></span>  
 <span data-ttu-id="42c5b-111">메서드는 반환 `S_OK` 경우 메모리 스트림의 길이 확인할 수 있습니다, 영 (0) 인 경우라도 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c5b-111">The method returns `S_OK` if the length of the memory stream can be determined, even if it is zero (0).</span></span>  
  
 <span data-ttu-id="42c5b-112">메서드는 반환 `CORPROF_E_MODULE_IS_DYNAMIC` 메서드를 사용 하 여 만들어진 경우 <xref:System.Reflection.Emit?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="42c5b-112">The method returns `CORPROF_E_MODULE_IS_DYNAMIC` if the method was created using <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42c5b-113">설명</span><span class="sxs-lookup"><span data-stu-id="42c5b-113">Remarks</span></span>  
 <span data-ttu-id="42c5b-114">스트림의 길이에 위치한 모듈에 있는 경우 메모리 내 기호, `pCountSymbolBytes`합니다.</span><span class="sxs-lookup"><span data-stu-id="42c5b-114">If the module has in-memory symbols, the length of the stream is placed in `pCountSymbolBytes`.</span></span> <span data-ttu-id="42c5b-115">모듈 메모리에 기호가 없으면 `*pCountSymbolBytes = 0`합니다.</span><span class="sxs-lookup"><span data-stu-id="42c5b-115">If the module doesn't have in-memory     symbols, `*pCountSymbolBytes = 0`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="42c5b-116">현재 구현에서는 Reflection.Emit을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="42c5b-116">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="42c5b-117">메서드가 반환 하는 경우 모듈을 Reflection.Emit을 사용 하 여 만든, `CORPROF_E_MODULE_IS_DYNAMIC`합니다.</span><span class="sxs-lookup"><span data-stu-id="42c5b-117">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42c5b-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="42c5b-118">Requirements</span></span>  
 <span data-ttu-id="42c5b-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="42c5b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42c5b-120">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="42c5b-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="42c5b-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42c5b-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42c5b-122">**.NET Framework 버전:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42c5b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42c5b-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="42c5b-123">See also</span></span>

- [<span data-ttu-id="42c5b-124">ICorProfilerInfo7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="42c5b-124">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
