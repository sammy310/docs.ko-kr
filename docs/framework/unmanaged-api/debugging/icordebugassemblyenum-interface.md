---
title: ICorDebugAssemblyEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugAssemblyEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssemblyEnum
helpviewer_keywords:
- ICorDebugAssemblyEnum interface [.NET Framework debugging]
ms.assetid: 891ceb43-5161-421e-a0bf-299962fd7efd
topic_type:
- apiref
ms.openlocfilehash: 1893f1f08d727606fecda7669719760179bb76f9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778053"
---
# <a name="icordebugassemblyenum-interface"></a><span data-ttu-id="a6728-102">ICorDebugAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a6728-102">ICorDebugAssemblyEnum Interface</span></span>

<span data-ttu-id="a6728-103">ICorDebugEnum 메서드를 구현 하 고 ICorDebugAssembly 배열을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6728-103">Implements ICorDebugEnum methods and enumerates ICorDebugAssembly arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a6728-104">메서드</span><span class="sxs-lookup"><span data-stu-id="a6728-104">Methods</span></span>  
  
|<span data-ttu-id="a6728-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a6728-105">Method</span></span>|<span data-ttu-id="a6728-106">설명</span><span class="sxs-lookup"><span data-stu-id="a6728-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a6728-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="a6728-107">Next Method</span></span>](icordebugassemblyenum-next-method.md)|<span data-ttu-id="a6728-108">현재 위치에서 시작 하 여 열거형에서 지정 된 수의 `ICorDebugAssembly` 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a6728-108">Gets the specified number of `ICorDebugAssembly` instances in the enumeration, starting from the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6728-109">주의</span><span class="sxs-lookup"><span data-stu-id="a6728-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a6728-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6728-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6728-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a6728-111">Requirements</span></span>  
 <span data-ttu-id="a6728-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a6728-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6728-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6728-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6728-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6728-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6728-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6728-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6728-116">참조</span><span class="sxs-lookup"><span data-stu-id="a6728-116">See also</span></span>

- [<span data-ttu-id="a6728-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a6728-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
