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
ms.openlocfilehash: ad9dc185514bfddd15a6110b1b0d80fc99230271
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472280"
---
# <a name="icorprofilerinfogethandlefromthread-method"></a><span data-ttu-id="7a2bc-102">ICorProfilerInfo::GetHandleFromThread 메서드</span><span class="sxs-lookup"><span data-stu-id="7a2bc-102">ICorProfilerInfo::GetHandleFromThread Method</span></span>
<span data-ttu-id="7a2bc-103">Win32 스레드 핸들을 스레드 ID를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-103">Maps the ID of a thread to a Win32 thread handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a2bc-104">구문</span><span class="sxs-lookup"><span data-stu-id="7a2bc-104">Syntax</span></span>  
  
```  
HRESULT GetHandleFromThread(  
    [in]  ThreadID threadId,  
    [out] HANDLE  *phThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a2bc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7a2bc-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="7a2bc-106">[in] 매핑할 스레드 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-106">[in] The thread ID to be mapped.</span></span>  
  
 `phThread`  
 <span data-ttu-id="7a2bc-107">[out] Win32 스레드 핸들에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-107">[out] A pointer to a Win32 thread handle.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a2bc-108">설명</span><span class="sxs-lookup"><span data-stu-id="7a2bc-108">Remarks</span></span>  
 <span data-ttu-id="7a2bc-109">프로파일러는 Win32를 호출 해야 `DuplicateHandle` 함수 사용 하기 전에 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-109">The profiler must call the Win32 `DuplicateHandle` function on the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a2bc-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7a2bc-110">Requirements</span></span>  
 <span data-ttu-id="7a2bc-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a2bc-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7a2bc-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7a2bc-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a2bc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a2bc-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a2bc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a2bc-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="7a2bc-115">See also</span></span>
- [<span data-ttu-id="7a2bc-116">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7a2bc-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
