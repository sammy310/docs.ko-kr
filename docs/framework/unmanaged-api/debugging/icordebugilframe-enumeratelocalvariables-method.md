---
title: ICorDebugILFrame::EnumerateLocalVariables 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateLocalVariables
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateLocalVariables
helpviewer_keywords:
- EnumerateLocalVariables method [.NET Framework debugging]
- ICorDebugILFrame::EnumerateLocalVariables method [.NET Framework debugging]
ms.assetid: 1a67fa1b-2419-4cd0-aad4-6f46a0719b4b
topic_type:
- apiref
ms.openlocfilehash: 07331a512dd513a94a7d8c3a8d8b0754d998b94b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131009"
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a><span data-ttu-id="104da-102">ICorDebugILFrame::EnumerateLocalVariables 메서드</span><span class="sxs-lookup"><span data-stu-id="104da-102">ICorDebugILFrame::EnumerateLocalVariables Method</span></span>
<span data-ttu-id="104da-103">이 프레임의 지역 변수에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="104da-103">Gets an enumerator for the local variables in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="104da-104">구문</span><span class="sxs-lookup"><span data-stu-id="104da-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLocalVariables(   
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="104da-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="104da-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="104da-106">제한이 이 프레임의 지역 변수에 대 한 열거자 인 ICorDebugValueEnum 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="104da-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="104da-107">주의</span><span class="sxs-lookup"><span data-stu-id="104da-107">Remarks</span></span>  
 <span data-ttu-id="104da-108">`EnumerateLocalVariables`이 ICorDebugILFrame 개체가 나타내는 호출 프레임에서 사용할 수 있는 지역 변수를 나열할 수 있는 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="104da-108">`EnumerateLocalVariables` gets an enumerator that can list the local variables available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="104da-109">일부 지역 변수가 활성 상태가 아닐 수 있으므로이 목록에는 실행 중인 함수의 모든 지역 변수가 포함 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="104da-109">The list may not include all of the local variables in the running function, because some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="104da-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="104da-110">Requirements</span></span>  
 <span data-ttu-id="104da-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="104da-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="104da-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="104da-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="104da-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="104da-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="104da-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="104da-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
