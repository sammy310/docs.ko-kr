---
title: ICorDebugProcess6::ProcessStateChanged 메서드
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
ms.openlocfilehash: 3927e57883ebe282b262cb03ececc3b2cd96fd46
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123423"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="29a38-102">ICorDebugProcess6::ProcessStateChanged 메서드</span><span class="sxs-lookup"><span data-stu-id="29a38-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="29a38-103">프로세스가 실행 중임을 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="29a38-103">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29a38-104">구문</span><span class="sxs-lookup"><span data-stu-id="29a38-104">Syntax</span></span>  
  
```cpp  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29a38-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="29a38-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="29a38-106">진행 [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) 열거형의 멤버</span><span class="sxs-lookup"><span data-stu-id="29a38-106">[in] A member of the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29a38-107">주의</span><span class="sxs-lookup"><span data-stu-id="29a38-107">Remarks</span></span>  
 <span data-ttu-id="29a38-108">디버거는이 메서드를 호출 하 여 프로세스가 실행 중임을 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="29a38-108">The debugger calls this method to notify [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="29a38-109">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29a38-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29a38-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="29a38-110">Requirements</span></span>  
 <span data-ttu-id="29a38-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="29a38-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29a38-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="29a38-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="29a38-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29a38-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29a38-114">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29a38-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29a38-115">참조</span><span class="sxs-lookup"><span data-stu-id="29a38-115">See also</span></span>

- [<span data-ttu-id="29a38-116">ICorDebugProcess6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="29a38-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="29a38-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="29a38-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
