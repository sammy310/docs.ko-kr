---
description: '자세히 알아보기: ICorDebugThread:: GetProcess 메서드'
title: ICorDebugThread::GetProcess 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetProcess
helpviewer_keywords:
- ICorDebugThread::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 163816e7-0739-4566-b3df-cd256be8b8a4
topic_type:
- apiref
ms.openlocfilehash: dac5da30b343ebd17c1b1ebdd6d4cfa38b78f0bd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658940"
---
# <a name="icordebugthreadgetprocess-method"></a><span data-ttu-id="6e963-103">ICorDebugThread::GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="6e963-103">ICorDebugThread::GetProcess Method</span></span>

<span data-ttu-id="6e963-104">이 ICorDebugThread 파트를 구성 하는 프로세스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6e963-104">Gets an interface pointer to the process of which this ICorDebugThread forms a part.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e963-105">구문</span><span class="sxs-lookup"><span data-stu-id="6e963-105">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e963-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6e963-106">Parameters</span></span>  

 `ppProcess`  
 <span data-ttu-id="6e963-107">제한이 프로세스를 나타내는 ICorDebugProcess interface 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6e963-107">[out] A pointer to the address of an ICorDebugProcess interface object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e963-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6e963-108">Requirements</span></span>  

 <span data-ttu-id="6e963-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6e963-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e963-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6e963-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6e963-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e963-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e963-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e963-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
