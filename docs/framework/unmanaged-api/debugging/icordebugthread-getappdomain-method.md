---
title: ICorDebugThread::GetAppDomain 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetAppDomain
helpviewer_keywords:
- GetAppDomain method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetAppDomain method [.NET Framework debugging]
ms.assetid: 415b3d34-8b35-4b60-a318-140646cc83f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da473ed176ab6c69ed974d5f28b22fc8eb30c6af
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762524"
---
# <a name="icordebugthreadgetappdomain-method"></a><span data-ttu-id="ec1f9-102">ICorDebugThread::GetAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="ec1f9-102">ICorDebugThread::GetAppDomain Method</span></span>
<span data-ttu-id="ec1f9-103">이 ICorDebugThread이 현재 실행 되는 응용 프로그램 도메인에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ec1f9-103">Gets an interface pointer to the application domain in which this ICorDebugThread is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec1f9-104">구문</span><span class="sxs-lookup"><span data-stu-id="ec1f9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec1f9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ec1f9-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="ec1f9-106">[out] 이 스레드가 현재 실행 되는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ec1f9-106">[out] A pointer to an ICorDebugAppDomain object that represents the application domain in which this thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec1f9-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ec1f9-107">Requirements</span></span>  
 <span data-ttu-id="ec1f9-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ec1f9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec1f9-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ec1f9-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ec1f9-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec1f9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec1f9-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec1f9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
