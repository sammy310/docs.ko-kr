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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bcd7bfb52cadf740d8fe3cb92a09b071f530b7ee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994333"
---
# <a name="icordebugstepperdeactivate-method"></a><span data-ttu-id="c823f-102">ICorDebugStepper::Deactivate 메서드</span><span class="sxs-lookup"><span data-stu-id="c823f-102">ICorDebugStepper::Deactivate Method</span></span>
<span data-ttu-id="c823f-103">수신 된 마지막 단계 명령을 취소 하려면이 ICorDebugStepper 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c823f-103">Causes this ICorDebugStepper to cancel the last step command that it received.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c823f-104">구문</span><span class="sxs-lookup"><span data-stu-id="c823f-104">Syntax</span></span>  
  
```  
HRESULT Deactivate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="c823f-105">설명</span><span class="sxs-lookup"><span data-stu-id="c823f-105">Remarks</span></span>  
 <span data-ttu-id="c823f-106">가장 최근에 수신한 단계 명령을 취소 된 후에 새 단계별 실행 명령을 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c823f-106">A new stepping command may be issued after the most recently received step command has been canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c823f-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c823f-107">Requirements</span></span>  
 <span data-ttu-id="c823f-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c823f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c823f-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c823f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c823f-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c823f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c823f-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c823f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
