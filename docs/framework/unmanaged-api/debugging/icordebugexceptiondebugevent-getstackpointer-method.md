---
description: '자세히 알아보기: ICorDebugExceptionDebugEvent:: GetStackPointer 메서드'
title: ICorDebugExceptionDebugEvent::GetStackPointer 메서드
ms.date: 03/30/2017
ms.assetid: d8f66a1c-16be-4264-afc5-bc2dfbb4a682
ms.openlocfilehash: 5a62a5eb54fff1e94beebc222e3f18cc4655040f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693449"
---
# <a name="icordebugexceptiondebugeventgetstackpointer-method"></a><span data-ttu-id="58b35-103">ICorDebugExceptionDebugEvent::GetStackPointer 메서드</span><span class="sxs-lookup"><span data-stu-id="58b35-103">ICorDebugExceptionDebugEvent::GetStackPointer Method</span></span>

<span data-ttu-id="58b35-104">이 예외 디버그 이벤트에 대한 스택 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="58b35-104">Gets the stack pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58b35-105">구문</span><span class="sxs-lookup"><span data-stu-id="58b35-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStackPointer(  
   [out]CORDB_ADDRESS *pStackPointer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58b35-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="58b35-106">Parameters</span></span>  

 `pStackPointer`  
 <span data-ttu-id="58b35-107">[out] 이 예외 디버그 이벤트의 스택 포인터에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="58b35-107">[out] A pointer to the address of the stack pointer for this exception debug event.</span></span> <span data-ttu-id="58b35-108">자세한 내용은 설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="58b35-108">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58b35-109">설명</span><span class="sxs-lookup"><span data-stu-id="58b35-109">Remarks</span></span>  

 <span data-ttu-id="58b35-110">이 스택 포인터의 의미는 다음 표와 같이 이벤트 유형에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="58b35-110">The meaning of this stack pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="58b35-111">이벤트 유형</span><span class="sxs-lookup"><span data-stu-id="58b35-111">Event type</span></span>|<span data-ttu-id="58b35-112">`pStackPointer` 값의 의미</span><span class="sxs-lookup"><span data-stu-id="58b35-112">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="58b35-113">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="58b35-113">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="58b35-114">예외를 throw한 프레임에 대한 스택 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="58b35-114">The stack pointer for the frame that threw the exception.</span></span>|  
|[<span data-ttu-id="58b35-115">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="58b35-115">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="58b35-116">예외가 throw된 지점과 가장 가까운 사용자 코드 프레임에 대한 스택 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="58b35-116">The stack pointer for the user-code frame closest to the point of the thrown exception.</span></span>|  
|[<span data-ttu-id="58b35-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="58b35-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="58b35-118">catch 처리기가 포함된 프레임에 대한 스택 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="58b35-118">The stack pointer for the frame that contains the catch handler.</span></span>|  
|[<span data-ttu-id="58b35-119">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="58b35-119">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="58b35-120">`pStackPointer`가 **null** 인 경우</span><span class="sxs-lookup"><span data-stu-id="58b35-120">`pStackPointer` is **null**.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="58b35-121">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58b35-121">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="58b35-122">이벤트 유형은 [ICorDebugDebugEvent:: GetEventKind](icordebugdebugevent-geteventkind-method.md) 메서드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58b35-122">The event type is available from the [ICorDebugDebugEvent::GetEventKind](icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58b35-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="58b35-123">Requirements</span></span>  

 <span data-ttu-id="58b35-124">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="58b35-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58b35-125">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="58b35-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="58b35-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58b35-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58b35-127">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58b35-127">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58b35-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58b35-128">See also</span></span>

- [<span data-ttu-id="58b35-129">ICorDebugExceptionDebugEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="58b35-129">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="58b35-130">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="58b35-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
