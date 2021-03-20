---
description: '자세히 알아보기: ICorProfilerInfo10:: EnumerateObjectReferences 메서드'
title: ICorProfilerInfo10::EnumerateObjectReferences
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.EnumerateObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: bcd374aec2944977a0745177995ba8adf0cce9b7
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759419"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a><span data-ttu-id="3917c-103">ICorProfilerInfo10:: EnumerateObjectReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="3917c-103">ICorProfilerInfo10::EnumerateObjectReferences Method</span></span>

<span data-ttu-id="3917c-104">ObjectID, callback 및 clientData가 지정 된 경우 각 개체 참조를 열거 합니다 (있는 경우).</span><span class="sxs-lookup"><span data-stu-id="3917c-104">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span>

## <a name="syntax"></a><span data-ttu-id="3917c-105">구문</span><span class="sxs-lookup"><span data-stu-id="3917c-105">Syntax</span></span>

```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```

## <a name="parameters"></a><span data-ttu-id="3917c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3917c-106">Parameters</span></span>

<span data-ttu-id="3917c-107">`objectId` 진행 참조를 열거할 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3917c-107">`objectId` [in] The object to enumerate references on.</span></span>

<span data-ttu-id="3917c-108">`callback` 진행 개체에 대 한 참조를 사용 하 여 호출 되는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="3917c-108">`callback` [in] The function that will be called with the references for the object.</span></span>

<span data-ttu-id="3917c-109">`clientData` 진행 프로파일러에서 함수에 전달할 데이터를 제공 `callback` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3917c-109">`clientData` [in] Profiler-provided data to pass to the `callback` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="3917c-110">설명</span><span class="sxs-lookup"><span data-stu-id="3917c-110">Remarks</span></span>

<span data-ttu-id="3917c-111">`EnumerateObjectReferences`메서드는 참조를 저장 하는 배열을 미리 할당 하는 대신 프로파일러의 요청 시 참조를 [ObjectReferences](icorprofilercallback-objectreferences-method.md)한다는 점을 제외 하 고는와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="3917c-111">The `EnumerateObjectReferences` method is similar to [ObjectReferences](icorprofilercallback-objectreferences-method.md), except that it walks the references on demand for the profiler instead of pre-allocating an array to store the references.</span></span>

## <a name="requirements"></a><span data-ttu-id="3917c-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3917c-112">Requirements</span></span>

<span data-ttu-id="3917c-113">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3917c-113">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="3917c-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3917c-114">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="3917c-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3917c-115">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="3917c-116">**.Net 버전:**[!INCLUDE[net_core_30](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3917c-116">**.NET Versions:** [!INCLUDE[net_core_30](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3917c-117">참조</span><span class="sxs-lookup"><span data-stu-id="3917c-117">See also</span></span>

- [<span data-ttu-id="3917c-118">ICorProfilerInfo10 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3917c-118">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
