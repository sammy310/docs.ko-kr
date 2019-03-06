---
title: ICorDebug::EnumerateProcesses 메서드
ms.date: 03/30/2017
api_name:
- ICorDebug.EnumerateProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- EnumerateProcesses
helpviewer_keywords:
- EnumerateProcesses method [.NET Framework debugging]
- ICorDebug::EnumerateProcesses method [.NET Framework debugging]
ms.assetid: ba25d166-1d28-4f1d-aca2-de298bbca669
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ecf5160a7ceb7a4d2f1d64d83f573f8450966dc0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476674"
---
# <a name="icordebugenumerateprocesses-method"></a><span data-ttu-id="22899-102">ICorDebug::EnumerateProcesses 메서드</span><span class="sxs-lookup"><span data-stu-id="22899-102">ICorDebug::EnumerateProcesses Method</span></span>
<span data-ttu-id="22899-103">디버그 중인 프로세스에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="22899-103">Gets an enumerator for the processes that are being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22899-104">구문</span><span class="sxs-lookup"><span data-stu-id="22899-104">Syntax</span></span>  
  
```  
HRESULT EnumerateProcesses (  
    [out] ICorDebugProcessEnum      **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22899-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="22899-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="22899-106">디버깅 중인 프로세스에 대 한 열거자는 ICorDebugProcessEnum 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="22899-106">A pointer to the address of an ICorDebugProcessEnum object that is the enumerator for the processes being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22899-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="22899-107">Requirements</span></span>  
 <span data-ttu-id="22899-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="22899-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22899-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22899-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22899-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22899-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22899-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22899-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22899-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="22899-112">See also</span></span>
- [<span data-ttu-id="22899-113">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="22899-113">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
