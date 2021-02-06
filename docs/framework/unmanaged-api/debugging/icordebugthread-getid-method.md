---
description: '자세히 알아보기: ICorDebugThread:: GetID 메서드'
title: ICorDebugThread::GetID 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetID
helpviewer_keywords:
- ICorDebugThread::GetID method [.NET Framework debugging]
- GetID method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: f1de4584-92df-42f3-9da4-fca03a1c6821
topic_type:
- apiref
ms.openlocfilehash: d089201527da67299b64cdf074bdd331f22375a1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659090"
---
# <a name="icordebugthreadgetid-method"></a><span data-ttu-id="0a21d-103">ICorDebugThread::GetID 메서드</span><span class="sxs-lookup"><span data-stu-id="0a21d-103">ICorDebugThread::GetID Method</span></span>

<span data-ttu-id="0a21d-104">이 ICorDebugThread 활성 부분의 현재 운영 체제 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0a21d-104">Gets the current operating system identifier of the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a21d-105">구문</span><span class="sxs-lookup"><span data-stu-id="0a21d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] DWORD *pdwThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a21d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0a21d-106">Parameters</span></span>  

 `pdwThreadId`  
 <span data-ttu-id="0a21d-107">제한이 스레드의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="0a21d-107">[out] The identifier of the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a21d-108">설명</span><span class="sxs-lookup"><span data-stu-id="0a21d-108">Remarks</span></span>  

 <span data-ttu-id="0a21d-109">운영 체제 식별자는 프로세스를 실행 하는 동안 변경 될 수 있으며 스레드의 다른 부분에 대 한 다른 값일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a21d-109">The operating system identifier can potentially change during execution of a process, and can be a different value for different parts of the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a21d-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0a21d-110">Requirements</span></span>  

 <span data-ttu-id="0a21d-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0a21d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a21d-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0a21d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0a21d-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a21d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a21d-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a21d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
