---
title: ICorDebugThreadEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugThreadEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum
helpviewer_keywords:
- ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: 796de687-7dd4-4b7b-a10b-8bf22dc7779f
topic_type:
- apiref
ms.openlocfilehash: 6de2cb7c1a1423c5bd38a6f2e5d01c39166ab119
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791326"
---
# <a name="icordebugthreadenum-interface"></a><span data-ttu-id="b43e0-102">ICorDebugThreadEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b43e0-102">ICorDebugThreadEnum Interface</span></span>
<span data-ttu-id="b43e0-103">ICorDebugEnum 메서드를 구현 하 고 ICorDebugThread 배열을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43e0-103">Implements ICorDebugEnum methods and enumerates ICorDebugThread arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b43e0-104">메서드</span><span class="sxs-lookup"><span data-stu-id="b43e0-104">Methods</span></span>  
  
|<span data-ttu-id="b43e0-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b43e0-105">Method</span></span>|<span data-ttu-id="b43e0-106">설명</span><span class="sxs-lookup"><span data-stu-id="b43e0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b43e0-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="b43e0-107">Next Method</span></span>](icordebugthreadenum-next-method.md)|<span data-ttu-id="b43e0-108">현재 위치에서 시작 하 여 열거형에서 지정 된 수의 `ICorDebugThread` 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b43e0-108">Gets the specified number of `ICorDebugThread` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b43e0-109">주의</span><span class="sxs-lookup"><span data-stu-id="b43e0-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b43e0-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b43e0-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b43e0-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b43e0-111">Requirements</span></span>  
 <span data-ttu-id="b43e0-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b43e0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b43e0-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b43e0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b43e0-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b43e0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b43e0-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b43e0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b43e0-116">참조</span><span class="sxs-lookup"><span data-stu-id="b43e0-116">See also</span></span>

- [<span data-ttu-id="b43e0-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b43e0-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
