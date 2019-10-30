---
title: ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
ms.openlocfilehash: b6bfd258f35f19719be5e5169a1edc22a358371c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123381"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a><span data-ttu-id="4ad2e-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode 메서드</span><span class="sxs-lookup"><span data-stu-id="4ad2e-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode Method</span></span>
<span data-ttu-id="4ad2e-103">[.NET Framework 4.6 이상 버전에서 지원 됨]</span><span class="sxs-lookup"><span data-stu-id="4ad2e-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="4ad2e-104">특정 형식의 [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) 예외 콜백을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ad2e-104">Enables or disables certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ad2e-105">구문</span><span class="sxs-lookup"><span data-stu-id="4ad2e-105">Syntax</span></span>  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ad2e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4ad2e-106">Parameters</span></span>  
 `enableExceptionsOutsideOfJMC`  
 <span data-ttu-id="4ad2e-107">[in]</span><span class="sxs-lookup"><span data-stu-id="4ad2e-107">[in]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ad2e-108">주의</span><span class="sxs-lookup"><span data-stu-id="4ad2e-108">Remarks</span></span>  
 <span data-ttu-id="4ad2e-109">`enableExceptionsOutsideOfJMC`의 값이 `false`인 경우:</span><span class="sxs-lookup"><span data-stu-id="4ad2e-109">If the value of `enableExceptionsOutsideOfJMC` is `false`:</span></span>  
  
- <span data-ttu-id="4ad2e-110">DEBUG_EXCEPTION_FIRST_CHANCE 예외로 인해 디버거에 대 한 콜백이 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ad2e-110">A DEBUG_EXCEPTION_FIRST_CHANCE exception will not result in a callback to the debugger.</span></span>  
  
- <span data-ttu-id="4ad2e-111">예외가 사용자 코드로 이스케이프 되지 않은 경우 (즉, 예외 원본에서 예외 처리기로의 경로에 JustMyCode 또는 JMC로 표시 된 메서드가 없는 경우) DEBUG_EXCEPTION_CATCH_HANDLER_FOUND 예외로 인해 디버거에 대 한 콜백이 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ad2e-111">A DEBUG_EXCEPTION_CATCH_HANDLER_FOUND exception will not result in a callback to the debugger if the exception never escapes into user code (that is, the path from an exception origin to an exception handler has no methods marked as JustMyCode, or JMC).</span></span>  
  
 <span data-ttu-id="4ad2e-112">`enableExceptionsOutsideOfJMC` 의 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="4ad2e-112">The default value of `enableExceptionsOutsideOfJMC` is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ad2e-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4ad2e-113">Requirements</span></span>  
 <span data-ttu-id="4ad2e-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ad2e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ad2e-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4ad2e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ad2e-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ad2e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ad2e-117">**.NET Framework 버전:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ad2e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ad2e-118">참조</span><span class="sxs-lookup"><span data-stu-id="4ad2e-118">See also</span></span>

- [<span data-ttu-id="4ad2e-119">ICorDebugProcess8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4ad2e-119">ICorDebugProcess8 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)
- [<span data-ttu-id="4ad2e-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4ad2e-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
