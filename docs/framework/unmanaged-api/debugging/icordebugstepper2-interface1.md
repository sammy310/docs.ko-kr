---
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
ms.openlocfilehash: ecbedfbca37a3630fc6d40c173f8a6cd05b4d3fb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727642"
---
# <a name="icordebugstepper2-interface"></a><span data-ttu-id="c1277-102">ICorDebugStepper2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c1277-102">ICorDebugStepper2 Interface</span></span>

<span data-ttu-id="c1277-103">내 코드만 (JMC) 디버깅을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1277-103">Provides support for just my code (JMC) debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c1277-104">메서드</span><span class="sxs-lookup"><span data-stu-id="c1277-104">Methods</span></span>  
  
|<span data-ttu-id="c1277-105">메서드</span><span class="sxs-lookup"><span data-stu-id="c1277-105">Method</span></span>|<span data-ttu-id="c1277-106">설명</span><span class="sxs-lookup"><span data-stu-id="c1277-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c1277-107">SetJMC 메서드</span><span class="sxs-lookup"><span data-stu-id="c1277-107">SetJMC Method</span></span>](icordebugstepper2-setjmc-method.md)|<span data-ttu-id="c1277-108">이 ICorDebugStepper 응용 프로그램 개발자가 작성 한 코드를 통해서만 단계별로 진행 하는지 여부를 지정 하는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1277-108">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1277-109">설명</span><span class="sxs-lookup"><span data-stu-id="c1277-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c1277-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1277-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1277-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c1277-111">Requirements</span></span>  

 <span data-ttu-id="c1277-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1277-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1277-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c1277-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c1277-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1277-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1277-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1277-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1277-116">참조</span><span class="sxs-lookup"><span data-stu-id="c1277-116">See also</span></span>

- [<span data-ttu-id="c1277-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c1277-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
