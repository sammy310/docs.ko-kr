---
title: ICorProfilerInfo::GetAssemblyInfo 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetAssemblyInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- GetAssemblyInfo Method
helpviewer_keywords:
- GetAssemblyInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetAssemblyInfo method [.NET Framework profiling]
ms.assetid: 7a3c97c3-1e31-47b1-bf23-386785c509c4
topic_type:
- apiref
ms.openlocfilehash: ff81da15b17ab0a7fbe62b08e358f65eed3edb71
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680278"
---
# <a name="icorprofilerinfogetassemblyinfo-method"></a><span data-ttu-id="b478d-102">ICorProfilerInfo::GetAssemblyInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="b478d-102">ICorProfilerInfo::GetAssemblyInfo Method</span></span>

<span data-ttu-id="b478d-103">어셈블리 ID를 받아서 어셈블리 이름 및 해당 매니페스트 모듈의 ID를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b478d-103">Accepts an assembly ID, and returns the assembly's name and the ID of its manifest module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b478d-104">구문</span><span class="sxs-lookup"><span data-stu-id="b478d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyInfo(  
    [in]  AssemblyID  assemblyId,  
    [in]  ULONG       cchName,  
    [out] ULONG       *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR       szName[] ,  
    [out] AppDomainID *pAppDomainId,  
    [out] ModuleID    *pModuleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b478d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b478d-105">Parameters</span></span>  

 `assemblyId`  
 <span data-ttu-id="b478d-106">[in] 어셈블리의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="b478d-106">[in] The identifier of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="b478d-107">[in] `szName`의 길이(문자)입니다.</span><span class="sxs-lookup"><span data-stu-id="b478d-107">[in] The length, in characters, of `szName`.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="b478d-108">[out] 어셈블리 이름의 총 문자 길이에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b478d-108">[out] A pointer to the total character length of the assembly's name.</span></span>  
  
 `szName`  
 <span data-ttu-id="b478d-109">[out] 호출자가 제공한 와이드 문자 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="b478d-109">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="b478d-110">함수가 반환되면 어셈블리 이름을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b478d-110">When the function returns, it will contain the assembly's name.</span></span>  
  
 `pAppDomainId`  
 <span data-ttu-id="b478d-111">[out] 어셈블리를 포함하는 애플리케이션 도메인의 ID에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b478d-111">[out] A pointer to the ID of the application domain that contains the assembly.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="b478d-112">[out] 어셈블리 매니페스트 모듈의 ID에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b478d-112">[out] A pointer to the ID of the assembly's manifest module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b478d-113">설명</span><span class="sxs-lookup"><span data-stu-id="b478d-113">Remarks</span></span>  

 <span data-ttu-id="b478d-114">이 메서드가 반환된 후 `szName` 버퍼가 모듈의 어셈블리의 전체 이름을 포함하기에 충분히 큰지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b478d-114">After this method returns, you must verify that the `szName` buffer was large enough to contain the full name of the assembly.</span></span> <span data-ttu-id="b478d-115">이렇게 하려면 `pcchName`가 가리키는 값을 `cchName` 매개 변수의 값과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="b478d-115">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="b478d-116">`pcchName`이 `cchName`보다 큰 값을 가리키는 경우 더 큰 `szName` 버퍼를 할당하고 `cchName`을 더 큰 새 크기로 업데이트한 후 `GetAssemblyInfo`를 다시 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b478d-116">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetAssemblyInfo` again.</span></span>  
  
 <span data-ttu-id="b478d-117">또는 길이가 0인 `szName` 버퍼로 `GetAssemblyInfo`를 먼저 호출하여 올바른 버퍼 크기를 구합니다.</span><span class="sxs-lookup"><span data-stu-id="b478d-117">Alternatively, you can first call `GetAssemblyInfo` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="b478d-118">그런 다음 `pcchName`에 반환된 값에 따라 버퍼 크기를 조정하고 `GetAssemblyInfo`를 다시 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b478d-118">You can then adjust the buffer size based on the value returned in `pcchName` and call `GetAssemblyInfo` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b478d-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b478d-119">Requirements</span></span>  

 <span data-ttu-id="b478d-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b478d-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b478d-121">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b478d-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b478d-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b478d-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b478d-123">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b478d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b478d-124">참조</span><span class="sxs-lookup"><span data-stu-id="b478d-124">See also</span></span>

- [<span data-ttu-id="b478d-125">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b478d-125">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="b478d-126">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b478d-126">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="b478d-127">프로파일링</span><span class="sxs-lookup"><span data-stu-id="b478d-127">Profiling</span></span>](index.md)
