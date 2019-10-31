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
ms.openlocfilehash: 3c62bd73b693322bd679b07b46e3549e1cfc8a56
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133394"
---
# <a name="icordebugthreadgetregisterset-method"></a><span data-ttu-id="a0752-102">ICorDebugThread::GetRegisterSet 메서드</span><span class="sxs-lookup"><span data-stu-id="a0752-102">ICorDebugThread::GetRegisterSet Method</span></span>
<span data-ttu-id="a0752-103">이 ICorDebugThread 개체의 활성 부분과 연결 된 레지스터 집합에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a0752-103">Gets an interface pointer to the register set that is associated with the active part of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0752-104">구문</span><span class="sxs-lookup"><span data-stu-id="a0752-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0752-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a0752-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="a0752-106">제한이 이 스레드의 활성 부분에 대 한 레지스터 집합을 나타내는 [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interface 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a0752-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interface object that represents the register set for the active part of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0752-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a0752-107">Requirements</span></span>  
 <span data-ttu-id="a0752-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a0752-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0752-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0752-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0752-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0752-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0752-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0752-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
