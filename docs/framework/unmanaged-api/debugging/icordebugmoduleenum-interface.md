---
description: '자세히 알아보기: ICorDebugModuleEnum 인터페이스'
title: ICorDebugModuleEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum
helpviewer_keywords:
- ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 2fb93cd6-6d47-4fdc-a9a0-047726fd03a1
topic_type:
- apiref
ms.openlocfilehash: c9c847f926984ed2b8aea87463e351cd97a62c80
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801048"
---
# <a name="icordebugmoduleenum-interface"></a><span data-ttu-id="c2407-103">ICorDebugModuleEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2407-103">ICorDebugModuleEnum Interface</span></span>

<span data-ttu-id="c2407-104">ICorDebugEnum 메서드를 구현 하 고 ICorDebugModule 배열을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2407-104">Implements ICorDebugEnum methods, and enumerates ICorDebugModule arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c2407-105">메서드</span><span class="sxs-lookup"><span data-stu-id="c2407-105">Methods</span></span>  
  
|<span data-ttu-id="c2407-106">메서드</span><span class="sxs-lookup"><span data-stu-id="c2407-106">Method</span></span>|<span data-ttu-id="c2407-107">설명</span><span class="sxs-lookup"><span data-stu-id="c2407-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c2407-108">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="c2407-108">Next Method</span></span>](icordebugmoduleenum-next-method.md)|<span data-ttu-id="c2407-109">`ICorDebugModule`현재 위치에서 시작 하 여 열거형에서 지정 된 수의 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c2407-109">Gets the specified number of `ICorDebugModule` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2407-110">설명</span><span class="sxs-lookup"><span data-stu-id="c2407-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c2407-111">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2407-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2407-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c2407-112">Requirements</span></span>  

 <span data-ttu-id="c2407-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2407-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2407-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2407-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2407-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2407-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2407-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2407-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2407-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c2407-117">See also</span></span>

- [<span data-ttu-id="c2407-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2407-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
