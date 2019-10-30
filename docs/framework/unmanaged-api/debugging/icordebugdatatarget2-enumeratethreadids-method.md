---
title: ICorDebugDataTarget2::EnumerateThreadIDs 메서드
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
ms.openlocfilehash: b4510e6858045281a2a663095972b84c40df3a22
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122154"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="658a5-102">ICorDebugDataTarget2::EnumerateThreadIDs 메서드</span><span class="sxs-lookup"><span data-stu-id="658a5-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>
<span data-ttu-id="658a5-103">활성 스레드 ID의 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="658a5-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="658a5-104">구문</span><span class="sxs-lookup"><span data-stu-id="658a5-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,   
    [out] ULONG32 *pcThreadIds,   
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="658a5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="658a5-105">Parameters</span></span>  
 <span data-ttu-id="658a5-106">cThreadIDs</span><span class="sxs-lookup"><span data-stu-id="658a5-106">cThreadIDs</span></span>  
 <span data-ttu-id="658a5-107">[in] 스레드 ID를 반환할 수 있는 최대 스레드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="658a5-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="658a5-108">pcThreadIds</span><span class="sxs-lookup"><span data-stu-id="658a5-108">pcThreadIds</span></span>  
 <span data-ttu-id="658a5-109">[out] `ULONG32` 배열에 기록된 스레드 ID의 실제 수를 나타내는 `pThreadIds`에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="658a5-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="658a5-110">pThreadIDs</span><span class="sxs-lookup"><span data-stu-id="658a5-110">pThreadIDs</span></span>  
 <span data-ttu-id="658a5-111">스레드 식별자의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="658a5-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="658a5-112">주의</span><span class="sxs-lookup"><span data-stu-id="658a5-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="658a5-113">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="658a5-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="658a5-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="658a5-114">Requirements</span></span>  
 <span data-ttu-id="658a5-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조 하세요. **헤더:** CorDebug 있습니다.</span><span class="sxs-lookup"><span data-stu-id="658a5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="658a5-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="658a5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="658a5-117">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="658a5-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="658a5-118">참조</span><span class="sxs-lookup"><span data-stu-id="658a5-118">See also</span></span>

- [<span data-ttu-id="658a5-119">ICorDebugDataTarget2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="658a5-119">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="658a5-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="658a5-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
