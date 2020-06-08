---
title: ICorProfilerInfo::GetFunctionInfo 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionInfo
helpviewer_keywords:
- ICorProfilerInfo::GetFunctionInfo method [.NET Framework profiling]
- GetFunctionInfo method [.NET Framework profiling]
ms.assetid: c42b5891-019d-46b3-b551-4606295b75b8
topic_type:
- apiref
ms.openlocfilehash: e7193526bb0da1d28da4bf6bde108fc4d3fba273
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503018"
---
# <a name="icorprofilerinfogetfunctioninfo-method"></a><span data-ttu-id="4a955-102">ICorProfilerInfo::GetFunctionInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="4a955-102">ICorProfilerInfo::GetFunctionInfo Method</span></span>
<span data-ttu-id="4a955-103">지정 된 함수에 대 한 부모 클래스 및 메타 데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4a955-103">Gets the parent class and metadata token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a955-104">구문</span><span class="sxs-lookup"><span data-stu-id="4a955-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionInfo(  
    [in]  FunctionID functionId,  
    [out] ClassID    *pClassId,  
    [out] ModuleID   *pModuleId,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a955-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4a955-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="4a955-106">진행 부모 클래스 및 메타 데이터 토큰을 가져올 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4a955-106">[in] The ID of the function for which to get the parent class and metadata token.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="4a955-107">[out] 함수의 부모 클래스에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4a955-107">[out] A pointer to the parent class of the function.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="4a955-108">[out] 함수의 부모 클래스가 정의된 모듈에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4a955-108">[out] A pointer to the module in which the function's parent class is defined.</span></span>  
  
 `pToken`  
 <span data-ttu-id="4a955-109">[out] 함수의 메타데이터 토큰에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4a955-109">[out] A pointer to the metadata token for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a955-110">설명</span><span class="sxs-lookup"><span data-stu-id="4a955-110">Remarks</span></span>  
 <span data-ttu-id="4a955-111">프로파일러 코드는 [ICorProfilerInfo:: GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) 를 호출 하 여 지정 된 모듈에 대 한 메타 데이터 인터페이스를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a955-111">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="4a955-112">`pToken`에서 참조하는 위치로 반환되는 메타데이터 토큰을 사용하여 함수에 대한 메타데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a955-112">The metadata token that is returned to the location referenced by `pToken` can then be used to access the metadata for the function.</span></span>  
  
 <span data-ttu-id="4a955-113">`ClassID`제네릭 클래스에 대 한 함수의는 함수 사용에 대 한 추가 컨텍스트 정보 없이 얻을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4a955-113">The `ClassID` of a function on a generic class might not be obtainable without more contextual information about the use of the function.</span></span> <span data-ttu-id="4a955-114">이 경우 `pClassId` 은 0이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a955-114">In this case, `pClassId` will be 0.</span></span> <span data-ttu-id="4a955-115">프로파일러 코드는 COR_PRF_FRAME_INFO 값을 사용 하 여 [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) 를 사용 하 여 더 많은 컨텍스트를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a955-115">Profiler code should use [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) with a COR_PRF_FRAME_INFO value to provide more context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a955-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4a955-116">Requirements</span></span>  
 <span data-ttu-id="4a955-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4a955-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a955-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4a955-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4a955-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a955-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a955-120">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a955-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a955-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a955-121">See also</span></span>

- [<span data-ttu-id="4a955-122">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4a955-122">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
