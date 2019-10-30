---
title: 'ICorDebugExceptionDebugEvent:: GetFlags 메서드'
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
ms.openlocfilehash: 6c330ce5b375daacdf257eda16fd5e34012f5d69
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084759"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="8efc5-102">ICorDebugExceptionDebugEvent:: GetFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="8efc5-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="8efc5-103">예외를 가로챌 수 있는지 여부를 나타내는 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8efc5-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8efc5-104">구문</span><span class="sxs-lookup"><span data-stu-id="8efc5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8efc5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8efc5-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="8efc5-106">제한이 예외를 가로챌 수 있는지 여부를 나타내는 [Cordebugexceptionflags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8efc5-106">[out] A pointer to a [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8efc5-107">주의</span><span class="sxs-lookup"><span data-stu-id="8efc5-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8efc5-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc5-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8efc5-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8efc5-109">Requirements</span></span>  
 <span data-ttu-id="8efc5-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8efc5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8efc5-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8efc5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8efc5-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8efc5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8efc5-113">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8efc5-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8efc5-114">참조</span><span class="sxs-lookup"><span data-stu-id="8efc5-114">See also</span></span>

- [<span data-ttu-id="8efc5-115">ICorDebugExceptionDebugEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8efc5-115">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="8efc5-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8efc5-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
