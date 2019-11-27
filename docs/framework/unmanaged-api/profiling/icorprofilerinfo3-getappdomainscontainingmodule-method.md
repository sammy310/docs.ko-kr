---
title: ICorProfilerInfo3::GetAppDomainsContainingModule 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetAppDomainsContainingModule Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetAppDomainsContainingModule
helpviewer_keywords:
- GetAppDomainsContainingModule method [.NET Framework profiling]
- ICorProfilerInfo3::GetAppDomainsContainingModule method [.NET Framework profiling]
ms.assetid: 603b3881-ea94-4dca-95cd-91eebac873a0
topic_type:
- apiref
ms.openlocfilehash: 93c042d760eab4bcb1846701ad92ac38cb473c69
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449740"
---
# <a name="icorprofilerinfo3getappdomainscontainingmodule-method"></a><span data-ttu-id="f0fb5-102">ICorProfilerInfo3::GetAppDomainsContainingModule 메서드</span><span class="sxs-lookup"><span data-stu-id="f0fb5-102">ICorProfilerInfo3::GetAppDomainsContainingModule Method</span></span>
<span data-ttu-id="f0fb5-103">지정된 모듈이 로드된 애플리케이션 도메인의 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f0fb5-103">Gets the identifiers of the application domains in which the given module has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0fb5-104">구문</span><span class="sxs-lookup"><span data-stu-id="f0fb5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomainsContainingModule(  
            [in] ModuleID moduleId,  
            [in] ULONG32 cAppDomainIds,  
            [out] ULONG32 *pcAppDomainIds,  
            [out, size_is(cAppDomainIds), length_is(*pcAppDomainIds)]  
                    AppDomainID appDomainIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0fb5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f0fb5-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="f0fb5-106">[in] 로드된 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f0fb5-106">[in] The ID of the loaded module.</span></span>  
  
 `cAppDomainIds`  
 <span data-ttu-id="f0fb5-107">[in] `appDomainIds` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="f0fb5-107">[in] The size of the `appDomainIds` array.</span></span>  
  
 `pcAppDomainIds`  
 <span data-ttu-id="f0fb5-108">[out] 반환된 요소의 총수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f0fb5-108">[out] A pointer to the total number of returned elements.</span></span>  
  
 `appDomainIds`  
 <span data-ttu-id="f0fb5-109">[out] 애플리케이션 도메인 ID 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="f0fb5-109">[out] An array of application domain ID values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0fb5-110">주의</span><span class="sxs-lookup"><span data-stu-id="f0fb5-110">Remarks</span></span>  
 <span data-ttu-id="f0fb5-111">메서드는 호출자 할당 버퍼를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0fb5-111">The method uses caller allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0fb5-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f0fb5-112">Requirements</span></span>  
 <span data-ttu-id="f0fb5-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0fb5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0fb5-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f0fb5-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f0fb5-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0fb5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0fb5-116">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0fb5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0fb5-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0fb5-117">See also</span></span>

- [<span data-ttu-id="f0fb5-118">ICorProfilerFunctionEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f0fb5-118">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="f0fb5-119">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f0fb5-119">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="f0fb5-120">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f0fb5-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="f0fb5-121">프로파일링</span><span class="sxs-lookup"><span data-stu-id="f0fb5-121">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
