---
description: '자세히 알아보기: ICorDebugDataTarget2:: EnumerateThreadIDs 메서드'
title: ICorDebugDataTarget2::EnumerateThreadIDs 메서드
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
ms.openlocfilehash: 5bbda67e6c6de81e9de566a68f772f324d79b92f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710558"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="c3c17-103">ICorDebugDataTarget2::EnumerateThreadIDs 메서드</span><span class="sxs-lookup"><span data-stu-id="c3c17-103">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>

<span data-ttu-id="c3c17-104">활성 스레드 ID의 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c3c17-104">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3c17-105">구문</span><span class="sxs-lookup"><span data-stu-id="c3c17-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,
    [out] ULONG32 *pcThreadIds,
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3c17-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c3c17-106">Parameters</span></span>  

 <span data-ttu-id="c3c17-107">cThreadIDs</span><span class="sxs-lookup"><span data-stu-id="c3c17-107">cThreadIDs</span></span>  
 <span data-ttu-id="c3c17-108">[in] 스레드 ID를 반환할 수 있는 최대 스레드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c3c17-108">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="c3c17-109">pcThreadIds</span><span class="sxs-lookup"><span data-stu-id="c3c17-109">pcThreadIds</span></span>  
 <span data-ttu-id="c3c17-110">[out] `ULONG32` 배열에 기록된 스레드 ID의 실제 수를 나타내는 `pThreadIds`에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c3c17-110">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="c3c17-111">pThreadIDs</span><span class="sxs-lookup"><span data-stu-id="c3c17-111">pThreadIDs</span></span>  
 <span data-ttu-id="c3c17-112">스레드 식별자의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="c3c17-112">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3c17-113">설명</span><span class="sxs-lookup"><span data-stu-id="c3c17-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c3c17-114">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3c17-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3c17-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c3c17-115">Requirements</span></span>  

 <span data-ttu-id="c3c17-116">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요. **헤더:** CorDebug 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3c17-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3c17-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3c17-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3c17-118">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3c17-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3c17-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c3c17-119">See also</span></span>

- [<span data-ttu-id="c3c17-120">ICorDebugDataTarget2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3c17-120">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="c3c17-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3c17-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
