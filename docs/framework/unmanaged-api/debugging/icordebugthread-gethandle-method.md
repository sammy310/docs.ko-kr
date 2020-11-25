---
title: ICorDebugThread::GetHandle 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetHandle method [.NET Framework debugging]
ms.assetid: 172ef8c4-2ead-4cfc-bd2e-dee4fb7191cd
topic_type:
- apiref
ms.openlocfilehash: 5debd09f3ca0b4562f62913f9530cc4fa6f9110b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728032"
---
# <a name="icordebugthreadgethandle-method"></a><span data-ttu-id="63ed3-102">ICorDebugThread::GetHandle 메서드</span><span class="sxs-lookup"><span data-stu-id="63ed3-102">ICorDebugThread::GetHandle Method</span></span>

<span data-ttu-id="63ed3-103">이 ICorDebugThread의 활성 부분에 대 한 현재 핸들을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="63ed3-103">Gets the current handle for the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63ed3-104">구문</span><span class="sxs-lookup"><span data-stu-id="63ed3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63ed3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="63ed3-105">Parameters</span></span>  

 `phThreadHandle`  
 <span data-ttu-id="63ed3-106">제한이 이 스레드의 활성 부분에 대 한 핸들 인 HTHREAD에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="63ed3-106">[out] A pointer to an HTHREAD that is the handle of the active part of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63ed3-107">설명</span><span class="sxs-lookup"><span data-stu-id="63ed3-107">Remarks</span></span>  

 <span data-ttu-id="63ed3-108">핸들은 프로세스가 실행 될 때 변경 될 수 있으며 스레드의 다른 부분에 대해 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63ed3-108">The handle may change as the process executes, and may be different for different parts of the thread.</span></span>  
  
 <span data-ttu-id="63ed3-109">이 핸들은 디버깅 API에서 소유 합니다.</span><span class="sxs-lookup"><span data-stu-id="63ed3-109">This handle is owned by the debugging API.</span></span> <span data-ttu-id="63ed3-110">디버거는 사용 하기 전에이를 복제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63ed3-110">The debugger should duplicate it before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63ed3-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="63ed3-111">Requirements</span></span>  

 <span data-ttu-id="63ed3-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="63ed3-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63ed3-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63ed3-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63ed3-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63ed3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63ed3-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63ed3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
