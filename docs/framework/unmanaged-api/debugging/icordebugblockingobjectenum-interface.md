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
ms.openlocfilehash: 221acf9bea714728a81b9f15c8165c1f9eba16a8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719205"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="c1768-102">ICorDebugBlockingObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c1768-102">ICorDebugBlockingObjectEnum Interface</span></span>

<span data-ttu-id="c1768-103">[CorDebugBlockingObject](cordebugblockingobject-structure.md) 구조체의 목록에 대 한 열거자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1768-103">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="c1768-104">이 인터페이스는 ICorDebugEnum 인터페이스의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c1768-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c1768-105">메서드</span><span class="sxs-lookup"><span data-stu-id="c1768-105">Methods</span></span>  
  
|<span data-ttu-id="c1768-106">메서드</span><span class="sxs-lookup"><span data-stu-id="c1768-106">Method</span></span>|<span data-ttu-id="c1768-107">설명</span><span class="sxs-lookup"><span data-stu-id="c1768-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c1768-108">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="c1768-108">Next Method</span></span>](icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="c1768-109">[CorDebugBlockingObject](cordebugblockingobject-structure.md) 구조체 목록을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1768-109">Enumerates through a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1768-110">설명</span><span class="sxs-lookup"><span data-stu-id="c1768-110">Remarks</span></span>  

 <span data-ttu-id="c1768-111">각 `CorDebugBlockingObject` 구조체는 스레드를 차단하는 개체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c1768-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c1768-112">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1768-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1768-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c1768-113">Requirements</span></span>  

 <span data-ttu-id="c1768-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1768-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1768-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c1768-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c1768-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1768-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1768-117">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1768-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1768-118">참조</span><span class="sxs-lookup"><span data-stu-id="c1768-118">See also</span></span>

- [<span data-ttu-id="c1768-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c1768-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c1768-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="c1768-120">Debugging</span></span>](index.md)
