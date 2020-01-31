---
title: ICorDebugTypeEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugTypeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugTypeEnum
helpviewer_keywords:
- ICorDebugTypeEnum interface [.NET Framework debugging]
ms.assetid: 159ccfcf-b37c-4ad9-8e0d-a9a443262472
topic_type:
- apiref
ms.openlocfilehash: ed7bceec9bf6ea0cf69cbb57fff83a91093ba6c4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791205"
---
# <a name="icordebugtypeenum-interface"></a><span data-ttu-id="6b923-102">ICorDebugTypeEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6b923-102">ICorDebugTypeEnum Interface</span></span>
<span data-ttu-id="6b923-103">"ICorDebugEnum" 메서드를 구현 하 고 "ICorDebugType" 배열을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b923-103">Implements "ICorDebugEnum" methods and enumerates "ICorDebugType" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6b923-104">메서드</span><span class="sxs-lookup"><span data-stu-id="6b923-104">Methods</span></span>  
  
|<span data-ttu-id="6b923-105">메서드</span><span class="sxs-lookup"><span data-stu-id="6b923-105">Method</span></span>|<span data-ttu-id="6b923-106">설명</span><span class="sxs-lookup"><span data-stu-id="6b923-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6b923-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="6b923-107">Next Method</span></span>](icordebugtypeenum-next-method.md)|<span data-ttu-id="6b923-108">현재 위치에서 시작 하 여 열거형에서 지정 된 수의 `ICorDebugType` 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6b923-108">Gets the specified number of `ICorDebugType` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b923-109">주의</span><span class="sxs-lookup"><span data-stu-id="6b923-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6b923-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6b923-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b923-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6b923-111">Requirements</span></span>  
 <span data-ttu-id="6b923-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b923-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b923-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b923-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b923-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b923-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b923-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b923-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b923-116">참조</span><span class="sxs-lookup"><span data-stu-id="6b923-116">See also</span></span>

- [<span data-ttu-id="6b923-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6b923-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
