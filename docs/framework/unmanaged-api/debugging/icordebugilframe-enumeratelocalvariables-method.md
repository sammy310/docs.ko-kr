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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3cc9601105d05740e6db0a41bae521bd9a276d74
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471318"
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a><span data-ttu-id="e5818-102">ICorDebugILFrame::EnumerateLocalVariables 메서드</span><span class="sxs-lookup"><span data-stu-id="e5818-102">ICorDebugILFrame::EnumerateLocalVariables Method</span></span>
<span data-ttu-id="e5818-103">이 프레임에서 로컬 변수에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e5818-103">Gets an enumerator for the local variables in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5818-104">구문</span><span class="sxs-lookup"><span data-stu-id="e5818-104">Syntax</span></span>  
  
```  
HRESULT EnumerateLocalVariables(   
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5818-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e5818-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="e5818-106">[out] 이 프레임에서 로컬 변수의 열거자 인 ICorDebugValueEnum 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e5818-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5818-107">설명</span><span class="sxs-lookup"><span data-stu-id="e5818-107">Remarks</span></span>  
 <span data-ttu-id="e5818-108">`EnumerateLocalVariables` 이 ICorDebugILFrame 개체로 표현 되는 호출 프레임에서 사용할 수 있는 지역 변수를 나열할 수 있는 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e5818-108">`EnumerateLocalVariables` gets an enumerator that can list the local variables available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="e5818-109">목록 포함시킬지 여부 지역 변수의 모든 실행 중인 함수에서 활성 수 없을 수도 그 중 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="e5818-109">The list may not include all of the local variables in the running function, because some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5818-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5818-110">Requirements</span></span>  
 <span data-ttu-id="e5818-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e5818-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5818-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5818-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5818-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5818-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5818-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5818-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
