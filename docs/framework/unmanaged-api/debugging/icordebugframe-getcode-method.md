---
title: ICorDebugFrame::GetCode 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCode
helpviewer_keywords:
- GetCode method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCode method [.NET Framework debugging]
ms.assetid: fbaa0794-a031-4015-8beb-2749e47ac340
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e7a4e8c6fa91ee43c33fe0f99d50bd4b1af4a0fd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481198"
---
# <a name="icordebugframegetcode-method"></a><span data-ttu-id="f2733-102">ICorDebugFrame::GetCode 메서드</span><span class="sxs-lookup"><span data-stu-id="f2733-102">ICorDebugFrame::GetCode Method</span></span>
<span data-ttu-id="f2733-103">이 스택 프레임과 연결 된 코드에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f2733-103">Gets a pointer to the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2733-104">구문</span><span class="sxs-lookup"><span data-stu-id="f2733-104">Syntax</span></span>  
  
```  
HRESULT GetCode (  
    [out] ICorDebugCode      **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2733-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f2733-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="f2733-106">[out] 이 프레임을 사용 하 여 연결 된 코드를 나타내는 ICorDebugCode 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f2733-106">[out] A pointer to the address of an ICorDebugCode object that represents the code associated with this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2733-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f2733-107">Requirements</span></span>  
 <span data-ttu-id="f2733-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f2733-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2733-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f2733-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2733-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2733-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2733-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2733-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
