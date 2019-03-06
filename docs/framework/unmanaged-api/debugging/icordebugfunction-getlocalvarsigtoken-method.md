---
title: ICorDebugFunction::GetLocalVarSigToken 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetLocalVarSigToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetLocalVarSigToken
helpviewer_keywords:
- ICorDebugFunction::GetLocalVarSigToken method [.NET Framework debugging]
- GetLocalVarSigToken method [.NET Framework debugging]
ms.assetid: 31e53494-bcc9-4981-91a4-f7e0f02cad48
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a682999c888a93cef94162a8179673c862dc43ce
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476648"
---
# <a name="icordebugfunctiongetlocalvarsigtoken-method"></a><span data-ttu-id="7d1ac-102">ICorDebugFunction::GetLocalVarSigToken 메서드</span><span class="sxs-lookup"><span data-stu-id="7d1ac-102">ICorDebugFunction::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="7d1ac-103">ICorDebugFunction 인스턴스에 의해 표현 되는 함수의 로컬 변수 서명에 대 한 메타 데이터를 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7d1ac-103">Gets the metadata token for the local variable signature of the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d1ac-104">구문</span><span class="sxs-lookup"><span data-stu-id="7d1ac-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVarSigToken (  
    [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d1ac-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7d1ac-105">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="7d1ac-106">[out] 에 대 한 포인터를 `mdSignature` 이 함수의 로컬 변수 서명에 대 한 토큰 또는 `mdSignatureNil`이면이 함수에 로컬 변수가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d1ac-106">[out] A pointer to the `mdSignature` token for the local variable signature of this function, or `mdSignatureNil`, if this function has no local variables.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d1ac-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7d1ac-107">Requirements</span></span>  
 <span data-ttu-id="7d1ac-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7d1ac-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d1ac-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7d1ac-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7d1ac-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d1ac-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d1ac-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d1ac-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
