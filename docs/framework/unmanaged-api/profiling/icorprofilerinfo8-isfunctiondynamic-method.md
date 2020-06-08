---
title: 'ICorProfilerInfo8:: IsFunctionDynamic'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.IsFunctionDynamic
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: c88279d361ea78a2e910c4621e92c500902d9124
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495127"
---
# <a name="icorprofilerinfo8isfunctiondynamic-method"></a><span data-ttu-id="226f8-102">ICorProfilerInfo8:: IsFunctionDynamic 메서드</span><span class="sxs-lookup"><span data-stu-id="226f8-102">ICorProfilerInfo8::IsFunctionDynamic Method</span></span>

<span data-ttu-id="226f8-103">함수에 연결 된 메타 데이터가 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="226f8-103">Determines if a function does not have associated metadata.</span></span>

## <a name="syntax"></a><span data-ttu-id="226f8-104">구문</span><span class="sxs-lookup"><span data-stu-id="226f8-104">Syntax</span></span>

```cpp
HRESULT IsFunctionDynamic( [in]  FunctionID  functionId,
                           [out] BOOL        *isDynamic);
```

## <a name="parameters"></a><span data-ttu-id="226f8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="226f8-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="226f8-106">\[in] `FunctionID` 문제의 함수를 식별 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="226f8-106">\[in]  The `FunctionID` that identifies the function in question.</span></span>

- `isDynamic`

  <span data-ttu-id="226f8-107">\[out] `BOOL` 함수가 메타 데이터를 포함 하지 않는지 여부를 나타내는 값을 포함 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="226f8-107">\[out] A pointer to a `BOOL` that will contain a value indicating if the function has no metadata.</span></span>

## <a name="remarks"></a><span data-ttu-id="226f8-108">설명</span><span class="sxs-lookup"><span data-stu-id="226f8-108">Remarks</span></span>

<span data-ttu-id="226f8-109">메타 데이터가 없는 함수는 동적 함수로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="226f8-109">A function is considered dynamic if it has no metadata.</span></span> <span data-ttu-id="226f8-110">IL 스텁 또는 LCG 메서드와 같은 특정 메서드는 IMetaDataImport Api를 사용 하 여 검색할 수 있는 연결 된 메타 데이터를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="226f8-110">Certain methods like IL Stubs or LCG Methods do not have associated metadata that can be retrieved using the IMetaDataImport APIs.</span></span> <span data-ttu-id="226f8-111">이러한 메서드는 프로파일러에서 명령 포인터를 통하거나 [ICorProfilerCallback::D ynamicmethodjitcompilationstarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)를 수신 하 여 발견할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="226f8-111">These methods can be encountered by profilers through instruction pointers or by listening to [ICorProfilerCallback::DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="226f8-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="226f8-112">Requirements</span></span>

<span data-ttu-id="226f8-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="226f8-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="226f8-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="226f8-114">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="226f8-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="226f8-115">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="226f8-116">**.NET Framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="226f8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="226f8-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="226f8-117">See also</span></span>

- [<span data-ttu-id="226f8-118">ICorProfilerInfo8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="226f8-118">ICorProfilerInfo8 Interface</span></span>](icorprofilerinfo8-interface.md)
