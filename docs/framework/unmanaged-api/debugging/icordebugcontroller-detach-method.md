---
title: ICorDebugController::Detach 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugController.Detach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Detach
helpviewer_keywords:
- Detach method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Detach method [.NET Framework debugging]
ms.assetid: 06fae364-f2c6-4a50-aa7e-3da9f2684dc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85a9bde77f7c393756ec1d3e7d30b96392aa6a94
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61749633"
---
# <a name="icordebugcontrollerdetach-method"></a><span data-ttu-id="af3a2-102">ICorDebugController::Detach 메서드</span><span class="sxs-lookup"><span data-stu-id="af3a2-102">ICorDebugController::Detach Method</span></span>
<span data-ttu-id="af3a2-103">프로세스 또는 응용 프로그램 도메인에서 디버거를 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="af3a2-103">Detaches the debugger from the process or application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af3a2-104">구문</span><span class="sxs-lookup"><span data-stu-id="af3a2-104">Syntax</span></span>  
  
```  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="af3a2-105">설명</span><span class="sxs-lookup"><span data-stu-id="af3a2-105">Remarks</span></span>  
 <span data-ttu-id="af3a2-106">프로세스 또는 응용 프로그램 도메인 실행을 일반적으로 계속 하지만 "ICorDebugProcess" 또는 "ICorDebugAppDomain" 개체를 더 이상 유효 하 고 없습니다 추가 콜백이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="af3a2-106">The process or application domain continues execution normally, but the "ICorDebugProcess" or "ICorDebugAppDomain" object is no longer valid and no further callbacks will occur.</span></span>  
  
 <span data-ttu-id="af3a2-107">.NET framework 버전 2.0에서 관리 되지 않는 디버깅을 사용 하도록 설정 하는 경우 운영 체제 제한으로 인해이 메서드가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="af3a2-107">In the .NET Framework version 2.0, if unmanaged debugging is enabled, this method will fail due to operating system limitations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af3a2-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="af3a2-108">Requirements</span></span>  
 <span data-ttu-id="af3a2-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="af3a2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af3a2-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af3a2-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af3a2-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af3a2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af3a2-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af3a2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af3a2-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="af3a2-113">See also</span></span>
