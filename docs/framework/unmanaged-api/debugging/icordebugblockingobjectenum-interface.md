---
description: '자세히 알아보기: ICorDebugBlockingObjectEnum 인터페이스'
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
ms.openlocfilehash: 4f28039cb8a9bdcb376a9acf22572d29e41a2adf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754071"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="df310-103">ICorDebugBlockingObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="df310-103">ICorDebugBlockingObjectEnum Interface</span></span>

<span data-ttu-id="df310-104">[CorDebugBlockingObject](cordebugblockingobject-structure.md) 구조체의 목록에 대 한 열거자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="df310-104">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="df310-105">이 인터페이스는 ICorDebugEnum 인터페이스의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="df310-105">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="df310-106">메서드</span><span class="sxs-lookup"><span data-stu-id="df310-106">Methods</span></span>  
  
|<span data-ttu-id="df310-107">메서드</span><span class="sxs-lookup"><span data-stu-id="df310-107">Method</span></span>|<span data-ttu-id="df310-108">설명</span><span class="sxs-lookup"><span data-stu-id="df310-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="df310-109">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="df310-109">Next Method</span></span>](icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="df310-110">[CorDebugBlockingObject](cordebugblockingobject-structure.md) 구조체 목록을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="df310-110">Enumerates through a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df310-111">설명</span><span class="sxs-lookup"><span data-stu-id="df310-111">Remarks</span></span>  

 <span data-ttu-id="df310-112">각 `CorDebugBlockingObject` 구조체는 스레드를 차단하는 개체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="df310-112">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="df310-113">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="df310-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df310-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="df310-114">Requirements</span></span>  

 <span data-ttu-id="df310-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df310-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df310-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df310-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df310-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df310-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df310-118">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df310-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df310-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="df310-119">See also</span></span>

- [<span data-ttu-id="df310-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="df310-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="df310-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="df310-121">Debugging</span></span>](index.md)
