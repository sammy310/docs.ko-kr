---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad87b6552df25926b5b4184b7884c1d444c4f1be
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769077"
---
# <a name="icordebugthreadgetprocess-method"></a><span data-ttu-id="09e82-102">ICorDebugThread::GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="09e82-102">ICorDebugThread::GetProcess Method</span></span>
<span data-ttu-id="09e82-103">이 ICorDebugThread를 포함 하는 프로세스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="09e82-103">Gets an interface pointer to the process of which this ICorDebugThread forms a part.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09e82-104">구문</span><span class="sxs-lookup"><span data-stu-id="09e82-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09e82-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="09e82-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="09e82-106">[out] 프로세스를 나타내는 ICorDebugProcess 인터페이스 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="09e82-106">[out] A pointer to the address of an ICorDebugProcess interface object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09e82-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="09e82-107">Requirements</span></span>  
 <span data-ttu-id="09e82-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="09e82-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09e82-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="09e82-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="09e82-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09e82-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09e82-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09e82-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
