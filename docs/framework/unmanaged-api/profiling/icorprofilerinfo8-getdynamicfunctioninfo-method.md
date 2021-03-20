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
ms.openlocfilehash: b38bd7a4f440edba0a7156176f223ba38c9807cf
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759119"
---
# <a name="icorprofilerinfo8getdynamicfunctioninfo-method"></a><span data-ttu-id="9134e-103">ICorProfilerInfo8:: GetDynamicFunctionInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="9134e-103">ICorProfilerInfo8::GetDynamicFunctionInfo Method</span></span>

<span data-ttu-id="9134e-104">동적 메서드에 대 한 정보를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="9134e-104">Retrieves information about dynamic methods.</span></span>

## <a name="syntax"></a><span data-ttu-id="9134e-105">구문</span><span class="sxs-lookup"><span data-stu-id="9134e-105">Syntax</span></span>

```cpp
HRESULT GetDynamicFunctionInfo( [in]  FunctionID              functionId,
                                [out] ModuleID                *moduleId,
                                [out] PCCOR_SIGNATURE         *ppvSig,
                                [out] ULONG                   *pbSig,
                                [in]  ULONG                   cchName,
                                [out] ULONG                   *pcchName,
                                [out] WCHAR                   wszName[]);
```

## <a name="parameters"></a><span data-ttu-id="9134e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9134e-106">Parameters</span></span>

<span data-ttu-id="9134e-107">`functionId` 진행 정보를 검색할 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9134e-107">`functionId` [in] The ID of the function for which to retrieve information.</span></span>

<span data-ttu-id="9134e-108">`moduleId` 진행 함수의 부모 클래스가 정의 되어 있는 모듈에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9134e-108">`moduleId` [in] A pointer to the module in which the function's parent class is defined.</span></span>

<span data-ttu-id="9134e-109">`ppvSig` 제한이 함수의 시그니처에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9134e-109">`ppvSig` [out] A pointer to the signature for the function.</span></span>

<span data-ttu-id="9134e-110">`pbSig` 제한이 함수 시그니처의 바이트 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9134e-110">`pbSig` [out] A pointer to the count of bytes for the function signature.</span></span>

<span data-ttu-id="9134e-111">`cchName` 진행 배열의 최대 크기 `wszName` 입니다.</span><span class="sxs-lookup"><span data-stu-id="9134e-111">`cchName` [in] The maximum size of the `wszName` array.</span></span>

<span data-ttu-id="9134e-112">`pcchName` 제한이 배열에 있는 문자의 수 `wszName` 입니다.</span><span class="sxs-lookup"><span data-stu-id="9134e-112">`pcchName` [out] The number of characters in the `wszName` array.</span></span>

<span data-ttu-id="9134e-113">`wszName` 제한이 함수 이름이 있는 경우이 배열에 해당 하는 배열입니다 `WCHAR` .</span><span class="sxs-lookup"><span data-stu-id="9134e-113">`wszName` [out] An array of `WCHAR` which is the name of the function, if one exists.</span></span>

## <a name="remarks"></a><span data-ttu-id="9134e-114">설명</span><span class="sxs-lookup"><span data-stu-id="9134e-114">Remarks</span></span>

<span data-ttu-id="9134e-115">IL 스텁 또는 LCG와 같은 특정 메서드에는 [IMetaDataImport](../metadata/imetadataimport-interface.md) 및 [IMetaDataImport2](../metadata/imetadataimport2-interface.md) api를 사용 하 여 검색할 수 있는 연결 된 메타 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9134e-115">Certain methods like IL Stubs or LCG do not have associated metadata that can be retrieved using the [IMetaDataImport](../metadata/imetadataimport-interface.md) and [IMetaDataImport2](../metadata/imetadataimport2-interface.md) APIs.</span></span> <span data-ttu-id="9134e-116">이러한 메서드는 프로파일러에서 명령 포인터를 통하거나 [ICorProfilerCallback8::D ynamicmethodjitcompilationstarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)를 수신 하 여 발견할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9134e-116">Such methods can be encountered by profilers through instruction pointers or by listening to [ICorProfilerCallback8::DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span></span>

<span data-ttu-id="9134e-117">이 API는 사용 가능한 경우 이름을 포함 하 여 동적 메서드에 대 한 정보를 검색 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9134e-117">This API can be used to retrieve information about dynamic methods, including a friendly name, if available.</span></span>

## <a name="requirements"></a><span data-ttu-id="9134e-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9134e-118">Requirements</span></span>

<span data-ttu-id="9134e-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9134e-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="9134e-120">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9134e-120">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="9134e-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9134e-121">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="9134e-122">**.NET Framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9134e-122">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="9134e-123">참조</span><span class="sxs-lookup"><span data-stu-id="9134e-123">See also</span></span>

- [<span data-ttu-id="9134e-124">ICorProfilerInfo8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9134e-124">ICorProfilerInfo8 Interface</span></span>](icorprofilerinfo8-interface.md)
