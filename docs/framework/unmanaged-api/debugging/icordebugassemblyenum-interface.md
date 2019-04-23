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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7fef4d757cf528cd3dc7d79db04d33c2cad9bbf1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59189845"
---
# <a name="icordebugassemblyenum-interface"></a><span data-ttu-id="298cb-102">ICorDebugAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="298cb-102">ICorDebugAssemblyEnum Interface</span></span>

<span data-ttu-id="298cb-103">ICorDebugEnum 메서드를 구현 하 고 ICorDebugAssembly 배열을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="298cb-103">Implements ICorDebugEnum methods and enumerates ICorDebugAssembly arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="298cb-104">메서드</span><span class="sxs-lookup"><span data-stu-id="298cb-104">Methods</span></span>  
  
|<span data-ttu-id="298cb-105">메서드</span><span class="sxs-lookup"><span data-stu-id="298cb-105">Method</span></span>|<span data-ttu-id="298cb-106">설명</span><span class="sxs-lookup"><span data-stu-id="298cb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="298cb-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="298cb-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassemblyenum-next-method.md)|<span data-ttu-id="298cb-108">지정 된 수를 가져옵니다 `ICorDebugAssembly` 현재 위치에서 시작 하는 열거형의 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="298cb-108">Gets the specified number of `ICorDebugAssembly` instances in the enumeration, starting from the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="298cb-109">설명</span><span class="sxs-lookup"><span data-stu-id="298cb-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="298cb-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="298cb-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="298cb-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="298cb-111">Requirements</span></span>  
 <span data-ttu-id="298cb-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="298cb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="298cb-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="298cb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="298cb-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="298cb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="298cb-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="298cb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="298cb-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="298cb-116">See also</span></span>

- [<span data-ttu-id="298cb-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="298cb-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
