---
description: '자세히 알아보기: ICorDebugProcess8:: EnableExceptionCallbacksOutsideOfMyCode 메서드'
title: ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
ms.openlocfilehash: a85c9d62e5fb62fe620f0901509afa5a03504d4e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691278"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a><span data-ttu-id="d3776-103">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode 메서드</span><span class="sxs-lookup"><span data-stu-id="d3776-103">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode Method</span></span>

<span data-ttu-id="d3776-104">[.NET Framework 4.6 이상 버전에서 지원 됨]</span><span class="sxs-lookup"><span data-stu-id="d3776-104">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="d3776-105">특정 형식의 [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) 예외 콜백을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3776-105">Enables or disables certain types of [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3776-106">구문</span><span class="sxs-lookup"><span data-stu-id="d3776-106">Syntax</span></span>  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3776-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d3776-107">Parameters</span></span>  

 `enableExceptionsOutsideOfJMC`  
 <span data-ttu-id="d3776-108">[in]</span><span class="sxs-lookup"><span data-stu-id="d3776-108">[in]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3776-109">설명</span><span class="sxs-lookup"><span data-stu-id="d3776-109">Remarks</span></span>  

 <span data-ttu-id="d3776-110">`enableExceptionsOutsideOfJMC`의 값이 `false`인 경우:</span><span class="sxs-lookup"><span data-stu-id="d3776-110">If the value of `enableExceptionsOutsideOfJMC` is `false`:</span></span>  
  
- <span data-ttu-id="d3776-111">DEBUG_EXCEPTION_FIRST_CHANCE 예외로 인해 디버거 콜백이 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3776-111">A DEBUG_EXCEPTION_FIRST_CHANCE exception will not result in a callback to the debugger.</span></span>  
  
- <span data-ttu-id="d3776-112">예외가 사용자 코드로 이스케이프되지 않는 경우(즉, 예외 출처에서 예외 처리기로의 경로에 JustMyCode 또는 JMC로 표시된 메서드가 없음) DEBUG_EXCEPTION_CATCH_HANDLER_FOUND 예외로 인해 디버거 콜백이 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3776-112">A DEBUG_EXCEPTION_CATCH_HANDLER_FOUND exception will not result in a callback to the debugger if the exception never escapes into user code (that is, the path from an exception origin to an exception handler has no methods marked as JustMyCode, or JMC).</span></span>  
  
 <span data-ttu-id="d3776-113">`enableExceptionsOutsideOfJMC` 의 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="d3776-113">The default value of `enableExceptionsOutsideOfJMC` is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3776-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d3776-114">Requirements</span></span>  

 <span data-ttu-id="d3776-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3776-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3776-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d3776-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d3776-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3776-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3776-118">**.NET Framework 버전:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3776-118">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3776-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3776-119">See also</span></span>

- [<span data-ttu-id="d3776-120">ICorDebugProcess8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d3776-120">ICorDebugProcess8 Interface</span></span>](icordebugprocess8-interface.md)
- [<span data-ttu-id="d3776-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d3776-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
