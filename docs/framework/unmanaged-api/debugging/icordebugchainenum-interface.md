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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d8a64b7dcaf4758cba217be06fa7d09f6c76920
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072958"
---
# <a name="icordebugchainenum-interface"></a><span data-ttu-id="7c71b-102">ICorDebugChainEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7c71b-102">ICorDebugChainEnum Interface</span></span>

<span data-ttu-id="7c71b-103">ICorDebugEnum 메서드를 구현 하 고 ICorDebugChain 배열을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c71b-103">Implements ICorDebugEnum methods, and enumerates ICorDebugChain arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7c71b-104">메서드</span><span class="sxs-lookup"><span data-stu-id="7c71b-104">Methods</span></span>  
  
|<span data-ttu-id="7c71b-105">메서드</span><span class="sxs-lookup"><span data-stu-id="7c71b-105">Method</span></span>|<span data-ttu-id="7c71b-106">설명</span><span class="sxs-lookup"><span data-stu-id="7c71b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7c71b-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="7c71b-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchainenum-next-method.md)|<span data-ttu-id="7c71b-108">지정 된 수를 가져옵니다 `ICorDebugChain` 인스턴스는 열거형에서 현재 위치에서 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c71b-108">Gets the specified number of `ICorDebugChain` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c71b-109">설명</span><span class="sxs-lookup"><span data-stu-id="7c71b-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7c71b-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c71b-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c71b-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7c71b-111">Requirements</span></span>  
 <span data-ttu-id="7c71b-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7c71b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c71b-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c71b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c71b-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c71b-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="7c71b-115">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="7c71b-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7c71b-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="7c71b-116">See also</span></span>

- [<span data-ttu-id="7c71b-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7c71b-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
