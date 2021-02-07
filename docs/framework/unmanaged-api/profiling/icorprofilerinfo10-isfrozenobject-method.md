---
description: '자세히 알아보기: ICorProfilerInfo10:: IsFrozenObject 메서드'
title: ICorProfilerInfo10::IsFrozenObject
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.IsFrozenObject
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: b07e456f7fa9c328217b8779733d45dfe2793fe2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753278"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a><span data-ttu-id="cf085-103">ICorProfilerInfo10:: IsFrozenObject 메서드</span><span class="sxs-lookup"><span data-stu-id="cf085-103">ICorProfilerInfo10::IsFrozenObject Method</span></span>

<span data-ttu-id="cf085-104">ObjectID가 지정 된 경우 개체가 읽기 전용 세그먼트에 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf085-104">Given an ObjectID, determines whether the object is in a read-only segment.</span></span>

## <a name="syntax"></a><span data-ttu-id="cf085-105">구문</span><span class="sxs-lookup"><span data-stu-id="cf085-105">Syntax</span></span>

```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```

## <a name="parameters"></a><span data-ttu-id="cf085-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cf085-106">Parameters</span></span>

- `objectId`

  <span data-ttu-id="cf085-107">\[in] 검사할 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cf085-107">\[in] The object to examine.</span></span>

- `pbFrozen`

  <span data-ttu-id="cf085-108">\[out] `BOOL` 개체가 읽기 전용 세그먼트에 있는지 여부를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="cf085-108">\[out] A `BOOL` indicating if the object is in a read-only segment.</span></span>

## <a name="requirements"></a><span data-ttu-id="cf085-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cf085-109">Requirements</span></span>

<span data-ttu-id="cf085-110">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cf085-110">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="cf085-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cf085-111">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="cf085-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf085-112">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="cf085-113">**.Net 버전:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf085-113">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="cf085-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf085-114">See also</span></span>

- [<span data-ttu-id="cf085-115">ICorProfilerInfo10 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cf085-115">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
