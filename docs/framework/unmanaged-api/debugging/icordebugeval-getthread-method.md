---
title: ICorDebugEval::GetThread 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::GetThread method [.NET Framework debugging]
ms.assetid: 57163b0d-c8a7-44af-9078-e7a895d29f9a
topic_type:
- apiref
ms.openlocfilehash: b985ada09e0e1914c5e60da61a45398fc6098b33
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976281"
---
# <a name="icordebugevalgetthread-method"></a><span data-ttu-id="185ba-102">ICorDebugEval::GetThread 메서드</span><span class="sxs-lookup"><span data-stu-id="185ba-102">ICorDebugEval::GetThread Method</span></span>
<span data-ttu-id="185ba-103">이 계산이 실행 되거나 실행 될 스레드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="185ba-103">Gets the thread in which this evaluation is executing or will execute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="185ba-104">구문</span><span class="sxs-lookup"><span data-stu-id="185ba-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread (  
    [out] ICorDebugThread   **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="185ba-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="185ba-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="185ba-106">제한이 스레드를 나타내는 ICorDebugThread 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="185ba-106">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="185ba-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="185ba-107">Requirements</span></span>  
 <span data-ttu-id="185ba-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="185ba-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="185ba-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="185ba-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="185ba-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="185ba-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="185ba-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="185ba-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
