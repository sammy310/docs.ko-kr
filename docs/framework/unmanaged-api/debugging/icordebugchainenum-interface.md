---
title: ICorDebugChainEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugChainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChainEnum
helpviewer_keywords:
- ICorDebugChainEnum interface [.NET Framework debugging]
ms.assetid: 6639335c-48e1-4e74-a4f3-70a6a0f54af1
topic_type:
- apiref
ms.openlocfilehash: 1f94e2e1f6b376a1998ba4fbcc940147eb16272a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784201"
---
# <a name="icordebugchainenum-interface"></a><span data-ttu-id="3443a-102">ICorDebugChainEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3443a-102">ICorDebugChainEnum Interface</span></span>

<span data-ttu-id="3443a-103">ICorDebugEnum 메서드를 구현 하 고 ICorDebugChain 배열을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="3443a-103">Implements ICorDebugEnum methods, and enumerates ICorDebugChain arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3443a-104">메서드</span><span class="sxs-lookup"><span data-stu-id="3443a-104">Methods</span></span>  
  
|<span data-ttu-id="3443a-105">메서드</span><span class="sxs-lookup"><span data-stu-id="3443a-105">Method</span></span>|<span data-ttu-id="3443a-106">설명</span><span class="sxs-lookup"><span data-stu-id="3443a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3443a-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="3443a-107">Next Method</span></span>](icordebugchainenum-next-method.md)|<span data-ttu-id="3443a-108">현재 위치에서 시작 하 여 열거형에서 지정 된 수의 `ICorDebugChain` 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3443a-108">Gets the specified number of `ICorDebugChain` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3443a-109">주의</span><span class="sxs-lookup"><span data-stu-id="3443a-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3443a-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3443a-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3443a-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3443a-111">Requirements</span></span>  
 <span data-ttu-id="3443a-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3443a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3443a-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3443a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3443a-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3443a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3443a-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3443a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3443a-116">참조</span><span class="sxs-lookup"><span data-stu-id="3443a-116">See also</span></span>

- [<span data-ttu-id="3443a-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3443a-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
