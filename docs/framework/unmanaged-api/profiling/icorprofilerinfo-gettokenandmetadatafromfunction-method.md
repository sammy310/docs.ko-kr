---
title: ICorProfilerInfo::GetTokenAndMetadataFromFunction 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetTokenAndMetadataFromFunction
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetTokenAndMetadataFromFunction
helpviewer_keywords:
- ICorProfilerInfo::GetTokenAndMetadataFromFunction method [.NET Framework profiling]
- GetTokenAndMetadataFromFunction method [.NET Framework profiling]
ms.assetid: e525aa16-c923-4b16-833b-36f1f0dd70fc
topic_type:
- apiref
ms.openlocfilehash: b3e14230888e9bf846879d5728c2b20883fb8d53
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438732"
---
# <a name="icorprofilerinfogettokenandmetadatafromfunction-method"></a><span data-ttu-id="a0c80-102">ICorProfilerInfo::GetTokenAndMetadataFromFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="a0c80-102">ICorProfilerInfo::GetTokenAndMetadataFromFunction Method</span></span>
<span data-ttu-id="a0c80-103">Gets the metadata token and a metadata interface instance that can be used against the token for the specified function.</span><span class="sxs-lookup"><span data-stu-id="a0c80-103">Gets the metadata token and a metadata interface instance that can be used against the token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0c80-104">구문</span><span class="sxs-lookup"><span data-stu-id="a0c80-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenAndMetaDataFromFunction(  
    [in]  FunctionID functionId,  
    [in]  REFIID     riid,  
    [out] IUnknown   **ppImport,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0c80-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a0c80-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="a0c80-106">[in] The ID of the function for which to get the metadata token and metadata interface.</span><span class="sxs-lookup"><span data-stu-id="a0c80-106">[in] The ID of the function for which to get the metadata token and metadata interface.</span></span>  
  
 `riid`  
 <span data-ttu-id="a0c80-107">[in] The reference ID of the metadata interface to get the instance of.</span><span class="sxs-lookup"><span data-stu-id="a0c80-107">[in] The reference ID of the metadata interface to get the instance of.</span></span>  
  
 `ppImport`  
 <span data-ttu-id="a0c80-108">[out] A pointer to the address of the metadata interface instance that can be used against the token for the specified function.</span><span class="sxs-lookup"><span data-stu-id="a0c80-108">[out] A pointer to the address of the metadata interface instance that can be used against the token for the specified function.</span></span>  
  
 `pToken`  
 <span data-ttu-id="a0c80-109">[out] A pointer to the metadata token for the specified function.</span><span class="sxs-lookup"><span data-stu-id="a0c80-109">[out] A pointer to the metadata token for the specified function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0c80-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a0c80-110">Requirements</span></span>  
 <span data-ttu-id="a0c80-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a0c80-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0c80-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a0c80-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a0c80-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0c80-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0c80-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0c80-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0c80-115">참조</span><span class="sxs-lookup"><span data-stu-id="a0c80-115">See also</span></span>

- [<span data-ttu-id="a0c80-116">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a0c80-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
