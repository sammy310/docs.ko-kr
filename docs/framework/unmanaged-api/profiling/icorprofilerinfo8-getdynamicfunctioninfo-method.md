---
title: 'ICorProfilerInfo8:: GetDynamicFunctionInfo'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.GetDynamicFunctionInfo
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: eaf33f3b0de7a18e400cd16d29c046784e2e190f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495322"
---
# <a name="icorprofilerinfo8getdynamicfunctioninfo-method"></a><span data-ttu-id="ef25c-102">ICorProfilerInfo8:: GetDynamicFunctionInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="ef25c-102">ICorProfilerInfo8::GetDynamicFunctionInfo Method</span></span>

<span data-ttu-id="ef25c-103">동적 메서드에 대 한 정보를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef25c-103">Retrieves information about dynamic methods.</span></span>

## <a name="syntax"></a><span data-ttu-id="ef25c-104">구문</span><span class="sxs-lookup"><span data-stu-id="ef25c-104">Syntax</span></span>

```cpp
HRESULT GetDynamicFunctionInfo( [in]  FunctionID              functionId,
                                [out] ModuleID                *moduleId,
                                [out] PCCOR_SIGNATURE         *ppvSig,
                                [out] ULONG                   *pbSig,
                                [in]  ULONG                   cchName,
                                [out] ULONG                   *pcchName,
                                [out] WCHAR                   wszName[]);
```

## <a name="parameters"></a><span data-ttu-id="ef25c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ef25c-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="ef25c-106">\[in] 정보를 검색할 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ef25c-106">\[in] The ID of the function for which to retrieve information.</span></span>

- `moduleId`

  <span data-ttu-id="ef25c-107">\[in] 함수의 부모 클래스가 정의 되어 있는 모듈에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ef25c-107">\[in] A pointer to the module in which the function's parent class is defined.</span></span>

- `ppvSig`

  <span data-ttu-id="ef25c-108">\[out] 함수에 대 한 시그니처에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ef25c-108">\[out] A pointer to the signature for the function.</span></span>

- `pbSig`

  <span data-ttu-id="ef25c-109">\[out] 함수 시그니처의 바이트 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ef25c-109">\[out] A pointer to the count of bytes for the function signature.</span></span>

- `cchName`

  <span data-ttu-id="ef25c-110">\[in] 배열의 최대 크기 `wszName` 입니다.</span><span class="sxs-lookup"><span data-stu-id="ef25c-110">\[in] The maximum size of the `wszName` array.</span></span>

- `pcchName`

  <span data-ttu-id="ef25c-111">\[out] 배열의 문자 수 `wszName` 입니다.</span><span class="sxs-lookup"><span data-stu-id="ef25c-111">\[out] The number of characters in the `wszName` array.</span></span>

- `wszName`

  <span data-ttu-id="ef25c-112">\[out] 함수 이름 (있는 경우)의 배열입니다 `WCHAR` .</span><span class="sxs-lookup"><span data-stu-id="ef25c-112">\[out] An array of `WCHAR` which is the name of the function, if one exists.</span></span>

## <a name="remarks"></a><span data-ttu-id="ef25c-113">설명</span><span class="sxs-lookup"><span data-stu-id="ef25c-113">Remarks</span></span>

<span data-ttu-id="ef25c-114">IL 스텁 또는 LCG와 같은 특정 메서드에는 [IMetaDataImport](../metadata/imetadataimport-interface.md) 및 [IMetaDataImport2](../metadata/imetadataimport2-interface.md) api를 사용 하 여 검색할 수 있는 연결 된 메타 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef25c-114">Certain methods like IL Stubs or LCG do not have associated metadata that can be retrieved using the [IMetaDataImport](../metadata/imetadataimport-interface.md) and [IMetaDataImport2](../metadata/imetadataimport2-interface.md) APIs.</span></span> <span data-ttu-id="ef25c-115">이러한 메서드는 프로파일러에서 명령 포인터를 통하거나 [ICorProfilerCallback8::D ynamicmethodjitcompilationstarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)를 수신 하 여 발견할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef25c-115">Such methods can be encountered by profilers through instruction pointers or by listening to [ICorProfilerCallback8::DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span></span>

<span data-ttu-id="ef25c-116">이 API는 사용 가능한 경우 이름을 포함 하 여 동적 메서드에 대 한 정보를 검색 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef25c-116">This API can be used to retrieve information about dynamic methods, including a friendly name, if available.</span></span>

## <a name="requirements"></a><span data-ttu-id="ef25c-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ef25c-117">Requirements</span></span>

<span data-ttu-id="ef25c-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ef25c-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="ef25c-119">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ef25c-119">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="ef25c-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef25c-120">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="ef25c-121">**.NET Framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ef25c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ef25c-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ef25c-122">See also</span></span>

- [<span data-ttu-id="ef25c-123">ICorProfilerInfo8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ef25c-123">ICorProfilerInfo8 Interface</span></span>](icorprofilerinfo8-interface.md)
