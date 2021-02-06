---
description: '자세히 알아보기: ICorDebugThread:: GetHandle 메서드'
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
ms.openlocfilehash: 378bb395e56f0fc287a480d67d2047e082d0796f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659103"
---
# <a name="icordebugthreadgethandle-method"></a><span data-ttu-id="1fcbf-103">ICorDebugThread::GetHandle 메서드</span><span class="sxs-lookup"><span data-stu-id="1fcbf-103">ICorDebugThread::GetHandle Method</span></span>

<span data-ttu-id="1fcbf-104">이 ICorDebugThread의 활성 부분에 대 한 현재 핸들을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1fcbf-104">Gets the current handle for the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fcbf-105">구문</span><span class="sxs-lookup"><span data-stu-id="1fcbf-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1fcbf-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1fcbf-106">Parameters</span></span>  

 `phThreadHandle`  
 <span data-ttu-id="1fcbf-107">제한이 이 스레드의 활성 부분에 대 한 핸들 인 HTHREAD에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1fcbf-107">[out] A pointer to an HTHREAD that is the handle of the active part of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1fcbf-108">설명</span><span class="sxs-lookup"><span data-stu-id="1fcbf-108">Remarks</span></span>  

 <span data-ttu-id="1fcbf-109">핸들은 프로세스가 실행 될 때 변경 될 수 있으며 스레드의 다른 부분에 대해 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fcbf-109">The handle may change as the process executes, and may be different for different parts of the thread.</span></span>  
  
 <span data-ttu-id="1fcbf-110">이 핸들은 디버깅 API에서 소유 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fcbf-110">This handle is owned by the debugging API.</span></span> <span data-ttu-id="1fcbf-111">디버거는 사용 하기 전에이를 복제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fcbf-111">The debugger should duplicate it before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fcbf-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1fcbf-112">Requirements</span></span>  

 <span data-ttu-id="1fcbf-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1fcbf-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fcbf-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1fcbf-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1fcbf-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1fcbf-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1fcbf-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fcbf-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
