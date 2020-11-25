---
title: ICorDebugAssemblyEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugAssemblyEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssemblyEnum
helpviewer_keywords:
- ICorDebugAssemblyEnum interface [.NET Framework debugging]
ms.assetid: 891ceb43-5161-421e-a0bf-299962fd7efd
topic_type:
- apiref
ms.openlocfilehash: dea5c0fd5d4ed1f830d9e75097d49c544dac2e57
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719249"
---
# <a name="icordebugassemblyenum-interface"></a><span data-ttu-id="2e21c-102">ICorDebugAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2e21c-102">ICorDebugAssemblyEnum Interface</span></span>

<span data-ttu-id="2e21c-103">ICorDebugEnum 메서드를 구현 하 고 ICorDebugAssembly 배열을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e21c-103">Implements ICorDebugEnum methods and enumerates ICorDebugAssembly arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2e21c-104">메서드</span><span class="sxs-lookup"><span data-stu-id="2e21c-104">Methods</span></span>  
  
|<span data-ttu-id="2e21c-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2e21c-105">Method</span></span>|<span data-ttu-id="2e21c-106">설명</span><span class="sxs-lookup"><span data-stu-id="2e21c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2e21c-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="2e21c-107">Next Method</span></span>](icordebugassemblyenum-next-method.md)|<span data-ttu-id="2e21c-108">`ICorDebugAssembly`현재 위치에서 시작 하 여 열거형의 지정 된 수의 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2e21c-108">Gets the specified number of `ICorDebugAssembly` instances in the enumeration, starting from the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e21c-109">설명</span><span class="sxs-lookup"><span data-stu-id="2e21c-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2e21c-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e21c-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e21c-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2e21c-111">Requirements</span></span>  

 <span data-ttu-id="2e21c-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2e21c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e21c-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2e21c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2e21c-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e21c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e21c-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e21c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e21c-116">참조</span><span class="sxs-lookup"><span data-stu-id="2e21c-116">See also</span></span>

- [<span data-ttu-id="2e21c-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2e21c-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
