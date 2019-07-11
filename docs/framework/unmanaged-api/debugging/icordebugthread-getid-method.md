---
title: ICorDebugThread::GetID 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetID
helpviewer_keywords:
- ICorDebugThread::GetID method [.NET Framework debugging]
- GetID method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: f1de4584-92df-42f3-9da4-fca03a1c6821
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 11e21e913e4749705ba6c7f91016be21b4de1712
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769972"
---
# <a name="icordebugthreadgetid-method"></a><span data-ttu-id="98213-102">ICorDebugThread::GetID 메서드</span><span class="sxs-lookup"><span data-stu-id="98213-102">ICorDebugThread::GetID Method</span></span>
<span data-ttu-id="98213-103">이 ICorDebugThread의 활성 부분의 현재 운영 체제 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="98213-103">Gets the current operating system identifier of the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98213-104">구문</span><span class="sxs-lookup"><span data-stu-id="98213-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] DWORD *pdwThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98213-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="98213-105">Parameters</span></span>  
 `pdwThreadId`  
 <span data-ttu-id="98213-106">[out] 스레드 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="98213-106">[out] The identifier of the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98213-107">설명</span><span class="sxs-lookup"><span data-stu-id="98213-107">Remarks</span></span>  
 <span data-ttu-id="98213-108">운영 체제 식별자는 프로세스를 실행 하는 동안 변경 될 수 있습니다 및 다른 스레드의 다른 부분에 대 한 값일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98213-108">The operating system identifier can potentially change during execution of a process, and can be a different value for different parts of the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98213-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="98213-109">Requirements</span></span>  
 <span data-ttu-id="98213-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="98213-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98213-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98213-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98213-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98213-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98213-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98213-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
