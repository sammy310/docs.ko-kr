---
title: ICorDebugThread::GetRegisterSet 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetRegisterSet
helpviewer_keywords:
- ICorDebugThread::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3b9b6260-98ac-4cfd-88e5-5d7614f94a0c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 909bcad035516c494d1f867b71bb8f52939eba13
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993995"
---
# <a name="icordebugthreadgetregisterset-method"></a><span data-ttu-id="4334c-102">ICorDebugThread::GetRegisterSet 메서드</span><span class="sxs-lookup"><span data-stu-id="4334c-102">ICorDebugThread::GetRegisterSet Method</span></span>
<span data-ttu-id="4334c-103">이 ICorDebugThread 개체의 활성 부분을 사용 하 여 연결 된 등록 집합에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4334c-103">Gets an interface pointer to the register set that is associated with the active part of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4334c-104">구문</span><span class="sxs-lookup"><span data-stu-id="4334c-104">Syntax</span></span>  
  
```  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4334c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4334c-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="4334c-106">[out] 주소에 대 한 포인터를 [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) 이 스레드가의 활성 부분에 대 한 등록을 나타내는 인터페이스 개체로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4334c-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interface object that represents the register set for the active part of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4334c-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4334c-107">Requirements</span></span>  
 <span data-ttu-id="4334c-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4334c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4334c-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4334c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4334c-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4334c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4334c-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4334c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
