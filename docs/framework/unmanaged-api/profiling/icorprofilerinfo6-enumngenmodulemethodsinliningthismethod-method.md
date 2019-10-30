---
title: ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod 메서드
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
ms.openlocfilehash: 103fe1b6845edfe0a364db979557db63511f6ee3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130379"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a><span data-ttu-id="d0b27-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="d0b27-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>

<span data-ttu-id="d0b27-103">지정 된 NGen 모듈에 정의 되어 있고 지정 된 메서드를 인라인 하는 모든 메서드에 대 한 열거자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b27-103">Returns an enumerator to all the methods that are defined in a given NGen module and inline a given method.</span></span>

## <a name="syntax"></a><span data-ttu-id="d0b27-104">구문</span><span class="sxs-lookup"><span data-stu-id="d0b27-104">Syntax</span></span>

```cpp
HRESULT EnumNgenModuleMethodsInliningThisMethod(
        [in] ModuleID inlinersModuleId,
        [in] ModuleID inlineeModuleId,
        [in] mdMethodDef inlineeMethodId,
        [out] BOOL *incompleteData,
        [out] ICorProfilerMethodEnum** ppEnum
);
```

## <a name="parameters"></a><span data-ttu-id="d0b27-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d0b27-105">Parameters</span></span>

`inlinersModuleId`\
<span data-ttu-id="d0b27-106">진행 NGen 모듈의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d0b27-106">[in] The identifier of an NGen module.</span></span>

`inlineeModuleId`\
<span data-ttu-id="d0b27-107">진행 `inlineeMethodId`를 정의 하는 모듈의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d0b27-107">[in] The identifier of a module that defines `inlineeMethodId`.</span></span> <span data-ttu-id="d0b27-108">자세한 내용은 설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d0b27-108">See the Remarks section for more information.</span></span>

`inlineeMethodId`\
<span data-ttu-id="d0b27-109">진행 인라인 된 메서드의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d0b27-109">[in] The identifier of an inlined method.</span></span> <span data-ttu-id="d0b27-110">자세한 내용은 설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d0b27-110">See the Remarks section for more information.</span></span>

`incompleteData`\
<span data-ttu-id="d0b27-111">제한이 `ppEnum` 지정 된 메서드를 인라인 하는 모든 메서드를 포함 하는지 여부를 나타내는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="d0b27-111">[out] A flag that indicates whether `ppEnum` contains all methods inlining a given method.</span></span>  <span data-ttu-id="d0b27-112">자세한 내용은 설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d0b27-112">See the Remarks section for more information.</span></span>

`ppEnum`\
<span data-ttu-id="d0b27-113">제한이 열거자의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d0b27-113">[out] A pointer to the address of an enumerator</span></span>

## <a name="remarks"></a><span data-ttu-id="d0b27-114">주의</span><span class="sxs-lookup"><span data-stu-id="d0b27-114">Remarks</span></span>

<span data-ttu-id="d0b27-115">`inlineeModuleId` 및 `inlineeMethodId` 함께 인라인 될 수 있는 메서드의 전체 식별자를 형성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b27-115">`inlineeModuleId` and `inlineeMethodId` together form the full identifier for the method that might be inlined.</span></span> <span data-ttu-id="d0b27-116">예를 들어 모듈 `A` `Simple.Add`메서드를 정의 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b27-116">For example, assume module `A` defines a method `Simple.Add`:</span></span>

```csharp
Simple.Add(int a, int b)
{ return a + b; }
```

<span data-ttu-id="d0b27-117">및 모듈 B는 `Fancy.AddTwice`을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b27-117">and module B defines `Fancy.AddTwice`:</span></span>

```csharp
Fancy.AddTwice(int a, int b)
{ return Simple.Add(a,b) + Simple.Add(a,b); }
```

<span data-ttu-id="d0b27-118">에서는 `Fancy.AddTwice`이 `SimpleAdd`에 대 한 호출을 inlines 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b27-118">Lets also assume that `Fancy.AddTwice` inlines the call to `SimpleAdd`.</span></span> <span data-ttu-id="d0b27-119">프로파일러에서는이 열거자를 사용 하 여 `Simple.Add`인라인 된 모듈 B에 정의 된 모든 메서드를 찾을 수 있으며, 결과는 `AddTwice`를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b27-119">A profiler could use this enumerator to find all methods defined in module B which inline `Simple.Add`, and the result would enumerate `AddTwice`.</span></span>  <span data-ttu-id="d0b27-120">`inlineeModuleId`는 모듈 `A`의 식별자 이며 `inlineeMethodId`는 `Simple.Add(int a, int b)`의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d0b27-120">`inlineeModuleId` is the identifier of module `A`, and `inlineeMethodId` is the identifier of `Simple.Add(int a, int b)`.</span></span>

<span data-ttu-id="d0b27-121">함수가 반환 된 후 `incompleteData` true 이면 열거자에 지정 된 메서드를 인라인 하는 메서드가 모두 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0b27-121">If `incompleteData` is true after the function returns, the enumerator does not contain all methods inlining a given method.</span></span> <span data-ttu-id="d0b27-122">Inliners 모듈의 직접 또는 간접 종속성이 하나 이상 아직 로드 되지 않은 경우이 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0b27-122">This can happen when one or more direct or indirect dependencies of inliners module haven't been loaded yet.</span></span> <span data-ttu-id="d0b27-123">프로파일러가 정확한 데이터를 필요로 하는 경우에는 나중에 각 모듈 로드에서 더 많은 모듈이 로드 될 때 다시 시도해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b27-123">If a profiler needs accurate data, it should retry later when more modules are loaded, preferably on each module load.</span></span>

<span data-ttu-id="d0b27-124">`EnumNgenModuleMethodsInliningThisMethod` 메서드를 사용 하 여 ReJIT의 인라인에 대 한 제한 사항을 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0b27-124">The `EnumNgenModuleMethodsInliningThisMethod` method can be used to work around limitations on inlining for ReJIT.</span></span> <span data-ttu-id="d0b27-125">ReJIT를 사용 하면 프로파일러가 메서드 구현을 변경한 다음 즉석에서 새 코드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0b27-125">ReJIT lets a profiler change the implementation of a method and then create new code for it on the fly.</span></span> <span data-ttu-id="d0b27-126">예를 들어 다음과 같이 `Simple.Add`를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0b27-126">For example, we could change `Simple.Add` as follows:</span></span>

```csharp
Simple.Add(int a, int b)
{ return 42; }
```

<span data-ttu-id="d0b27-127">그러나 `Fancy.AddTwice` 이미 `Simple.Add`인라인 되어 있기 때문에 이전과 같은 동작이 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0b27-127">However because `Fancy.AddTwice` has already inlined `Simple.Add`, it continues to have the same behavior as before.</span></span> <span data-ttu-id="d0b27-128">이 제한을 해결 하기 위해 호출자는 `Simple.Add` 인라인 하는 모든 모듈의 모든 메서드를 검색 하 고 이러한 각 메서드에서 `ICorProfilerInfo5::RequestRejit`를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b27-128">To work around that limitation, the caller has to search for all methods in all modules that inline `Simple.Add` and use `ICorProfilerInfo5::RequestRejit` on each of those methods.</span></span> <span data-ttu-id="d0b27-129">메서드를 다시 컴파일하면 이전 동작 대신 `Simple.Add`의 새 동작이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b27-129">When the methods are re-compiled, they will have the new behavior of `Simple.Add` instead of the old behavior.</span></span>

## <a name="requirements"></a><span data-ttu-id="d0b27-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d0b27-130">Requirements</span></span>

<span data-ttu-id="d0b27-131">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d0b27-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="d0b27-132">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d0b27-132">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="d0b27-133">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0b27-133">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="d0b27-134">**.NET Framework 버전:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0b27-134">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d0b27-135">참조</span><span class="sxs-lookup"><span data-stu-id="d0b27-135">See also</span></span>

- [<span data-ttu-id="d0b27-136">ICorProfilerInfo6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d0b27-136">ICorProfilerInfo6 Interface</span></span>](icorprofilerinfo6-interface.md)
