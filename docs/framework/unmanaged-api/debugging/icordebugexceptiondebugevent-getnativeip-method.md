---
title: ICorDebugExceptionDebugEvent::GetNativeIP 메서드
ms.date: 03/30/2017
ms.assetid: 12e6a262-d9ac-49b8-9b80-1e653a2a3819
ms.openlocfilehash: 31af92dae47027b7285b422a05014b081d7e39a2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788681"
---
# <a name="icordebugexceptiondebugeventgetnativeip-method"></a><span data-ttu-id="42d64-102">ICorDebugExceptionDebugEvent::GetNativeIP 메서드</span><span class="sxs-lookup"><span data-stu-id="42d64-102">ICorDebugExceptionDebugEvent::GetNativeIP Method</span></span>
<span data-ttu-id="42d64-103">이 예외 디버그 이벤트에 대한 네이티브 명령 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="42d64-103">Gets the native instruction pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42d64-104">구문</span><span class="sxs-lookup"><span data-stu-id="42d64-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeIP(  
   [out]CORDB_ADDRESS *pIP  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42d64-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="42d64-105">Parameters</span></span>  
 `pIP`  
 <span data-ttu-id="42d64-106">[out] 이 예외 디버그 이벤트의 명령 포인터에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="42d64-106">[out] A pointer to the instruction pointer for this exception debug event.</span></span> <span data-ttu-id="42d64-107">자세한 내용은 설명 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="42d64-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42d64-108">주의</span><span class="sxs-lookup"><span data-stu-id="42d64-108">Remarks</span></span>  
 <span data-ttu-id="42d64-109">이 명령 포인터의 의미는 다음 표와 같이 이벤트 유형에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="42d64-109">The meaning of this instruction pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="42d64-110">이벤트 유형</span><span class="sxs-lookup"><span data-stu-id="42d64-110">Event type</span></span>|<span data-ttu-id="42d64-111">`pStackPointer` 값의 의미</span><span class="sxs-lookup"><span data-stu-id="42d64-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="42d64-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="42d64-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="42d64-113">오류가 발생한 명령의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="42d64-113">The address of the faulting instruction.</span></span>|  
|[<span data-ttu-id="42d64-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="42d64-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="42d64-115">예외가 발생 하지 않은 경우 실행을 다시 시작할 [Getstackpointer](icordebugexceptiondebugevent-getstackpointer-method.md) 메서드로 표시 된 프레임의 코드 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="42d64-115">The code address in the frame indicated by the [GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md) method where execution would resume if no exception had been raised.</span></span> <span data-ttu-id="42d64-116">예외로 인해 `try/catch/finally` 절의 catch 블록과 같은 다른 코드가 이 프레임에서 실행되거나 실행되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42d64-116">The exception may or may not cause different code, such as the catch block of a `try/catch/finally` clause, to be executed in this frame.</span></span>|  
|[<span data-ttu-id="42d64-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="42d64-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="42d64-118">[Getstackpointer](icordebugexceptiondebugevent-getstackpointer-method.md) 메서드로 표시 된 프레임에서 `catch` 처리기 실행이 시작 되는 코드 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="42d64-118">The code address where `catch` handler execution will start in the frame indicated by the [GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md) method.</span></span>|  
|[<span data-ttu-id="42d64-119">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="42d64-119">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="42d64-120">`pIP`가 0입니다.</span><span class="sxs-lookup"><span data-stu-id="42d64-120">`pIP` is 0.</span></span>|  
  
 <span data-ttu-id="42d64-121">이벤트 유형은 [ICorDebugDebugEvent:: GetEventKind](icordebugdebugevent-geteventkind-method.md) 메서드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42d64-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="42d64-122">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42d64-122">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42d64-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="42d64-123">Requirements</span></span>  
 <span data-ttu-id="42d64-124">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="42d64-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42d64-125">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="42d64-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42d64-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42d64-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42d64-127">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42d64-127">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42d64-128">참조</span><span class="sxs-lookup"><span data-stu-id="42d64-128">See also</span></span>

- [<span data-ttu-id="42d64-129">ICorDebugExceptionDebugEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="42d64-129">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="42d64-130">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="42d64-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
