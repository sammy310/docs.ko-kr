---
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
ms.openlocfilehash: 85cfd7ba648f21721f1a9689843eac232489cb42
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728019"
---
# <a name="icordebugthreadgetid-method"></a><span data-ttu-id="39fd1-102">ICorDebugThread::GetID 메서드</span><span class="sxs-lookup"><span data-stu-id="39fd1-102">ICorDebugThread::GetID Method</span></span>

<span data-ttu-id="39fd1-103">이 ICorDebugThread 활성 부분의 현재 운영 체제 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="39fd1-103">Gets the current operating system identifier of the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39fd1-104">구문</span><span class="sxs-lookup"><span data-stu-id="39fd1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] DWORD *pdwThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39fd1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="39fd1-105">Parameters</span></span>  

 `pdwThreadId`  
 <span data-ttu-id="39fd1-106">제한이 스레드의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="39fd1-106">[out] The identifier of the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39fd1-107">설명</span><span class="sxs-lookup"><span data-stu-id="39fd1-107">Remarks</span></span>  

 <span data-ttu-id="39fd1-108">운영 체제 식별자는 프로세스를 실행 하는 동안 변경 될 수 있으며 스레드의 다른 부분에 대 한 다른 값일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39fd1-108">The operating system identifier can potentially change during execution of a process, and can be a different value for different parts of the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39fd1-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="39fd1-109">Requirements</span></span>  

 <span data-ttu-id="39fd1-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39fd1-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39fd1-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="39fd1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="39fd1-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39fd1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39fd1-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39fd1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
