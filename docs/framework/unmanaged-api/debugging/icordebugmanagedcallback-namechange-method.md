---
title: ICorDebugManagedCallback::NameChange 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.NameChange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::NameChange
helpviewer_keywords:
- ICorDebugManagedCallback::NameChange method [.NET Framework debugging]
- NameChange method [.NET Framework debugging]
ms.assetid: a7018a0e-880e-4b68-b52a-1cd22c7aad62
topic_type:
- apiref
ms.openlocfilehash: 2d8fa00a1a998430a55b913cfa25624246eab967
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788354"
---
# <a name="icordebugmanagedcallbacknamechange-method"></a><span data-ttu-id="fc765-102">ICorDebugManagedCallback::NameChange 메서드</span><span class="sxs-lookup"><span data-stu-id="fc765-102">ICorDebugManagedCallback::NameChange Method</span></span>
<span data-ttu-id="fc765-103">응용 프로그램 도메인 또는 스레드의 이름이 변경 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="fc765-103">Notifies the debugger that the name of either an application domain or a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc765-104">구문</span><span class="sxs-lookup"><span data-stu-id="fc765-104">Syntax</span></span>  
  
```cpp  
HRESULT NameChange (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc765-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fc765-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="fc765-106">진행 이름이 변경 되었거나 이름이 변경 된 스레드를 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fc765-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that either had a name change or that contains the thread that had a name change.</span></span>  
  
 `pThread`  
 <span data-ttu-id="fc765-107">진행 이름이 변경 된 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fc765-107">[in] A pointer to an ICorDebugThread object that represents the thread that had a name change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc765-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fc765-108">Requirements</span></span>  
 <span data-ttu-id="fc765-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc765-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc765-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc765-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc765-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc765-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc765-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc765-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc765-113">참조</span><span class="sxs-lookup"><span data-stu-id="fc765-113">See also</span></span>

- [<span data-ttu-id="fc765-114">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fc765-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
