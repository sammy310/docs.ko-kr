---
description: '자세히 알아보기: ICorDebugChainEnum 인터페이스'
title: ICorDebugChainEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugChainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChainEnum
helpviewer_keywords:
- ICorDebugChainEnum interface [.NET Framework debugging]
ms.assetid: 6639335c-48e1-4e74-a4f3-70a6a0f54af1
topic_type:
- apiref
ms.openlocfilehash: 948bca1e01a49e7cd2e3fbadca7e3957e5ce38c0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661160"
---
# <a name="icordebugchainenum-interface"></a><span data-ttu-id="7ee0b-103">ICorDebugChainEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7ee0b-103">ICorDebugChainEnum Interface</span></span>

<span data-ttu-id="7ee0b-104">ICorDebugEnum 메서드를 구현 하 고 ICorDebugChain 배열을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ee0b-104">Implements ICorDebugEnum methods, and enumerates ICorDebugChain arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7ee0b-105">메서드</span><span class="sxs-lookup"><span data-stu-id="7ee0b-105">Methods</span></span>  
  
|<span data-ttu-id="7ee0b-106">메서드</span><span class="sxs-lookup"><span data-stu-id="7ee0b-106">Method</span></span>|<span data-ttu-id="7ee0b-107">설명</span><span class="sxs-lookup"><span data-stu-id="7ee0b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7ee0b-108">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="7ee0b-108">Next Method</span></span>](icordebugchainenum-next-method.md)|<span data-ttu-id="7ee0b-109">`ICorDebugChain`현재 위치에서 시작 하 여 열거형에서 지정 된 수의 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7ee0b-109">Gets the specified number of `ICorDebugChain` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ee0b-110">설명</span><span class="sxs-lookup"><span data-stu-id="7ee0b-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7ee0b-111">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7ee0b-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ee0b-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7ee0b-112">Requirements</span></span>  

 <span data-ttu-id="7ee0b-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7ee0b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ee0b-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ee0b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ee0b-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ee0b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ee0b-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ee0b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ee0b-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7ee0b-117">See also</span></span>

- [<span data-ttu-id="7ee0b-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7ee0b-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
