---
description: '자세히 알아보기: ICorDebugExceptionDebugEvent:: GetNativeIP 메서드'
title: ICorDebugExceptionDebugEvent::GetNativeIP 메서드
ms.date: 03/30/2017
ms.assetid: 12e6a262-d9ac-49b8-9b80-1e653a2a3819
ms.openlocfilehash: 89bda36efc59e2462634c3d8a3a5835c9d4b3354
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693462"
---
# <a name="icordebugexceptiondebugeventgetnativeip-method"></a><span data-ttu-id="1935d-103">ICorDebugExceptionDebugEvent::GetNativeIP 메서드</span><span class="sxs-lookup"><span data-stu-id="1935d-103">ICorDebugExceptionDebugEvent::GetNativeIP Method</span></span>

<span data-ttu-id="1935d-104">이 예외 디버그 이벤트에 대한 네이티브 명령 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1935d-104">Gets the native instruction pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1935d-105">구문</span><span class="sxs-lookup"><span data-stu-id="1935d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeIP(  
   [out]CORDB_ADDRESS *pIP  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1935d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1935d-106">Parameters</span></span>  

 `pIP`  
 <span data-ttu-id="1935d-107">[out] 이 예외 디버그 이벤트의 명령 포인터에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1935d-107">[out] A pointer to the instruction pointer for this exception debug event.</span></span> <span data-ttu-id="1935d-108">자세한 내용은 설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1935d-108">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1935d-109">설명</span><span class="sxs-lookup"><span data-stu-id="1935d-109">Remarks</span></span>  

 <span data-ttu-id="1935d-110">이 명령 포인터의 의미는 다음 표와 같이 이벤트 유형에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="1935d-110">The meaning of this instruction pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="1935d-111">이벤트 유형</span><span class="sxs-lookup"><span data-stu-id="1935d-111">Event type</span></span>|<span data-ttu-id="1935d-112">`pStackPointer` 값의 의미</span><span class="sxs-lookup"><span data-stu-id="1935d-112">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="1935d-113">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="1935d-113">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="1935d-114">오류가 발생한 명령의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="1935d-114">The address of the faulting instruction.</span></span>|  
|[<span data-ttu-id="1935d-115">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="1935d-115">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="1935d-116">예외가 발생 하지 않은 경우 실행을 다시 시작할 [Getstackpointer](icordebugexceptiondebugevent-getstackpointer-method.md) 메서드로 표시 된 프레임의 코드 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="1935d-116">The code address in the frame indicated by the [GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md) method where execution would resume if no exception had been raised.</span></span> <span data-ttu-id="1935d-117">예외로 인해 `try/catch/finally` 절의 catch 블록과 같은 다른 코드가 이 프레임에서 실행되거나 실행되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1935d-117">The exception may or may not cause different code, such as the catch block of a `try/catch/finally` clause, to be executed in this frame.</span></span>|  
|[<span data-ttu-id="1935d-118">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="1935d-118">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="1935d-119">`catch` [Getstackpointer](icordebugexceptiondebugevent-getstackpointer-method.md) 메서드로 표시 된 프레임에서 처리기 실행이 시작 되는 코드 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="1935d-119">The code address where `catch` handler execution will start in the frame indicated by the [GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md) method.</span></span>|  
|[<span data-ttu-id="1935d-120">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="1935d-120">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="1935d-121">`pIP`가 0입니다.</span><span class="sxs-lookup"><span data-stu-id="1935d-121">`pIP` is 0.</span></span>|  
  
 <span data-ttu-id="1935d-122">이벤트 유형은 [ICorDebugDebugEvent:: GetEventKind](icordebugdebugevent-geteventkind-method.md) 메서드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1935d-122">The event type is available from the [ICorDebugDebugEvent::GetEventKind](icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1935d-123">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1935d-123">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1935d-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1935d-124">Requirements</span></span>  

 <span data-ttu-id="1935d-125">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1935d-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1935d-126">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1935d-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1935d-127">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1935d-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1935d-128">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1935d-128">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1935d-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1935d-129">See also</span></span>

- [<span data-ttu-id="1935d-130">ICorDebugExceptionDebugEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1935d-130">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="1935d-131">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1935d-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
