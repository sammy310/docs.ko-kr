---
title: ICorDebugBlockingObjectEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum
helpviewer_keywords:
- ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
ms.assetid: 208e5c2d-3f3f-404e-8b3c-7cccc14ddb16
topic_type:
- apiref
ms.openlocfilehash: be1e1cd0d38ad71de43478af5565bb1ac98a8c0d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778008"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="94c61-102">ICorDebugBlockingObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="94c61-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="94c61-103">[CorDebugBlockingObject](cordebugblockingobject-structure.md) 구조체의 목록에 대 한 열거자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="94c61-103">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="94c61-104">이 인터페이스는 ICorDebugEnum 인터페이스의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="94c61-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="94c61-105">메서드</span><span class="sxs-lookup"><span data-stu-id="94c61-105">Methods</span></span>  
  
|<span data-ttu-id="94c61-106">메서드</span><span class="sxs-lookup"><span data-stu-id="94c61-106">Method</span></span>|<span data-ttu-id="94c61-107">설명</span><span class="sxs-lookup"><span data-stu-id="94c61-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="94c61-108">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="94c61-108">Next Method</span></span>](icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="94c61-109">[CorDebugBlockingObject](cordebugblockingobject-structure.md) 구조체 목록을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="94c61-109">Enumerates through a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94c61-110">주의</span><span class="sxs-lookup"><span data-stu-id="94c61-110">Remarks</span></span>  
 <span data-ttu-id="94c61-111">각 `CorDebugBlockingObject` 구조체는 스레드를 차단하는 개체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="94c61-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="94c61-112">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94c61-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94c61-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="94c61-113">Requirements</span></span>  
 <span data-ttu-id="94c61-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94c61-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94c61-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94c61-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94c61-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94c61-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94c61-117">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94c61-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94c61-118">참조</span><span class="sxs-lookup"><span data-stu-id="94c61-118">See also</span></span>

- [<span data-ttu-id="94c61-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="94c61-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="94c61-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="94c61-120">Debugging</span></span>](index.md)
