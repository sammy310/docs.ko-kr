---
title: ICorDebugProcess::GetThread 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetThread
helpviewer_keywords:
- ICorDebugProcess::GetThread method [.NET Framework debugging]
- GetThread method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a48261ed-700b-41c9-8cb4-18c526546603
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d5cbdd19fa14a41d8bd2eadec80dbafcea7b720d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766435"
---
# <a name="icordebugprocessgetthread-method"></a><span data-ttu-id="96847-102">ICorDebugProcess::GetThread 메서드</span><span class="sxs-lookup"><span data-stu-id="96847-102">ICorDebugProcess::GetThread Method</span></span>
<span data-ttu-id="96847-103">지정 된 운영 체제 (OS) 스레드 ID가 있습니다.이 프로세스의이 스레드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="96847-103">Gets this process's thread that has the specified operating system (OS) thread ID.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96847-104">구문</span><span class="sxs-lookup"><span data-stu-id="96847-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
    [in] DWORD dwThreadId,  
    [out] ICorDebugThread **ppThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96847-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="96847-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="96847-106">[in] OS 스레드 검색할 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="96847-106">[in] The OS thread ID of the thread to be retrieved.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="96847-107">[out] 스레드를 나타내는 ICorDebugThread 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="96847-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96847-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="96847-108">Requirements</span></span>  
 <span data-ttu-id="96847-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="96847-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96847-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96847-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96847-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96847-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96847-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96847-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
