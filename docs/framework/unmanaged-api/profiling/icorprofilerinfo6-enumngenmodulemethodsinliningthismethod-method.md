---
description: '자세히 알아보기: ICorProfilerInfo6:: EnumNgenModuleMethodsInliningThisMethod 메서드'
title: ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod 메서드
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
ms.openlocfilehash: 236aaa820162dcc1d5c6c8ade1e8da78f5f4acb0
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759132"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a><span data-ttu-id="70e88-103">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="70e88-103">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>

<span data-ttu-id="70e88-104">지정 된 NGen 모듈에 정의 되어 있고 지정 된 메서드를 인라인 하는 모든 메서드에 대 한 열거자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e88-104">Returns an enumerator to all the methods that are defined in a given NGen module and inline a given method.</span></span>

## <a name="syntax"></a><span data-ttu-id="70e88-105">구문</span><span class="sxs-lookup"><span data-stu-id="70e88-105">Syntax</span></span>

```cpp
HRESULT EnumNgenModuleMethodsInliningThisMethod(
        [in] ModuleID inlinersModuleId,
        [in] ModuleID inlineeModuleId,
        [in] mdMethodDef inlineeMethodId,
        [out] BOOL *incompleteData,
        [out] ICorProfilerMethodEnum** ppEnum
);
```

## <a name="parameters"></a><span data-ttu-id="70e88-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="70e88-106">Parameters</span></span>

<span data-ttu-id="70e88-107">`inlinersModuleId` 진행 NGen 모듈의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="70e88-107">`inlinersModuleId` [in] The identifier of an NGen module.</span></span>

<span data-ttu-id="70e88-108">`inlineeModuleId` 진행 를 정의 하는 모듈의 식별자입니다 `inlineeMethodId` .</span><span class="sxs-lookup"><span data-stu-id="70e88-108">`inlineeModuleId` [in] The identifier of a module that defines `inlineeMethodId`.</span></span> <span data-ttu-id="70e88-109">자세한 내용은 설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70e88-109">See the Remarks section for more information.</span></span>

<span data-ttu-id="70e88-110">`inlineeMethodId` 진행 인라인 된 메서드의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="70e88-110">`inlineeMethodId` [in] The identifier of an inlined method.</span></span> <span data-ttu-id="70e88-111">자세한 내용은 설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70e88-111">See the Remarks section for more information.</span></span>

<span data-ttu-id="70e88-112">`incompleteData` 제한이 `ppEnum` 에 지정 된 메서드를 인라인 하는 모든 메서드가 포함 되어 있는지 여부를 나타내는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="70e88-112">`incompleteData` [out] A flag that indicates whether `ppEnum` contains all methods inlining a given method.</span></span>  <span data-ttu-id="70e88-113">자세한 내용은 설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70e88-113">See the Remarks section for more information.</span></span>

<span data-ttu-id="70e88-114">`ppEnum` 제한이 열거자의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="70e88-114">`ppEnum` [out] A pointer to the address of an enumerator</span></span>

## <a name="remarks"></a><span data-ttu-id="70e88-115">설명</span><span class="sxs-lookup"><span data-stu-id="70e88-115">Remarks</span></span>

<span data-ttu-id="70e88-116">`inlineeModuleId` 및는 `inlineeMethodId` 모두 인라인 될 수 있는 메서드의 전체 식별자를 형성 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e88-116">`inlineeModuleId` and `inlineeMethodId` together form the full identifier for the method that might be inlined.</span></span> <span data-ttu-id="70e88-117">예를 들어 모듈에서 `A` 메서드를 정의 한다고 가정 합니다 `Simple.Add` .</span><span class="sxs-lookup"><span data-stu-id="70e88-117">For example, assume module `A` defines a method `Simple.Add`:</span></span>

```csharp
Simple.Add(int a, int b)
{ return a + b; }
```

<span data-ttu-id="70e88-118">및 모듈 B는 다음을 정의 합니다 `Fancy.AddTwice` .</span><span class="sxs-lookup"><span data-stu-id="70e88-118">and module B defines `Fancy.AddTwice`:</span></span>

```csharp
Fancy.AddTwice(int a, int b)
{ return Simple.Add(a,b) + Simple.Add(a,b); }
```

<span data-ttu-id="70e88-119">`Fancy.AddTwice`에서는가에 대 한 호출을 inlines 가정 `SimpleAdd` 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e88-119">Lets also assume that `Fancy.AddTwice` inlines the call to `SimpleAdd`.</span></span> <span data-ttu-id="70e88-120">프로파일러에서는이 열거자를 사용 하 여 모듈 B에 정의 된 모든 메서드 (인라인)를 찾을 수 `Simple.Add` 있으며 결과는를 열거 `AddTwice` 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e88-120">A profiler could use this enumerator to find all methods defined in module B which inline `Simple.Add`, and the result would enumerate `AddTwice`.</span></span>  <span data-ttu-id="70e88-121">`inlineeModuleId` 는 모듈의 식별자 이며 `A` `inlineeMethodId` 은의 식별자입니다 `Simple.Add(int a, int b)` .</span><span class="sxs-lookup"><span data-stu-id="70e88-121">`inlineeModuleId` is the identifier of module `A`, and `inlineeMethodId` is the identifier of `Simple.Add(int a, int b)`.</span></span>

<span data-ttu-id="70e88-122">`incompleteData`함수가 반환 된 후이 true 이면 열거자에 지정 된 메서드를 인라인 하는 메서드가 모두 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70e88-122">If `incompleteData` is true after the function returns, the enumerator does not contain all methods inlining a given method.</span></span> <span data-ttu-id="70e88-123">Inliners 모듈의 직접 또는 간접 종속성이 하나 이상 아직 로드 되지 않은 경우이 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e88-123">This can happen when one or more direct or indirect dependencies of inliners module haven't been loaded yet.</span></span> <span data-ttu-id="70e88-124">프로파일러가 정확한 데이터를 필요로 하는 경우에는 나중에 각 모듈 로드에서 더 많은 모듈이 로드 될 때 다시 시도해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e88-124">If a profiler needs accurate data, it should retry later when more modules are loaded, preferably on each module load.</span></span>

<span data-ttu-id="70e88-125">`EnumNgenModuleMethodsInliningThisMethod`메서드를 사용 하 여 ReJIT의 인라인에 대 한 제한 사항을 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e88-125">The `EnumNgenModuleMethodsInliningThisMethod` method can be used to work around limitations on inlining for ReJIT.</span></span> <span data-ttu-id="70e88-126">ReJIT를 사용 하면 프로파일러가 메서드 구현을 변경한 다음 즉석에서 새 코드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e88-126">ReJIT lets a profiler change the implementation of a method and then create new code for it on the fly.</span></span> <span data-ttu-id="70e88-127">예를 들어 다음과 같이 변경할 수 있습니다 `Simple.Add` .</span><span class="sxs-lookup"><span data-stu-id="70e88-127">For example, we could change `Simple.Add` as follows:</span></span>

```csharp
Simple.Add(int a, int b)
{ return 42; }
```

<span data-ttu-id="70e88-128">그러나가 이미 인라인 되어 있기 때문에 `Fancy.AddTwice` `Simple.Add` 이전과 동일한 동작을 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e88-128">However because `Fancy.AddTwice` has already inlined `Simple.Add`, it continues to have the same behavior as before.</span></span> <span data-ttu-id="70e88-129">이러한 제한을 해결 하기 위해 호출자는 `Simple.Add` 이러한 각 메서드에서 인라인 및 사용 하는 모든 모듈의 모든 메서드를 검색 해야 합니다 `ICorProfilerInfo5::RequestRejit` .</span><span class="sxs-lookup"><span data-stu-id="70e88-129">To work around that limitation, the caller has to search for all methods in all modules that inline `Simple.Add` and use `ICorProfilerInfo5::RequestRejit` on each of those methods.</span></span> <span data-ttu-id="70e88-130">메서드를 다시 컴파일하면 이전 동작 대신 새 동작을 갖게 됩니다 `Simple.Add` .</span><span class="sxs-lookup"><span data-stu-id="70e88-130">When the methods are re-compiled, they will have the new behavior of `Simple.Add` instead of the old behavior.</span></span>

## <a name="requirements"></a><span data-ttu-id="70e88-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="70e88-131">Requirements</span></span>

<span data-ttu-id="70e88-132">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70e88-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="70e88-133">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="70e88-133">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="70e88-134">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70e88-134">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="70e88-135">**.NET Framework 버전:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70e88-135">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="70e88-136">참조</span><span class="sxs-lookup"><span data-stu-id="70e88-136">See also</span></span>

- [<span data-ttu-id="70e88-137">ICorProfilerInfo6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="70e88-137">ICorProfilerInfo6 Interface</span></span>](icorprofilerinfo6-interface.md)
