---
description: '자세히 알아보기: ICorProfilerInfo5:: SetEventMask2 메서드'
title: ICorProfilerInfo5::SetEventMask2 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- IcorProfilerInfo5.SetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 05dbbe2b-049c-4a60-be69-2ad7a949405e
topic_type:
- apiref
ms.openlocfilehash: 2928ec408f2fdeb363164530258a3bf5c9719e2b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799007"
---
# <a name="icorprofilerinfo5seteventmask2-method"></a><span data-ttu-id="1a5e1-103">ICorProfilerInfo5::SetEventMask2 메서드</span><span class="sxs-lookup"><span data-stu-id="1a5e1-103">ICorProfilerInfo5::SetEventMask2 Method</span></span>

<span data-ttu-id="1a5e1-104">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="1a5e1-104">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="1a5e1-105">프로파일러가 CLR(공용 언어 런타임)에서 이벤트 알림을 받을 이벤트 형식을 지정하는 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-105">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span> <span data-ttu-id="1a5e1-106">[ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) 메서드보다 더 많은 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-106">It provides more functionality than the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a5e1-107">구문</span><span class="sxs-lookup"><span data-stu-id="1a5e1-107">Syntax</span></span>  
  
```cpp
HRESULT SetEventMask2(        [in] DWORD dwEventsLow,        [in] DWORD dwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a5e1-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1a5e1-108">Parameters</span></span>  

 `dwEventsLow`  
 <span data-ttu-id="1a5e1-109">[in] 이벤트 범주를 지정하는 4바이트 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-109">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="1a5e1-110">각 비트는 서로 다른 기능, 동작 또는 이벤트 형식을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-110">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="1a5e1-111">비트는 [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) 열거형에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-111">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `dwEventsHigh`  
 <span data-ttu-id="1a5e1-112">[in] 이벤트 범주를 지정하는 4바이트 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-112">[in] A 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="1a5e1-113">각 비트는 서로 다른 기능, 동작 또는 이벤트 형식을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-113">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="1a5e1-114">비트는 [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) 열거형에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-114">The bits are described in the [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a5e1-115">설명</span><span class="sxs-lookup"><span data-stu-id="1a5e1-115">Remarks</span></span>  

 <span data-ttu-id="1a5e1-116">`SetEventMask2` 메서드를 사용하여 프로파일러가 구독하는 콜백을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-116">The `SetEventMask2` method is used to set the callbacks to which the profiler subscribes.</span></span> <span data-ttu-id="1a5e1-117">일반적으로 [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) 메서드를 호출 하 여 설정 되는 비트를 확인 하 고, 해당 `pdwEventsLow` 및 값과 설정 하려는 새 비트의 논리 OR을 수행한 `pdwEventsHigh` 다음 메서드를 호출 `SetEventMask2` 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-117">Typically, you call the [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) method to determine which bits are set, perform a logical OR of its `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the `SetEventMask2` method.</span></span>  
  
 <span data-ttu-id="1a5e1-118">이 메서드는 [Seteventmask](icorprofilerinfo-seteventmask-method.md) 메서드 대신 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-118">This method is the recommended alternative to the [SetEventMask](icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a5e1-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1a5e1-119">Requirements</span></span>  

 <span data-ttu-id="1a5e1-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a5e1-121">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1a5e1-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1a5e1-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a5e1-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a5e1-123">**.NET Framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a5e1-123">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a5e1-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1a5e1-124">See also</span></span>

- [<span data-ttu-id="1a5e1-125">ICorProfilerInfo5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1a5e1-125">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)
- [<span data-ttu-id="1a5e1-126">GetEventMask2 메서드</span><span class="sxs-lookup"><span data-stu-id="1a5e1-126">GetEventMask2 Method</span></span>](icorprofilerinfo5-geteventmask2-method.md)
