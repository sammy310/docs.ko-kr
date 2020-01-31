---
title: ICorDebugILFrame3 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 15212cb5-93d4-4025-bec9-d4b9919eb1fe
topic_type:
- apiref
ms.openlocfilehash: 739c648173d45a9c147ea2a4e469a3a4b518e893
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794344"
---
# <a name="icordebugilframe3-interface"></a><span data-ttu-id="47c5e-102">ICorDebugILFrame3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="47c5e-102">ICorDebugILFrame3 Interface</span></span>
<span data-ttu-id="47c5e-103">함수의 반환 값을 캡슐화하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="47c5e-103">Provides a method that encapsulates the return value of a function.</span></span> <span data-ttu-id="47c5e-104">`ICorDebugILFrame3`은 ICorDebugILFrame 및 ICorDebugILFrame2 인터페이스의 논리적 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="47c5e-104">`ICorDebugILFrame3` is a logical extension of the ICorDebugILFrame and ICorDebugILFrame2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="47c5e-105">메서드</span><span class="sxs-lookup"><span data-stu-id="47c5e-105">Methods</span></span>  
  
|<span data-ttu-id="47c5e-106">메서드</span><span class="sxs-lookup"><span data-stu-id="47c5e-106">Method</span></span>|<span data-ttu-id="47c5e-107">설명</span><span class="sxs-lookup"><span data-stu-id="47c5e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="47c5e-108">GetReturnValueForILOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="47c5e-108">GetReturnValueForILOffset Method</span></span>](icordebugilframe3-getreturnvalueforiloffset-method.md)|<span data-ttu-id="47c5e-109">함수의 반환 값을 캡슐화 하는 ICorDebugValue 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="47c5e-109">Gets an ICorDebugValue object that encapsulates the return value of a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47c5e-110">주의</span><span class="sxs-lookup"><span data-stu-id="47c5e-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="47c5e-111">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47c5e-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47c5e-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="47c5e-112">Requirements</span></span>  
 <span data-ttu-id="47c5e-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47c5e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47c5e-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="47c5e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="47c5e-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47c5e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47c5e-116">**.NET Framework 버전:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47c5e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47c5e-117">참조</span><span class="sxs-lookup"><span data-stu-id="47c5e-117">See also</span></span>

- [<span data-ttu-id="47c5e-118">ICorDebugCode3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="47c5e-118">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
- [<span data-ttu-id="47c5e-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="47c5e-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
