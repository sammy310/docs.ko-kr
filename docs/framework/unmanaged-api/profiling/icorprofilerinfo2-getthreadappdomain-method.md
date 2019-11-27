---
title: ICorProfilerInfo2::GetThreadAppDomain 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetThreadAppDomain
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetThreadAppDomain
helpviewer_keywords:
- ICorProfilerInfo2::GetThreadAppDomain method [.NET Framework profiling]
- GetThreadAppDomain method [.NET Framework profiling]
ms.assetid: 4a11b264-8540-4732-aa35-bc2d95b95b8e
topic_type:
- apiref
ms.openlocfilehash: 8637be3c0a59676dc52aea985d7418bfd8f247bc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443110"
---
# <a name="icorprofilerinfo2getthreadappdomain-method"></a><span data-ttu-id="4019d-102">ICorProfilerInfo2::GetThreadAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="4019d-102">ICorProfilerInfo2::GetThreadAppDomain Method</span></span>
<span data-ttu-id="4019d-103">지정 된 스레드가 현재 실행 중인 코드의 응용 프로그램 도메인 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4019d-103">Gets the ID of the application domain in which the specified thread is currently executing code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4019d-104">구문</span><span class="sxs-lookup"><span data-stu-id="4019d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadAppDomain(  
    [in]  ThreadID threadId,  
    [out] AppDomainID *pAppDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4019d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4019d-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="4019d-106">진행 스레드를 지정 하는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4019d-106">[in] The ID specifying the thread.</span></span>  
  
 `pAppDomainId`  
 <span data-ttu-id="4019d-107">제한이 응용 프로그램 도메인의 ID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4019d-107">[out] A pointer to the ID of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4019d-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4019d-108">Requirements</span></span>  
 <span data-ttu-id="4019d-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4019d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4019d-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4019d-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4019d-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4019d-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4019d-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4019d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4019d-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4019d-113">See also</span></span>

- [<span data-ttu-id="4019d-114">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4019d-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="4019d-115">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4019d-115">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
