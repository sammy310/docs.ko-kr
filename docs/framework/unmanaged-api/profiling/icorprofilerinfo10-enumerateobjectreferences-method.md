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
ms.openlocfilehash: c18532450e420f38413028a18630dbf3e308fa61
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102106724"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a><span data-ttu-id="c65a7-103">ICorProfilerInfo10:: EnumerateObjectReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="c65a7-103">ICorProfilerInfo10::EnumerateObjectReferences Method</span></span>

<span data-ttu-id="c65a7-104">ObjectID, callback 및 clientData가 지정 된 경우 각 개체 참조를 열거 합니다 (있는 경우).</span><span class="sxs-lookup"><span data-stu-id="c65a7-104">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span>

## <a name="syntax"></a><span data-ttu-id="c65a7-105">구문</span><span class="sxs-lookup"><span data-stu-id="c65a7-105">Syntax</span></span>

```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```

## <a name="parameters"></a><span data-ttu-id="c65a7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c65a7-106">Parameters</span></span>

- `objectId`

  <span data-ttu-id="c65a7-107">\[in] 참조를 열거 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c65a7-107">\[in] The object to enumerate references on.</span></span>

- `callback`

  <span data-ttu-id="c65a7-108">\[in] 개체에 대 한 참조를 사용 하 여 호출 되는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="c65a7-108">\[in] The function that will be called with the references for the object.</span></span>

- `clientData`

  <span data-ttu-id="c65a7-109">\[in] 프로파일러에서 함수에 전달할 데이터를 제공 `callback` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c65a7-109">\[in] Profiler-provided data to pass to the `callback` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="c65a7-110">설명</span><span class="sxs-lookup"><span data-stu-id="c65a7-110">Remarks</span></span>

<span data-ttu-id="c65a7-111">`EnumerateObjectReferences`메서드는 참조를 저장 하는 배열을 미리 할당 하는 대신 프로파일러의 요청 시 참조를 [ObjectReferences](icorprofilercallback-objectreferences-method.md)한다는 점을 제외 하 고는와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="c65a7-111">The `EnumerateObjectReferences` method is similar to [ObjectReferences](icorprofilercallback-objectreferences-method.md), except that it walks the references on demand for the profiler instead of pre-allocating an array to store the references.</span></span>

## <a name="requirements"></a><span data-ttu-id="c65a7-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c65a7-112">Requirements</span></span>

<span data-ttu-id="c65a7-113">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c65a7-113">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="c65a7-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c65a7-114">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="c65a7-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c65a7-115">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="c65a7-116">**.Net 버전:**[!INCLUDE[net_core_30](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c65a7-116">**.NET Versions:** [!INCLUDE[net_core_30](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c65a7-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c65a7-117">See also</span></span>

- [<span data-ttu-id="c65a7-118">ICorProfilerInfo10 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c65a7-118">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
