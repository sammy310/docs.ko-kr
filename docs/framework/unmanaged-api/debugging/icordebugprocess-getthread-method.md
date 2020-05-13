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
ms.openlocfilehash: 081852f91f243c4a979e2969220e71bd10c8c56b
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212889"
---
# <a name="icordebugprocessgetthread-method"></a><span data-ttu-id="0c814-102">ICorDebugProcess::GetThread 메서드</span><span class="sxs-lookup"><span data-stu-id="0c814-102">ICorDebugProcess::GetThread Method</span></span>
<span data-ttu-id="0c814-103">지정 된 OS (운영 체제) 스레드 ID를 포함 하는이 프로세스의 스레드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0c814-103">Gets this process's thread that has the specified operating system (OS) thread ID.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c814-104">구문</span><span class="sxs-lookup"><span data-stu-id="0c814-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
    [in] DWORD dwThreadId,  
    [out] ICorDebugThread **ppThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c814-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0c814-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="0c814-106">진행 검색할 스레드의 OS 스레드 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0c814-106">[in] The OS thread ID of the thread to be retrieved.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="0c814-107">제한이 스레드를 나타내는 ICorDebugThread 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0c814-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c814-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0c814-108">Requirements</span></span>  
 <span data-ttu-id="0c814-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c814-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c814-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c814-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c814-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c814-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c814-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c814-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
