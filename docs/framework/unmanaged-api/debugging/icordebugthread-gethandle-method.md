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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 900fece1dd29f73f77b85ff08e4deff1396f8aaf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994021"
---
# <a name="icordebugthreadgethandle-method"></a><span data-ttu-id="6562e-102">ICorDebugThread::GetHandle 메서드</span><span class="sxs-lookup"><span data-stu-id="6562e-102">ICorDebugThread::GetHandle Method</span></span>
<span data-ttu-id="6562e-103">이 ICorDebugThread의 활성 부분에 대 한 현재 핸들을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-103">Gets the current handle for the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6562e-104">구문</span><span class="sxs-lookup"><span data-stu-id="6562e-104">Syntax</span></span>  
  
```  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6562e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6562e-105">Parameters</span></span>  
 `phThreadHandle`  
 <span data-ttu-id="6562e-106">[out] 이 스레드의 활성 부분의 핸들 인는 HTHREAD 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-106">[out] A pointer to an HTHREAD that is the handle of the active part of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6562e-107">설명</span><span class="sxs-lookup"><span data-stu-id="6562e-107">Remarks</span></span>  
 <span data-ttu-id="6562e-108">프로세스를 실행 하 고 스레드의 부분 마다 다를 수 핸들을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-108">The handle may change as the process executes, and may be different for different parts of the thread.</span></span>  
  
 <span data-ttu-id="6562e-109">디버깅 API에서이 핸들을 소유 합니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-109">This handle is owned by the debugging API.</span></span> <span data-ttu-id="6562e-110">디버거 사용 하기 전에 복제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-110">The debugger should duplicate it before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6562e-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6562e-111">Requirements</span></span>  
 <span data-ttu-id="6562e-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6562e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6562e-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6562e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6562e-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6562e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6562e-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6562e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
