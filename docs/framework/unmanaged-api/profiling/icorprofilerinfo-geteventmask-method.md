---
description: '자세히 알아보기: ICorProfilerInfo:: GetEventMask 메서드'
title: ICorProfilerInfo::GetEventMask 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetEventMask
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetEventMask
helpviewer_keywords:
- GetEventMask method [.NET Framework profiling]
- ICorProfilerInfo::GetEventMask method [.NET Framework profiling]
ms.assetid: ec34cc13-45a3-4695-abc3-b3347d4e6fc2
topic_type:
- apiref
ms.openlocfilehash: 8ae02a0ef98330207fa7ce6366342d5e0bcb4f19
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647648"
---
# <a name="icorprofilerinfogeteventmask-method"></a><span data-ttu-id="7c557-103">ICorProfilerInfo::GetEventMask 메서드</span><span class="sxs-lookup"><span data-stu-id="7c557-103">ICorProfilerInfo::GetEventMask Method</span></span>

<span data-ttu-id="7c557-104">프로파일러가 CLR(공용 언어 런타임)에서 이벤트 알림을 받으려는 현재 이벤트 범주를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7c557-104">Gets the current event categories for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c557-105">구문</span><span class="sxs-lookup"><span data-stu-id="7c557-105">Syntax</span></span>  
  
```cpp  
HRESULT GetEventMask(  
    [out] DWORD *pdwEvents);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c557-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7c557-106">Parameters</span></span>  

 `pdwEvents`  
 <span data-ttu-id="7c557-107">[out] 이벤트 범주를 지정하는 4바이트 값에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7c557-107">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="7c557-108">각 비트는 서로 다른 기능, 동작 또는 이벤트 형식을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="7c557-108">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="7c557-109">비트는 [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) 열거형에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c557-109">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c557-110">설명</span><span class="sxs-lookup"><span data-stu-id="7c557-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7c557-111">이 메서드 대신 [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c557-111">You should call the [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="7c557-112">메서드는 `SetEventMask` 계속 지원 되지만 [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) 는 추가 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c557-112">Although the `SetEventMask` method continues to be supported, [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c557-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7c557-113">Requirements</span></span>  

 <span data-ttu-id="7c557-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c557-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c557-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7c557-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7c557-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c557-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c557-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c557-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c557-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c557-118">See also</span></span>

- [<span data-ttu-id="7c557-119">GetEventMask2 메서드</span><span class="sxs-lookup"><span data-stu-id="7c557-119">GetEventMask2 Method</span></span>](icorprofilerinfo5-geteventmask2-method.md)
- [<span data-ttu-id="7c557-120">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7c557-120">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
