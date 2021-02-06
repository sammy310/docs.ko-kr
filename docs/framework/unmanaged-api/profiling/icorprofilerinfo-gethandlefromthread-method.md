---
description: '자세히 알아보기: ICorProfilerInfo:: GetHandleFromThread 메서드'
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
ms.openlocfilehash: 541a2872bc3cbbe8233e09283b9773957b0a7daf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647556"
---
# <a name="icorprofilerinfogethandlefromthread-method"></a><span data-ttu-id="96ccd-103">ICorProfilerInfo::GetHandleFromThread 메서드</span><span class="sxs-lookup"><span data-stu-id="96ccd-103">ICorProfilerInfo::GetHandleFromThread Method</span></span>

<span data-ttu-id="96ccd-104">스레드의 ID를 Win32 스레드 핸들에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="96ccd-104">Maps the ID of a thread to a Win32 thread handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96ccd-105">구문</span><span class="sxs-lookup"><span data-stu-id="96ccd-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHandleFromThread(  
    [in]  ThreadID threadId,  
    [out] HANDLE  *phThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96ccd-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="96ccd-106">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="96ccd-107">진행 매핑할 스레드 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="96ccd-107">[in] The thread ID to be mapped.</span></span>  
  
 `phThread`  
 <span data-ttu-id="96ccd-108">제한이 Win32 스레드 핸들에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="96ccd-108">[out] A pointer to a Win32 thread handle.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96ccd-109">설명</span><span class="sxs-lookup"><span data-stu-id="96ccd-109">Remarks</span></span>  

 <span data-ttu-id="96ccd-110">프로파일러는 `DuplicateHandle` 사용 하기 전에 핸들에서 Win32 함수를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96ccd-110">The profiler must call the Win32 `DuplicateHandle` function on the handle before using it.</span></span>  

 <span data-ttu-id="96ccd-111">이 메서드에서 반환 된 핸들은 런타임에 의해 소유 되며 프로파일러에서는이를 닫지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96ccd-111">The handle returned from this method is owned by the runtime and the profiler should never close it.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="96ccd-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="96ccd-112">Requirements</span></span>  

 <span data-ttu-id="96ccd-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96ccd-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96ccd-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="96ccd-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="96ccd-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96ccd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96ccd-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96ccd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96ccd-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96ccd-117">See also</span></span>

- [<span data-ttu-id="96ccd-118">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="96ccd-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
