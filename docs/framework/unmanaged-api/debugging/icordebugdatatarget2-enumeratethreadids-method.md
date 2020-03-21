---
title: ICorDebugDataTarget2::EnumerateThreadIDs 메서드
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
ms.openlocfilehash: 120a970aac33b1ab06ae47335a959d2791f893ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178987"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="a65ed-102">ICorDebugDataTarget2::EnumerateThreadIDs 메서드</span><span class="sxs-lookup"><span data-stu-id="a65ed-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>
<span data-ttu-id="a65ed-103">활성 스레드 ID의 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a65ed-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a65ed-104">구문</span><span class="sxs-lookup"><span data-stu-id="a65ed-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,
    [out] ULONG32 *pcThreadIds,
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a65ed-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a65ed-105">Parameters</span></span>  
 <span data-ttu-id="a65ed-106">cThreadIDs</span><span class="sxs-lookup"><span data-stu-id="a65ed-106">cThreadIDs</span></span>  
 <span data-ttu-id="a65ed-107">[in] 스레드 ID를 반환할 수 있는 최대 스레드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a65ed-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="a65ed-108">pcThreadIds</span><span class="sxs-lookup"><span data-stu-id="a65ed-108">pcThreadIds</span></span>  
 <span data-ttu-id="a65ed-109">[out] `ULONG32` 배열에 기록된 스레드 ID의 실제 수를 나타내는 `pThreadIds`에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a65ed-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="a65ed-110">pThreadIDs</span><span class="sxs-lookup"><span data-stu-id="a65ed-110">pThreadIDs</span></span>  
 <span data-ttu-id="a65ed-111">스레드 식별자의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="a65ed-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a65ed-112">설명</span><span class="sxs-lookup"><span data-stu-id="a65ed-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a65ed-113">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a65ed-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a65ed-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a65ed-114">Requirements</span></span>  
 <span data-ttu-id="a65ed-115">**플랫폼:** [시스템 요구 사항을](../../../../docs/framework/get-started/system-requirements.md)참조하십시오. **헤더:** 코르데버그.idl, 코르데버그.h</span><span class="sxs-lookup"><span data-stu-id="a65ed-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a65ed-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a65ed-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a65ed-117">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a65ed-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a65ed-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a65ed-118">See also</span></span>

- [<span data-ttu-id="a65ed-119">ICorDebugDataTarget2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a65ed-119">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="a65ed-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a65ed-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
