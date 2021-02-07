---
description: '자세히 알아보기: ICorDebugStepper2 인터페이스'
title: ICorDebugStepper2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugStepper2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper2
helpviewer_keywords:
- ICorDebugStepper2 interface [.NET Framework debugging]
ms.assetid: 7a191c2a-95ea-4d47-83b0-44de2b632d63
topic_type:
- apiref
ms.openlocfilehash: 31e9216535da239573a7a4ecde8cb2e670ad5418
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717552"
---
# <a name="icordebugstepper2-interface"></a><span data-ttu-id="4470a-103">ICorDebugStepper2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4470a-103">ICorDebugStepper2 Interface</span></span>

<span data-ttu-id="4470a-104">내 코드만 (JMC) 디버깅을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4470a-104">Provides support for just my code (JMC) debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4470a-105">메서드</span><span class="sxs-lookup"><span data-stu-id="4470a-105">Methods</span></span>  
  
|<span data-ttu-id="4470a-106">메서드</span><span class="sxs-lookup"><span data-stu-id="4470a-106">Method</span></span>|<span data-ttu-id="4470a-107">설명</span><span class="sxs-lookup"><span data-stu-id="4470a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4470a-108">SetJMC 메서드</span><span class="sxs-lookup"><span data-stu-id="4470a-108">SetJMC Method</span></span>](icordebugstepper2-setjmc-method.md)|<span data-ttu-id="4470a-109">이 ICorDebugStepper 응용 프로그램 개발자가 작성 한 코드를 통해서만 단계별로 진행 하는지 여부를 지정 하는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4470a-109">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4470a-110">설명</span><span class="sxs-lookup"><span data-stu-id="4470a-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4470a-111">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4470a-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4470a-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4470a-112">Requirements</span></span>  

 <span data-ttu-id="4470a-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4470a-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4470a-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4470a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4470a-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4470a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4470a-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4470a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4470a-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4470a-117">See also</span></span>

- [<span data-ttu-id="4470a-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4470a-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
