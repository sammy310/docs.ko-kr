---
title: ICorDebugRegisterSet 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet
helpviewer_keywords:
- ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: d3d9676d-0b87-4bc3-b679-7bbc7a186c88
topic_type:
- apiref
ms.openlocfilehash: 940810288b72be0d4dfc5366176663c22c369ebb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712380"
---
# <a name="icordebugregisterset-interface"></a><span data-ttu-id="8074a-102">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8074a-102">ICorDebugRegisterSet Interface</span></span>

<span data-ttu-id="8074a-103">현재 코드를 실행 중인 컴퓨터에서 사용할 수 있는 레지스터 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8074a-103">Represents the set of registers available on the computer that is currently executing code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8074a-104">메서드</span><span class="sxs-lookup"><span data-stu-id="8074a-104">Methods</span></span>  
  
|<span data-ttu-id="8074a-105">메서드</span><span class="sxs-lookup"><span data-stu-id="8074a-105">Method</span></span>|<span data-ttu-id="8074a-106">설명</span><span class="sxs-lookup"><span data-stu-id="8074a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8074a-107">GetRegisters 메서드</span><span class="sxs-lookup"><span data-stu-id="8074a-107">GetRegisters Method</span></span>](icordebugregisterset-getregisters-method.md)|<span data-ttu-id="8074a-108">비트 마스크로 지정 된 각 레지스터의 값 (현재 코드를 실행 중인 컴퓨터)을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8074a-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="8074a-109">GetRegistersAvailable 메서드</span><span class="sxs-lookup"><span data-stu-id="8074a-109">GetRegistersAvailable Method</span></span>](icordebugregisterset-getregistersavailable-method.md)|<span data-ttu-id="8074a-110">현재 사용할 수 있는 레지스터를 나타내는 비트 마스크를 가져옵니다 `ICorDebugRegisterSet` .</span><span class="sxs-lookup"><span data-stu-id="8074a-110">Gets a bit mask indicating which registers in this `ICorDebugRegisterSet` are currently available.</span></span>|  
|[<span data-ttu-id="8074a-111">GetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="8074a-111">GetThreadContext Method</span></span>](icordebugregisterset-getthreadcontext-method.md)|<span data-ttu-id="8074a-112">현재 스레드의 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8074a-112">Gets the context of the current thread.</span></span>|  
|[<span data-ttu-id="8074a-113">SetRegisters 메서드</span><span class="sxs-lookup"><span data-stu-id="8074a-113">SetRegisters Method</span></span>](icordebugregisterset-setregisters-method.md)|<span data-ttu-id="8074a-114">.NET Framework 버전 2.0에 대해 구현 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="8074a-114">Not implemented for the .NET Framework version 2.0.</span></span>|  
|[<span data-ttu-id="8074a-115">SetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="8074a-115">SetThreadContext Method</span></span>](icordebugregisterset-setthreadcontext-method.md)|<span data-ttu-id="8074a-116">.NET Framework 2.0에 대해 구현 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="8074a-116">Not implemented for the .NET Framework 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8074a-117">설명</span><span class="sxs-lookup"><span data-stu-id="8074a-117">Remarks</span></span>  

 <span data-ttu-id="8074a-118">`ICorDebugRegisterSet`인터페이스는 32 비트 레지스터만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8074a-118">The `ICorDebugRegisterSet` interface supports only 32-bit registers.</span></span> <span data-ttu-id="8074a-119">추가 레지스터가 필요한 IA-64와 같은 플랫폼에서 [ICorDebugRegisterSet2](icordebugregisterset2-interface.md) 인터페이스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8074a-119">Use the [ICorDebugRegisterSet2](icordebugregisterset2-interface.md) interface on platforms such as IA-64 that require additional registers.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8074a-120">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8074a-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8074a-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8074a-121">Requirements</span></span>  

 <span data-ttu-id="8074a-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8074a-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8074a-123">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8074a-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8074a-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8074a-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8074a-125">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8074a-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8074a-126">참조</span><span class="sxs-lookup"><span data-stu-id="8074a-126">See also</span></span>

- [<span data-ttu-id="8074a-127">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8074a-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="8074a-128">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8074a-128">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
