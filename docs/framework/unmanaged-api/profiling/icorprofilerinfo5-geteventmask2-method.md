---
description: '자세히 알아보기: ICorProfilerInfo5:: GetEventMask2 메서드'
title: ICorProfilerInfo5::GetEventMask2 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerInfo5.GetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: f854b68f-009c-4ffb-89cd-ca874d1c0fb7
topic_type:
- apiref
ms.openlocfilehash: c6652ffe1b8fd0d99ce5493c8ba27a971363c423
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646662"
---
# <a name="icorprofilerinfo5geteventmask2-method"></a><span data-ttu-id="ae91e-103">ICorProfilerInfo5::GetEventMask2 메서드</span><span class="sxs-lookup"><span data-stu-id="ae91e-103">ICorProfilerInfo5::GetEventMask2 Method</span></span>

<span data-ttu-id="ae91e-104">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="ae91e-104">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="ae91e-105">프로파일러가 CLR(공용 언어 런타임)에서 알림을 받으려는 현재 이벤트 범주를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ae91e-105">Gets the current event categories for which the profiler wants to receive notifications from the common language runtime (CLR).</span></span>  <span data-ttu-id="ae91e-106">[ICorProfilerInfo:: GetEventMask](icorprofilerinfo-geteventmask-method.md) 메서드에서 제공 하지 않는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae91e-106">It provides functionality not provided by the [ICorProfilerInfo::GetEventMask](icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae91e-107">구문</span><span class="sxs-lookup"><span data-stu-id="ae91e-107">Syntax</span></span>  
  
```cpp
HRESULT GetEventMask2(  
        [out] DWORD* pdwEventsLow,  
        [out] DWORD* pdwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae91e-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ae91e-108">Parameters</span></span>  

 `pdwEventsLow`  
 <span data-ttu-id="ae91e-109">[out] 이벤트 범주를 지정하는 4바이트 값에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ae91e-109">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="ae91e-110">각 비트는 서로 다른 기능, 동작 또는 이벤트 형식을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="ae91e-110">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="ae91e-111">비트는 [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) 열거형에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae91e-111">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `pdwEventsHigh`  
 <span data-ttu-id="ae91e-112">[out] 이벤트 범주를 지정하는 4바이트 값에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ae91e-112">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="ae91e-113">각 비트는 서로 다른 기능, 동작 또는 이벤트 형식을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="ae91e-113">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="ae91e-114">비트는 [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) 열거형에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae91e-114">The bits are described in the [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae91e-115">설명</span><span class="sxs-lookup"><span data-stu-id="ae91e-115">Remarks</span></span>  

 <span data-ttu-id="ae91e-116">`GetEventMask2` 메서드를 사용하여 프로파일러가 구독한 콜백을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ae91e-116">The `GetEventMask2` method is used to determine which callbacks the profiler has subscribed to.</span></span> <span data-ttu-id="ae91e-117">일반적으로 `pdwEventsLow` 및 값 및 설정 하려는 새 비트의 논리 OR을 수행한 `pdwEventsHigh` 다음 [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae91e-117">Typically, you perform a logical OR of the `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
 <span data-ttu-id="ae91e-118">[Geteventmask](icorprofilerinfo-geteventmask-method.md) 메서드 대신이 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae91e-118">This method is the recommended alternative to the [GetEventMask](icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae91e-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ae91e-119">Requirements</span></span>  

 <span data-ttu-id="ae91e-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae91e-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae91e-121">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ae91e-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ae91e-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae91e-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae91e-123">**.NET Framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae91e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae91e-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae91e-124">See also</span></span>

- [<span data-ttu-id="ae91e-125">ICorProfilerInfo5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae91e-125">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)
- [<span data-ttu-id="ae91e-126">SetEventMask2 메서드</span><span class="sxs-lookup"><span data-stu-id="ae91e-126">SetEventMask2 Method</span></span>](icorprofilerinfo5-seteventmask2-method.md)
