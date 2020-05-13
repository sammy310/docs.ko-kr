---
title: ICorDebugThread::GetActiveChain 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveChain
helpviewer_keywords:
- ICorDebugThread::GetActiveChain method [.NET Framework debugging]
- GetActiveChain method [.NET Framework debugging]
ms.assetid: f50de1f7-40ef-4949-b542-1d9a61f7bfef
topic_type:
- apiref
ms.openlocfilehash: 70e79378ad8eb2599199a1f7bc57cf530c9b4dd3
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379688"
---
# <a name="icordebugthreadgetactivechain-method"></a><span data-ttu-id="983e5-102">ICorDebugThread::GetActiveChain 메서드</span><span class="sxs-lookup"><span data-stu-id="983e5-102">ICorDebugThread::GetActiveChain Method</span></span>
<span data-ttu-id="983e5-103">이 ICorDebugThread 개체의 활성 (가장 최근) 스택 체인에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="983e5-103">Gets an interface pointer to the active (most recent) stack chain on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="983e5-104">구문</span><span class="sxs-lookup"><span data-stu-id="983e5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveChain (  
    [out] ICorDebugChain **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="983e5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="983e5-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="983e5-106">제한이 스택 체인을 나타내는 ICorDebugChain 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="983e5-106">[out] A pointer to the address of an ICorDebugChain object that represents the stack chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="983e5-107">설명</span><span class="sxs-lookup"><span data-stu-id="983e5-107">Remarks</span></span>  
 <span data-ttu-id="983e5-108">`ppChain`현재 활성 상태인 스택 체인이 없는 경우 매개 변수는 null입니다.</span><span class="sxs-lookup"><span data-stu-id="983e5-108">The `ppChain` parameter is null if no stack chain is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="983e5-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="983e5-109">Requirements</span></span>  
 <span data-ttu-id="983e5-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="983e5-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="983e5-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="983e5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="983e5-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="983e5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="983e5-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="983e5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
