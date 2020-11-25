---
title: ICorDebugStepperEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugStepperEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepperEnum
helpviewer_keywords:
- ICorDebugStepperEnum interface [.NET Framework debugging]
ms.assetid: 988718c1-1a4a-40f2-a04c-7d67e5cfe1e2
topic_type:
- apiref
ms.openlocfilehash: facea5cd7f0b0e0e6c0b1049e87a2355f1d3965a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697170"
---
# <a name="icordebugstepperenum-interface"></a><span data-ttu-id="062eb-102">ICorDebugStepperEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="062eb-102">ICorDebugStepperEnum Interface</span></span>

<span data-ttu-id="062eb-103">ICorDebugEnum 메서드를 구현 하 고 ICorDebugStepper 배열을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="062eb-103">Implements ICorDebugEnum methods, and enumerates ICorDebugStepper arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="062eb-104">메서드</span><span class="sxs-lookup"><span data-stu-id="062eb-104">Methods</span></span>  
  
|<span data-ttu-id="062eb-105">메서드</span><span class="sxs-lookup"><span data-stu-id="062eb-105">Method</span></span>|<span data-ttu-id="062eb-106">설명</span><span class="sxs-lookup"><span data-stu-id="062eb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="062eb-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="062eb-107">Next Method</span></span>](icordebugstepperenum-next-method.md)|<span data-ttu-id="062eb-108">`ICorDebugStepper`현재 위치에서 시작 하 여 열거형에서 지정 된 수의 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="062eb-108">Gets the specified number of `ICorDebugStepper` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="062eb-109">설명</span><span class="sxs-lookup"><span data-stu-id="062eb-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="062eb-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="062eb-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="062eb-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="062eb-111">Requirements</span></span>  

 <span data-ttu-id="062eb-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="062eb-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="062eb-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="062eb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="062eb-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="062eb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="062eb-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="062eb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="062eb-116">참조</span><span class="sxs-lookup"><span data-stu-id="062eb-116">See also</span></span>

- [<span data-ttu-id="062eb-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="062eb-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
