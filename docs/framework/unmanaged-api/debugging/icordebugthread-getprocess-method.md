---
title: ICorDebugThread::GetProcess 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetProcess
helpviewer_keywords:
- ICorDebugThread::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 163816e7-0739-4566-b3df-cd256be8b8a4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46aa2ec5a282ef56f28d5fa0499571028e6602e6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57483630"
---
# <a name="icordebugthreadgetprocess-method"></a><span data-ttu-id="3c16d-102">ICorDebugThread::GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="3c16d-102">ICorDebugThread::GetProcess Method</span></span>
<span data-ttu-id="3c16d-103">이 ICorDebugThread를 포함 하는 프로세스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3c16d-103">Gets an interface pointer to the process of which this ICorDebugThread forms a part.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c16d-104">구문</span><span class="sxs-lookup"><span data-stu-id="3c16d-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c16d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3c16d-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="3c16d-106">[out] 프로세스를 나타내는 ICorDebugProcess 인터페이스 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3c16d-106">[out] A pointer to the address of an ICorDebugProcess interface object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c16d-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3c16d-107">Requirements</span></span>  
 <span data-ttu-id="3c16d-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3c16d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c16d-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c16d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c16d-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c16d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c16d-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c16d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
