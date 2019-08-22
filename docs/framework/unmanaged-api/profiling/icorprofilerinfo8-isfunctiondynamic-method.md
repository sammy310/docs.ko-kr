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
ms.openlocfilehash: 046db493db77572904a8454a5b002dcae15b9e1d
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69661151"
---
# <a name="icorprofilerinfo8isfunctiondynamic-method"></a><span data-ttu-id="ea18c-102">ICorProfilerInfo8:: IsFunctionDynamic 메서드</span><span class="sxs-lookup"><span data-stu-id="ea18c-102">ICorProfilerInfo8::IsFunctionDynamic Method</span></span>

<span data-ttu-id="ea18c-103">함수에 연결 된 메타 데이터가 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea18c-103">Determines if a function does not have associated metadata.</span></span>

## <a name="syntax"></a><span data-ttu-id="ea18c-104">구문</span><span class="sxs-lookup"><span data-stu-id="ea18c-104">Syntax</span></span>

```cpp
HRESULT IsFunctionDynamic( [in]  FunctionID  functionId,
                           [out] BOOL        *isDynamic);
```

#### <a name="parameters"></a><span data-ttu-id="ea18c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ea18c-105">Parameters</span></span>

`functionId` \
<span data-ttu-id="ea18c-106">진행  문제의 함수를 식별 하는입니다.`FunctionID`</span><span class="sxs-lookup"><span data-stu-id="ea18c-106">[in]  The `FunctionID` that identifies the function in question.</span></span>

`isDynamic` \
<span data-ttu-id="ea18c-107">제한이 함수가 메타 데이터를 `BOOL` 포함 하지 않는지 여부를 나타내는 값을 포함 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ea18c-107">[out] A pointer to a `BOOL` that will contain a value indicating if the function has no metadata.</span></span>

## <a name="remarks"></a><span data-ttu-id="ea18c-108">설명</span><span class="sxs-lookup"><span data-stu-id="ea18c-108">Remarks</span></span>

<span data-ttu-id="ea18c-109">메타 데이터가 없는 함수는 동적 함수로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea18c-109">A function is considered dynamic if it has no metadata.</span></span> <span data-ttu-id="ea18c-110">IL 스텁 또는 LCG 메서드와 같은 특정 메서드는 IMetaDataImport Api를 사용 하 여 검색할 수 있는 연결 된 메타 데이터를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ea18c-110">Certain methods like IL Stubs or LCG Methods do not have associated metadata that can be retrieved using the IMetaDataImport APIs.</span></span> <span data-ttu-id="ea18c-111">이러한 메서드는 프로파일러에서 명령 포인터를 통하거나 [ICorProfilerCallback::D ynamicmethodjitcompilationstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)를 수신 하 여 발견할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea18c-111">These methods can be encountered by profilers through instruction pointers or by listening to [ICorProfilerCallback::DynamicMethodJITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="ea18c-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ea18c-112">Requirements</span></span>

<span data-ttu-id="ea18c-113">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ea18c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="ea18c-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ea18c-114">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="ea18c-115">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea18c-115">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="ea18c-116">**.NET Framework 버전:** [! [NET_CURRENT_V472PLUS](../../../../includes/net-current-v472plus.md) 포함</span><span class="sxs-lookup"><span data-stu-id="ea18c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="ea18c-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="ea18c-117">See also</span></span>

- [<span data-ttu-id="ea18c-118">ICorProfilerInfo8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ea18c-118">ICorProfilerInfo8 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)
