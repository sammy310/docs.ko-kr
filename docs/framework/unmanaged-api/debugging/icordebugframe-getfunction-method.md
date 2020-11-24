---
title: ICorDebugFrame::GetFunction 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetFunction method [.NET Framework debugging]
ms.assetid: 879d2311-0ff1-4616-a8b3-959ea5868b2e
topic_type:
- apiref
ms.openlocfilehash: 9f9a6238057f56459eb8dca2375da412c3cd569d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690319"
---
# <a name="icordebugframegetfunction-method"></a><span data-ttu-id="6d92e-102">ICorDebugFrame::GetFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="6d92e-102">ICorDebugFrame::GetFunction Method</span></span>

<span data-ttu-id="6d92e-103">이 스택 프레임과 연결 된 코드를 포함 하는 함수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6d92e-103">Gets the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d92e-104">구문</span><span class="sxs-lookup"><span data-stu-id="6d92e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d92e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6d92e-105">Parameters</span></span>  

 `ppFunction`  
 <span data-ttu-id="6d92e-106">제한이 이 스택 프레임과 연결 된 코드를 포함 하는 함수를 나타내는 ICorDebugFunction 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6d92e-106">[out] A pointer to the address of an ICorDebugFunction object that represents the function containing the code associated with this stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d92e-107">설명</span><span class="sxs-lookup"><span data-stu-id="6d92e-107">Remarks</span></span>  

 <span data-ttu-id="6d92e-108">`GetFunction`프레임이 특정 함수와 연결 되어 있지 않으면 메서드가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d92e-108">The `GetFunction` method may fail if the frame is not associated with any particular function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d92e-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6d92e-109">Requirements</span></span>  

 <span data-ttu-id="6d92e-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6d92e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d92e-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d92e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d92e-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d92e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d92e-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d92e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
