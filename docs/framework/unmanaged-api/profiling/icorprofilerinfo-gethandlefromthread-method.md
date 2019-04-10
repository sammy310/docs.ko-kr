---
title: ICorProfilerInfo::GetHandleFromThread 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetHandleFromThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetHandleFromThread
helpviewer_keywords:
- GetHandleFromThread method [.NET Framework profiling]
- ICorProfilerInfo::GetHandleFromThread method [.NET Framework profiling]
ms.assetid: 36cdc9f5-7579-4cd2-aa36-fc05c741584c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8fc26ad9b25ad243bf868d6ef3155360509e6483
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59185746"
---
# <a name="icorprofilerinfogethandlefromthread-method"></a><span data-ttu-id="fb61b-102">ICorProfilerInfo::GetHandleFromThread 메서드</span><span class="sxs-lookup"><span data-stu-id="fb61b-102">ICorProfilerInfo::GetHandleFromThread Method</span></span>
<span data-ttu-id="fb61b-103">Win32 스레드 핸들을 스레드 ID를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="fb61b-103">Maps the ID of a thread to a Win32 thread handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb61b-104">구문</span><span class="sxs-lookup"><span data-stu-id="fb61b-104">Syntax</span></span>  
  
```  
HRESULT GetHandleFromThread(  
    [in]  ThreadID threadId,  
    [out] HANDLE  *phThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb61b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fb61b-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="fb61b-106">[in] 매핑할 스레드 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fb61b-106">[in] The thread ID to be mapped.</span></span>  
  
 `phThread`  
 <span data-ttu-id="fb61b-107">[out] Win32 스레드 핸들에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fb61b-107">[out] A pointer to a Win32 thread handle.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb61b-108">설명</span><span class="sxs-lookup"><span data-stu-id="fb61b-108">Remarks</span></span>  
 <span data-ttu-id="fb61b-109">프로파일러는 Win32를 호출 해야 `DuplicateHandle` 함수 사용 하기 전에 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="fb61b-109">The profiler must call the Win32 `DuplicateHandle` function on the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb61b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fb61b-110">Requirements</span></span>  
 <span data-ttu-id="fb61b-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fb61b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb61b-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fb61b-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fb61b-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb61b-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="fb61b-114">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="fb61b-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fb61b-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="fb61b-115">See also</span></span>

- [<span data-ttu-id="fb61b-116">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb61b-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
