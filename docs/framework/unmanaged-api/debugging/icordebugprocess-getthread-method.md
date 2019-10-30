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
ms.openlocfilehash: 6bf73a4be40f1fbd8e9d37477907001604e8e4a6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128816"
---
# <a name="icordebugprocessgetthread-method"></a><span data-ttu-id="52002-102">ICorDebugProcess::GetThread 메서드</span><span class="sxs-lookup"><span data-stu-id="52002-102">ICorDebugProcess::GetThread Method</span></span>
<span data-ttu-id="52002-103">지정 된 OS (운영 체제) 스레드 ID를 포함 하는이 프로세스의 스레드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="52002-103">Gets this process's thread that has the specified operating system (OS) thread ID.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52002-104">구문</span><span class="sxs-lookup"><span data-stu-id="52002-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
    [in] DWORD dwThreadId,  
    [out] ICorDebugThread **ppThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52002-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="52002-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="52002-106">진행 검색할 스레드의 OS 스레드 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="52002-106">[in] The OS thread ID of the thread to be retrieved.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="52002-107">제한이 스레드를 나타내는 ICorDebugThread 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="52002-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52002-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="52002-108">Requirements</span></span>  
 <span data-ttu-id="52002-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52002-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52002-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="52002-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="52002-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52002-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52002-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52002-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
