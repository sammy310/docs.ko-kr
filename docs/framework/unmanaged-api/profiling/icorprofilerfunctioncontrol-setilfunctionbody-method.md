---
title: ICorProfilerFunctionControl::SetILFunctionBody 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 2c33f0f7-75b2-4c19-b2c7-c94b54997576
topic_type:
- apiref
ms.openlocfilehash: a6b24fd59a183a4a59b117663772417d55cc67db
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503144"
---
# <a name="icorprofilerfunctioncontrolsetilfunctionbody-method"></a><span data-ttu-id="c19aa-102">ICorProfilerFunctionControl::SetILFunctionBody 메서드</span><span class="sxs-lookup"><span data-stu-id="c19aa-102">ICorProfilerFunctionControl::SetILFunctionBody Method</span></span>
<span data-ttu-id="c19aa-103">메서드의 공용 중간 언어(CIL) 본문을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="c19aa-103">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c19aa-104">구문</span><span class="sxs-lookup"><span data-stu-id="c19aa-104">Syntax</span></span>  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in]  ULONG   cbNewILMethodHeader,  
    [in, size_is(cbNewILMethodHeader)] LPCBYTE pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c19aa-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c19aa-105">Parameters</span></span>  
 `cbNewILMethodHeader`  
 <span data-ttu-id="c19aa-106">[in] 헤더와 본문 다음에 오는 모든 구조를 포함한 새 CIL의 총 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="c19aa-106">[in] The total size of the new CIL, including the header and any structures that come after the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="c19aa-107">[in] 새 CIL 헤더에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c19aa-107">[in] A pointer to the new CIL header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c19aa-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="c19aa-108">Return Value</span></span>  
 <span data-ttu-id="c19aa-109">이 메서드는 다음과 같은 특정 HRESULT를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c19aa-109">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="c19aa-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c19aa-110">HRESULT</span></span>|<span data-ttu-id="c19aa-111">설명</span><span class="sxs-lookup"><span data-stu-id="c19aa-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c19aa-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c19aa-112">S_OK</span></span>|<span data-ttu-id="c19aa-113">바꾸기에 성공했습니다.</span><span class="sxs-lookup"><span data-stu-id="c19aa-113">The replacement was successful.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c19aa-114">설명</span><span class="sxs-lookup"><span data-stu-id="c19aa-114">Remarks</span></span>  
 <span data-ttu-id="c19aa-115">[ICorProfilerInfo:: SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) 메서드와 달리 `SetILFunctionBody` 메서드는 새 CIL 본문에 필요한 메모리를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="c19aa-115">Unlike the [ICorProfilerInfo::SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) method, the `SetILFunctionBody` method manages the memory required for the new CIL body.</span></span> <span data-ttu-id="c19aa-116">즉, 프로파일러에서 제공 하는 CIL 본문을 [Imethodmalloc](imethodmalloc-interface.md) 인터페이스를 사용 하 여 할당 하거나 특정 범위 내에 할당할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c19aa-116">This means that the CIL body provided by the profiler does not have to be allocated by using the [IMethodMalloc](imethodmalloc-interface.md) interface or allocated within a particular range.</span></span> <span data-ttu-id="c19aa-117">어떤 힙에든 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c19aa-117">It can be allocated on any heap.</span></span> <span data-ttu-id="c19aa-118">프로파일러는가 반환 된 후 CIL 본문에 사용 되는 메모리를 해제할 수 있습니다 `SetILFunctionBody` .</span><span class="sxs-lookup"><span data-stu-id="c19aa-118">The profiler can free the memory used for its CIL body after `SetILFunctionBody` returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c19aa-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c19aa-119">Requirements</span></span>  
 <span data-ttu-id="c19aa-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c19aa-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c19aa-121">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c19aa-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c19aa-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c19aa-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c19aa-123">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c19aa-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c19aa-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c19aa-124">See also</span></span>

- [<span data-ttu-id="c19aa-125">ICorProfilerFunctionControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c19aa-125">ICorProfilerFunctionControl Interface</span></span>](icorprofilerfunctioncontrol-interface.md)
