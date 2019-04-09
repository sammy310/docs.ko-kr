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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7edf103e397c6e3e1577b5ed4bc8fc0df264b843
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137997"
---
# <a name="icordebugthreadenum-interface"></a><span data-ttu-id="83e05-102">ICorDebugThreadEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="83e05-102">ICorDebugThreadEnum Interface</span></span>
<span data-ttu-id="83e05-103">ICorDebugEnum 메서드를 구현 하 고 배열 ICorDebugThread를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="83e05-103">Implements ICorDebugEnum methods and enumerates ICorDebugThread arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="83e05-104">메서드</span><span class="sxs-lookup"><span data-stu-id="83e05-104">Methods</span></span>  
  
|<span data-ttu-id="83e05-105">메서드</span><span class="sxs-lookup"><span data-stu-id="83e05-105">Method</span></span>|<span data-ttu-id="83e05-106">설명</span><span class="sxs-lookup"><span data-stu-id="83e05-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="83e05-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="83e05-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-next-method.md)|<span data-ttu-id="83e05-108">지정 된 수를 가져옵니다 `ICorDebugThread` 인스턴스는 열거형에서 현재 위치에서 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="83e05-108">Gets the specified number of `ICorDebugThread` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83e05-109">설명</span><span class="sxs-lookup"><span data-stu-id="83e05-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83e05-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83e05-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83e05-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="83e05-111">Requirements</span></span>  
 <span data-ttu-id="83e05-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="83e05-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83e05-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="83e05-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83e05-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83e05-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="83e05-115">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="83e05-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="83e05-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="83e05-116">See also</span></span>

- [<span data-ttu-id="83e05-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="83e05-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
