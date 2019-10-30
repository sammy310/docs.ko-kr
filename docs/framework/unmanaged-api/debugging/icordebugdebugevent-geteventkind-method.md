---
title: ICorDebugDebugEvent::GetEventKind 메서드
ms.date: 03/30/2017
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
ms.openlocfilehash: 92606d7bd0a277dd327ce4fd430ce963a260206d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136653"
---
# <a name="icordebugdebugeventgeteventkind-method"></a><span data-ttu-id="e9866-102">ICorDebugDebugEvent::GetEventKind 메서드</span><span class="sxs-lookup"><span data-stu-id="e9866-102">ICorDebugDebugEvent::GetEventKind Method</span></span>
<span data-ttu-id="e9866-103">이 `ICorDebugDebugEvent` 개체가 나타내는 이벤트의 종류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e9866-103">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9866-104">구문</span><span class="sxs-lookup"><span data-stu-id="e9866-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9866-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e9866-105">Parameters</span></span>  
 <span data-ttu-id="e9866-106">pDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="e9866-106">pDebugEventKind</span></span>  
 <span data-ttu-id="e9866-107">이벤트 유형을 나타내는 [Cordebugdebugeventkind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) 열거형 멤버에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e9866-107">A pointer to a [CorDebugDebugEventKind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) enumeration member that indicates the type of event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9866-108">주의</span><span class="sxs-lookup"><span data-stu-id="e9866-108">Remarks</span></span>  
 <span data-ttu-id="e9866-109">`pDebugEventKind`의 값에 따라 `QueryInterface`를 호출하여 추가 데이터를 포함하는 보다 정확한 디버그 이벤트 인터페이스를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9866-109">Based on the value of `pDebugEventKind`, you can call `QueryInterface` to get a more precise debug event interface that has additional data.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e9866-110">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9866-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9866-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e9866-111">Requirements</span></span>  
 <span data-ttu-id="e9866-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e9866-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9866-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9866-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9866-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9866-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9866-115">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9866-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9866-116">참조</span><span class="sxs-lookup"><span data-stu-id="e9866-116">See also</span></span>

- [<span data-ttu-id="e9866-117">ICorDebugDebugEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e9866-117">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [<span data-ttu-id="e9866-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e9866-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
