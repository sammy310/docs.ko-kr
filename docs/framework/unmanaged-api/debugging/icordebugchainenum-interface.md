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
ms.openlocfilehash: dd2507bb66e036dfbb1f4e8cc262f01d926adca1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728227"
---
# <a name="icordebugchainenum-interface"></a><span data-ttu-id="5e7fd-102">ICorDebugChainEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5e7fd-102">ICorDebugChainEnum Interface</span></span>

<span data-ttu-id="5e7fd-103">ICorDebugEnum 메서드를 구현 하 고 ICorDebugChain 배열을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7fd-103">Implements ICorDebugEnum methods, and enumerates ICorDebugChain arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5e7fd-104">메서드</span><span class="sxs-lookup"><span data-stu-id="5e7fd-104">Methods</span></span>  
  
|<span data-ttu-id="5e7fd-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5e7fd-105">Method</span></span>|<span data-ttu-id="5e7fd-106">설명</span><span class="sxs-lookup"><span data-stu-id="5e7fd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5e7fd-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="5e7fd-107">Next Method</span></span>](icordebugchainenum-next-method.md)|<span data-ttu-id="5e7fd-108">`ICorDebugChain`현재 위치에서 시작 하 여 열거형에서 지정 된 수의 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5e7fd-108">Gets the specified number of `ICorDebugChain` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e7fd-109">설명</span><span class="sxs-lookup"><span data-stu-id="5e7fd-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5e7fd-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e7fd-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e7fd-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5e7fd-111">Requirements</span></span>  

 <span data-ttu-id="5e7fd-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5e7fd-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e7fd-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e7fd-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e7fd-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e7fd-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e7fd-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e7fd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e7fd-116">참조</span><span class="sxs-lookup"><span data-stu-id="5e7fd-116">See also</span></span>

- [<span data-ttu-id="5e7fd-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5e7fd-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
