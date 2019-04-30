---
title: ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08937e87b8bd2249b8608f8ec1ed1f7734961b3b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948566"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a><span data-ttu-id="a13dc-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode 메서드</span><span class="sxs-lookup"><span data-stu-id="a13dc-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode Method</span></span>
<span data-ttu-id="a13dc-103">[[!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="a13dc-103">[Supported in the [!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="a13dc-104">특정 유형의 사용할지 [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) 예외 콜백을 합니다.</span><span class="sxs-lookup"><span data-stu-id="a13dc-104">Enables or disables certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a13dc-105">구문</span><span class="sxs-lookup"><span data-stu-id="a13dc-105">Syntax</span></span>  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a13dc-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a13dc-106">Parameters</span></span>  
 `enableExceptionsOutsideOfJMC`  
 <span data-ttu-id="a13dc-107">[in]</span><span class="sxs-lookup"><span data-stu-id="a13dc-107">[in]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a13dc-108">설명</span><span class="sxs-lookup"><span data-stu-id="a13dc-108">Remarks</span></span>  
 <span data-ttu-id="a13dc-109">`enableExceptionsOutsideOfJMC`의 값이 `false`인 경우:</span><span class="sxs-lookup"><span data-stu-id="a13dc-109">If the value of `enableExceptionsOutsideOfJMC` is `false`:</span></span>  
  
- <span data-ttu-id="a13dc-110">DEBUG_EXCEPTION_FIRST_CHANCE 예외 디버거 콜백이 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a13dc-110">A DEBUG_EXCEPTION_FIRST_CHANCE exception will not result in a callback to the debugger.</span></span>  
  
- <span data-ttu-id="a13dc-111">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND 예외를 발생 하지 것입니다 콜백에서 디버거는 예외가 사용자 코드로 이스케이프 되지 않는 경우 (즉, 예외 출처에서 예외 처리기를 경로 JustMyCode 또는 JMC로 표시 된 메서드가 없습니다).</span><span class="sxs-lookup"><span data-stu-id="a13dc-111">A DEBUG_EXCEPTION_CATCH_HANDLER_FOUND exception will not result in a callback to the debugger if the exception never escapes into user code (that is, the path from an exception origin to an exception handler has no methods marked as JustMyCode, or JMC).</span></span>  
  
 <span data-ttu-id="a13dc-112">`enableExceptionsOutsideOfJMC` 의 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="a13dc-112">The default value of `enableExceptionsOutsideOfJMC` is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a13dc-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a13dc-113">Requirements</span></span>  
 <span data-ttu-id="a13dc-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a13dc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a13dc-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a13dc-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a13dc-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a13dc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a13dc-117">**.NET Framework 버전:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a13dc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a13dc-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="a13dc-118">See also</span></span>

- [<span data-ttu-id="a13dc-119">ICorDebugProcess8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a13dc-119">ICorDebugProcess8 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)
- [<span data-ttu-id="a13dc-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a13dc-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
