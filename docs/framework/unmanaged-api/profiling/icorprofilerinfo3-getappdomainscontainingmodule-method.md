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
ms.openlocfilehash: 5cc3436716bcfc2ed0f9fd7ff7982bac7a48de9a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731204"
---
# <a name="icorprofilerinfo3getappdomainscontainingmodule-method"></a><span data-ttu-id="5b18b-102">ICorProfilerInfo3::GetAppDomainsContainingModule 메서드</span><span class="sxs-lookup"><span data-stu-id="5b18b-102">ICorProfilerInfo3::GetAppDomainsContainingModule Method</span></span>

<span data-ttu-id="5b18b-103">지정된 모듈이 로드된 애플리케이션 도메인의 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5b18b-103">Gets the identifiers of the application domains in which the given module has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b18b-104">구문</span><span class="sxs-lookup"><span data-stu-id="5b18b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomainsContainingModule(  
            [in] ModuleID moduleId,  
            [in] ULONG32 cAppDomainIds,  
            [out] ULONG32 *pcAppDomainIds,  
            [out, size_is(cAppDomainIds), length_is(*pcAppDomainIds)]  
                    AppDomainID appDomainIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b18b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5b18b-105">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="5b18b-106">[in] 로드된 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5b18b-106">[in] The ID of the loaded module.</span></span>  
  
 `cAppDomainIds`  
 <span data-ttu-id="5b18b-107">[in] `appDomainIds` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="5b18b-107">[in] The size of the `appDomainIds` array.</span></span>  
  
 `pcAppDomainIds`  
 <span data-ttu-id="5b18b-108">[out] 반환된 요소의 총수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5b18b-108">[out] A pointer to the total number of returned elements.</span></span>  
  
 `appDomainIds`  
 <span data-ttu-id="5b18b-109">[out] 애플리케이션 도메인 ID 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="5b18b-109">[out] An array of application domain ID values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b18b-110">설명</span><span class="sxs-lookup"><span data-stu-id="5b18b-110">Remarks</span></span>  

 <span data-ttu-id="5b18b-111">메서드는 호출자 할당 버퍼를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5b18b-111">The method uses caller allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b18b-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5b18b-112">Requirements</span></span>  

 <span data-ttu-id="5b18b-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b18b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b18b-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5b18b-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5b18b-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b18b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b18b-116">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b18b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b18b-117">참조</span><span class="sxs-lookup"><span data-stu-id="5b18b-117">See also</span></span>

- [<span data-ttu-id="5b18b-118">ICorProfilerFunctionEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5b18b-118">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="5b18b-119">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5b18b-119">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="5b18b-120">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5b18b-120">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="5b18b-121">프로파일링</span><span class="sxs-lookup"><span data-stu-id="5b18b-121">Profiling</span></span>](index.md)
