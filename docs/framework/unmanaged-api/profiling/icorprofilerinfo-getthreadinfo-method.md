---
title: ICorProfilerInfo::GetThreadInfo 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetThreadInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetThreadInfo
helpviewer_keywords:
- ICorProfilerInfo::GetThreadInfo method [.NET Framework profiling]
- GetThreadInfo method [.NET Framework profiling]
ms.assetid: fc994fef-65c9-432a-84cb-66c8141147e7
topic_type:
- apiref
ms.openlocfilehash: 516a12b7a4457a0f67da24294ad96fb79d1aa5aa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707518"
---
# <a name="icorprofilerinfogetthreadinfo-method"></a><span data-ttu-id="95466-102">ICorProfilerInfo::GetThreadInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="95466-102">ICorProfilerInfo::GetThreadInfo Method</span></span>

<span data-ttu-id="95466-103">지정 된 스레드에 대 한 현재 Win32 스레드 id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="95466-103">Gets the current Win32 thread identity for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95466-104">구문</span><span class="sxs-lookup"><span data-stu-id="95466-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadInfo(  
    [in]  ThreadID threadId,  
    [out] DWORD    *pdwWin32ThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95466-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="95466-105">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="95466-106">진행 현재 Win32 ID를 가져올 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="95466-106">[in] The ID of the thread for which to get the current Win32 ID.</span></span>  
  
 `pdwWin32ThreadId`  
 <span data-ttu-id="95466-107">제한이 지정 된 스레드의 현재 Win32 스레드 ID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="95466-107">[out] A pointer to the specified thread's current Win32 thread ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95466-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="95466-108">Requirements</span></span>  

 <span data-ttu-id="95466-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95466-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95466-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="95466-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="95466-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95466-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95466-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95466-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95466-113">참조</span><span class="sxs-lookup"><span data-stu-id="95466-113">See also</span></span>

- [<span data-ttu-id="95466-114">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="95466-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
