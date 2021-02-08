---
description: '자세히 알아보기: ICorProfilerCallback2:: ThreadNameChanged 메서드'
title: ICorProfilerCallback2::ThreadNameChanged 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.ThreadNameChanged
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::ThreadNameChanged
helpviewer_keywords:
- ThreadNameChanged method [.NET Framework profiling]
- ICorProfilerCallback2::ThreadNameChanged method [.NET Framework profiling]
ms.assetid: c8bbd76d-a9ff-44f2-87a6-be052819da36
topic_type:
- apiref
ms.openlocfilehash: 161247f9692d1307d063e244b200eb0d8f739e9a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799046"
---
# <a name="icorprofilercallback2threadnamechanged-method"></a><span data-ttu-id="e4931-103">ICorProfilerCallback2::ThreadNameChanged 메서드</span><span class="sxs-lookup"><span data-stu-id="e4931-103">ICorProfilerCallback2::ThreadNameChanged Method</span></span>

<span data-ttu-id="e4931-104">스레드의 이름이 변경 되었음을 코드 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e4931-104">Notifies the code profiler that the name of a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4931-105">구문</span><span class="sxs-lookup"><span data-stu-id="e4931-105">Syntax</span></span>  
  
```cpp  
HRESULT ThreadNameChanged(  
    [in] ThreadID threadId,  
    [in] ULONG cchName,  
    [in] WCHAR name[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4931-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e4931-106">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="e4931-107">진행 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e4931-107">[in] The ID of the thread.</span></span>  
  
 `cchName`  
 <span data-ttu-id="e4931-108">진행 스레드의 새 이름 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="e4931-108">[in] The length of the new name of the thread.</span></span>  
  
 `name`  
 <span data-ttu-id="e4931-109">진행 스레드의 새 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e4931-109">[in] The new name of the thread.</span></span> <span data-ttu-id="e4931-110">이름이 null로 종료 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e4931-110">The name is not null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4931-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e4931-111">Requirements</span></span>  

 <span data-ttu-id="e4931-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e4931-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4931-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e4931-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e4931-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4931-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4931-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4931-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4931-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e4931-116">See also</span></span>

- [<span data-ttu-id="e4931-117">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e4931-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="e4931-118">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e4931-118">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
