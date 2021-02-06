---
description: '자세히 알아보기: ICorProfilerInfo3:: GetAppDomainsContainingModule 메서드'
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
ms.openlocfilehash: 0f0fea5b01b80b110d7ab041574dc195162cb508
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646844"
---
# <a name="icorprofilerinfo3getappdomainscontainingmodule-method"></a><span data-ttu-id="79a63-103">ICorProfilerInfo3::GetAppDomainsContainingModule 메서드</span><span class="sxs-lookup"><span data-stu-id="79a63-103">ICorProfilerInfo3::GetAppDomainsContainingModule Method</span></span>

<span data-ttu-id="79a63-104">지정된 모듈이 로드된 애플리케이션 도메인의 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="79a63-104">Gets the identifiers of the application domains in which the given module has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79a63-105">구문</span><span class="sxs-lookup"><span data-stu-id="79a63-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomainsContainingModule(  
            [in] ModuleID moduleId,  
            [in] ULONG32 cAppDomainIds,  
            [out] ULONG32 *pcAppDomainIds,  
            [out, size_is(cAppDomainIds), length_is(*pcAppDomainIds)]  
                    AppDomainID appDomainIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79a63-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="79a63-106">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="79a63-107">[in] 로드된 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="79a63-107">[in] The ID of the loaded module.</span></span>  
  
 `cAppDomainIds`  
 <span data-ttu-id="79a63-108">[in] `appDomainIds` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="79a63-108">[in] The size of the `appDomainIds` array.</span></span>  
  
 `pcAppDomainIds`  
 <span data-ttu-id="79a63-109">[out] 반환된 요소의 총수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="79a63-109">[out] A pointer to the total number of returned elements.</span></span>  
  
 `appDomainIds`  
 <span data-ttu-id="79a63-110">[out] 애플리케이션 도메인 ID 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="79a63-110">[out] An array of application domain ID values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79a63-111">설명</span><span class="sxs-lookup"><span data-stu-id="79a63-111">Remarks</span></span>  

 <span data-ttu-id="79a63-112">메서드는 호출자 할당 버퍼를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="79a63-112">The method uses caller allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79a63-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="79a63-113">Requirements</span></span>  

 <span data-ttu-id="79a63-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79a63-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79a63-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="79a63-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="79a63-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79a63-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79a63-117">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79a63-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79a63-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="79a63-118">See also</span></span>

- [<span data-ttu-id="79a63-119">ICorProfilerFunctionEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="79a63-119">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="79a63-120">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="79a63-120">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="79a63-121">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="79a63-121">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="79a63-122">프로파일링</span><span class="sxs-lookup"><span data-stu-id="79a63-122">Profiling</span></span>](index.md)
