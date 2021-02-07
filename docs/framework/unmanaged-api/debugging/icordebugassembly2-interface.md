---
description: '자세히 알아보기: ICorDebugAssembly2 인터페이스'
title: ICorDebugAssembly2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly2
helpviewer_keywords:
- ICorDebugAssembly2 interface [.NET Framework debugging]
ms.assetid: c0766e29-e573-4f9a-a928-167d1de5aa7e
topic_type:
- apiref
ms.openlocfilehash: 2a2d035329ba66153bfee83daa9501581f32842f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754123"
---
# <a name="icordebugassembly2-interface"></a><span data-ttu-id="a6d66-103">ICorDebugAssembly2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a6d66-103">ICorDebugAssembly2 Interface</span></span>

<span data-ttu-id="a6d66-104">어셈블리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a6d66-104">Represents an assembly.</span></span> <span data-ttu-id="a6d66-105">이 인터페이스는 ICorDebugAssembly 인터페이스의 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="a6d66-105">This interface is an extension of the ICorDebugAssembly interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a6d66-106">메서드</span><span class="sxs-lookup"><span data-stu-id="a6d66-106">Methods</span></span>  
  
|<span data-ttu-id="a6d66-107">메서드</span><span class="sxs-lookup"><span data-stu-id="a6d66-107">Method</span></span>|<span data-ttu-id="a6d66-108">설명</span><span class="sxs-lookup"><span data-stu-id="a6d66-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a6d66-109">IsFullyTrusted 메서드</span><span class="sxs-lookup"><span data-stu-id="a6d66-109">IsFullyTrusted Method</span></span>](icordebugassembly2-isfullytrusted-method.md)|<span data-ttu-id="a6d66-110">어셈블리에 런타임 보안 시스템에서 완전 신뢰를 부여 했는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a6d66-110">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6d66-111">설명</span><span class="sxs-lookup"><span data-stu-id="a6d66-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a6d66-112">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6d66-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6d66-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a6d66-113">Requirements</span></span>  

 <span data-ttu-id="a6d66-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a6d66-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6d66-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6d66-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6d66-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6d66-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6d66-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6d66-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6d66-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a6d66-118">See also</span></span>

- [<span data-ttu-id="a6d66-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a6d66-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
