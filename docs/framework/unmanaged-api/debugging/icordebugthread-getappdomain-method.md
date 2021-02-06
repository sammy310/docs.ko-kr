---
description: '자세히 알아보기: ICorDebugThread:: GetAppDomain 메서드'
title: ICorDebugThread::GetAppDomain 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetAppDomain
helpviewer_keywords:
- GetAppDomain method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetAppDomain method [.NET Framework debugging]
ms.assetid: 415b3d34-8b35-4b60-a318-140646cc83f8
topic_type:
- apiref
ms.openlocfilehash: 416ab80fa08786fb5e95776b164723317fa59ca6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659207"
---
# <a name="icordebugthreadgetappdomain-method"></a><span data-ttu-id="0d2fc-103">ICorDebugThread::GetAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="0d2fc-103">ICorDebugThread::GetAppDomain Method</span></span>

<span data-ttu-id="0d2fc-104">이 ICorDebugThread 현재 실행 중인 응용 프로그램 도메인에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0d2fc-104">Gets an interface pointer to the application domain in which this ICorDebugThread is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d2fc-105">구문</span><span class="sxs-lookup"><span data-stu-id="0d2fc-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d2fc-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0d2fc-106">Parameters</span></span>  

 `ppAppDomain`  
 <span data-ttu-id="0d2fc-107">제한이 이 스레드가 현재 실행 중인 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0d2fc-107">[out] A pointer to an ICorDebugAppDomain object that represents the application domain in which this thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d2fc-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0d2fc-108">Requirements</span></span>  

 <span data-ttu-id="0d2fc-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d2fc-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d2fc-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d2fc-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d2fc-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d2fc-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d2fc-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d2fc-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
