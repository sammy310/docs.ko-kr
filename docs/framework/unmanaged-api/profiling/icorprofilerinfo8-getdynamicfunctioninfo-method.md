---
description: '자세히 알아보기: ICorProfilerInfo8:: GetDynamicFunctionInfo 메서드'
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
ms.openlocfilehash: 48c8dbe20ccafb3fb23e9e289f728d5e3370613a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646584"
---
# <a name="icorprofilerinfo8getdynamicfunctioninfo-method"></a><span data-ttu-id="3934e-103">ICorProfilerInfo8:: GetDynamicFunctionInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="3934e-103">ICorProfilerInfo8::GetDynamicFunctionInfo Method</span></span>

<span data-ttu-id="3934e-104">동적 메서드에 대 한 정보를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="3934e-104">Retrieves information about dynamic methods.</span></span>

## <a name="syntax"></a><span data-ttu-id="3934e-105">구문</span><span class="sxs-lookup"><span data-stu-id="3934e-105">Syntax</span></span>

```cpp
HRESULT GetDynamicFunctionInfo( [in]  FunctionID              functionId,
                                [out] ModuleID                *moduleId,
                                [out] PCCOR_SIGNATURE         *ppvSig,
                                [out] ULONG                   *pbSig,
                                [in]  ULONG                   cchName,
                                [out] ULONG                   *pcchName,
                                [out] WCHAR                   wszName[]);
```

## <a name="parameters"></a><span data-ttu-id="3934e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3934e-106">Parameters</span></span>

- `functionId`

  <span data-ttu-id="3934e-107">\[in] 정보를 검색할 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3934e-107">\[in] The ID of the function for which to retrieve information.</span></span>

- `moduleId`

  <span data-ttu-id="3934e-108">\[in] 함수의 부모 클래스가 정의 되어 있는 모듈에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3934e-108">\[in] A pointer to the module in which the function's parent class is defined.</span></span>

- `ppvSig`

  <span data-ttu-id="3934e-109">\[out] 함수에 대 한 시그니처에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3934e-109">\[out] A pointer to the signature for the function.</span></span>

- `pbSig`

  <span data-ttu-id="3934e-110">\[out] 함수 시그니처의 바이트 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3934e-110">\[out] A pointer to the count of bytes for the function signature.</span></span>

- `cchName`

  <span data-ttu-id="3934e-111">\[in] 배열의 최대 크기 `wszName` 입니다.</span><span class="sxs-lookup"><span data-stu-id="3934e-111">\[in] The maximum size of the `wszName` array.</span></span>

- `pcchName`

  <span data-ttu-id="3934e-112">\[out] 배열의 문자 수 `wszName` 입니다.</span><span class="sxs-lookup"><span data-stu-id="3934e-112">\[out] The number of characters in the `wszName` array.</span></span>

- `wszName`

  <span data-ttu-id="3934e-113">\[out] 함수 이름 (있는 경우)의 배열입니다 `WCHAR` .</span><span class="sxs-lookup"><span data-stu-id="3934e-113">\[out] An array of `WCHAR` which is the name of the function, if one exists.</span></span>

## <a name="remarks"></a><span data-ttu-id="3934e-114">설명</span><span class="sxs-lookup"><span data-stu-id="3934e-114">Remarks</span></span>

<span data-ttu-id="3934e-115">IL 스텁 또는 LCG와 같은 특정 메서드에는 [IMetaDataImport](../metadata/imetadataimport-interface.md) 및 [IMetaDataImport2](../metadata/imetadataimport2-interface.md) api를 사용 하 여 검색할 수 있는 연결 된 메타 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3934e-115">Certain methods like IL Stubs or LCG do not have associated metadata that can be retrieved using the [IMetaDataImport](../metadata/imetadataimport-interface.md) and [IMetaDataImport2](../metadata/imetadataimport2-interface.md) APIs.</span></span> <span data-ttu-id="3934e-116">이러한 메서드는 프로파일러에서 명령 포인터를 통하거나 [ICorProfilerCallback8::D ynamicmethodjitcompilationstarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)를 수신 하 여 발견할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3934e-116">Such methods can be encountered by profilers through instruction pointers or by listening to [ICorProfilerCallback8::DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span></span>

<span data-ttu-id="3934e-117">이 API는 사용 가능한 경우 이름을 포함 하 여 동적 메서드에 대 한 정보를 검색 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3934e-117">This API can be used to retrieve information about dynamic methods, including a friendly name, if available.</span></span>

## <a name="requirements"></a><span data-ttu-id="3934e-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3934e-118">Requirements</span></span>

<span data-ttu-id="3934e-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3934e-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="3934e-120">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3934e-120">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="3934e-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3934e-121">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="3934e-122">**.NET Framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3934e-122">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3934e-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3934e-123">See also</span></span>

- [<span data-ttu-id="3934e-124">ICorProfilerInfo8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3934e-124">ICorProfilerInfo8 Interface</span></span>](icorprofilerinfo8-interface.md)
