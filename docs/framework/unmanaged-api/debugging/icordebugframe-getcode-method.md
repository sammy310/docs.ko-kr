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
ms.openlocfilehash: 9a4f533c0ab817d800c2d35b7d64c7aee78faaea
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121174"
---
# <a name="icordebugframegetcode-method"></a><span data-ttu-id="bb873-102">ICorDebugFrame::GetCode 메서드</span><span class="sxs-lookup"><span data-stu-id="bb873-102">ICorDebugFrame::GetCode Method</span></span>
<span data-ttu-id="bb873-103">이 스택 프레임과 연결 된 코드에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bb873-103">Gets a pointer to the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb873-104">구문</span><span class="sxs-lookup"><span data-stu-id="bb873-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode (  
    [out] ICorDebugCode      **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb873-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bb873-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="bb873-106">제한이 이 프레임과 연결 된 코드를 나타내는 ICorDebugCode 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bb873-106">[out] A pointer to the address of an ICorDebugCode object that represents the code associated with this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb873-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bb873-107">Requirements</span></span>  
 <span data-ttu-id="bb873-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb873-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb873-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb873-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb873-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb873-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb873-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb873-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
