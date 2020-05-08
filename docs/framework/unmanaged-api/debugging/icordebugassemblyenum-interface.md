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
ms.openlocfilehash: 988637956b1176235618bf8f4aee7ecec9ce1187
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894829"
---
# <a name="icordebugassemblyenum-interface"></a><span data-ttu-id="e6a1b-102">ICorDebugAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e6a1b-102">ICorDebugAssemblyEnum Interface</span></span>

<span data-ttu-id="e6a1b-103">ICorDebugEnum 메서드를 구현 하 고 ICorDebugAssembly 배열을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a1b-103">Implements ICorDebugEnum methods and enumerates ICorDebugAssembly arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e6a1b-104">메서드</span><span class="sxs-lookup"><span data-stu-id="e6a1b-104">Methods</span></span>  
  
|<span data-ttu-id="e6a1b-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e6a1b-105">Method</span></span>|<span data-ttu-id="e6a1b-106">설명</span><span class="sxs-lookup"><span data-stu-id="e6a1b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e6a1b-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="e6a1b-107">Next Method</span></span>](icordebugassemblyenum-next-method.md)|<span data-ttu-id="e6a1b-108">현재 위치에서 시작 하 `ICorDebugAssembly` 여 열거형의 지정 된 수의 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e6a1b-108">Gets the specified number of `ICorDebugAssembly` instances in the enumeration, starting from the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6a1b-109">설명</span><span class="sxs-lookup"><span data-stu-id="e6a1b-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e6a1b-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a1b-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6a1b-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e6a1b-111">Requirements</span></span>  
 <span data-ttu-id="e6a1b-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6a1b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6a1b-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e6a1b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6a1b-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6a1b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6a1b-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6a1b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6a1b-116">참조</span><span class="sxs-lookup"><span data-stu-id="e6a1b-116">See also</span></span>

- [<span data-ttu-id="e6a1b-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e6a1b-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
