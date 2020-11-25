---
title: ICorDebugStepper::Deactivate 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Deactivate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Deactivate
helpviewer_keywords:
- Deactivate method [.NET Framework debugging]
- ICorDebugStepper::Deactivate method [.NET Framework debugging]
ms.assetid: 855f4199-b62d-40ce-998e-1eb4a1772142
topic_type:
- apiref
ms.openlocfilehash: 0d7d5e7e6c9bc1a68feda85c5214f3ae95df9b97
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730593"
---
# <a name="icordebugstepperdeactivate-method"></a><span data-ttu-id="ed4c3-102">ICorDebugStepper::Deactivate 메서드</span><span class="sxs-lookup"><span data-stu-id="ed4c3-102">ICorDebugStepper::Deactivate Method</span></span>

<span data-ttu-id="ed4c3-103">이 ICorDebugStepper에서 받은 마지막 단계 명령을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed4c3-103">Causes this ICorDebugStepper to cancel the last step command that it received.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed4c3-104">구문</span><span class="sxs-lookup"><span data-stu-id="ed4c3-104">Syntax</span></span>  
  
```cpp  
HRESULT Deactivate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="ed4c3-105">설명</span><span class="sxs-lookup"><span data-stu-id="ed4c3-105">Remarks</span></span>  

 <span data-ttu-id="ed4c3-106">가장 최근에 받은 단계 명령이 취소 된 후에 새 단계별 실행 명령이 실행 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed4c3-106">A new stepping command may be issued after the most recently received step command has been canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed4c3-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ed4c3-107">Requirements</span></span>  

 <span data-ttu-id="ed4c3-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed4c3-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed4c3-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ed4c3-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ed4c3-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed4c3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed4c3-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed4c3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
