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
ms.openlocfilehash: c159a175ddd380015cc2dc21637c8b63fd3caea6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137892"
---
# <a name="icordebugfunctiongetlocalvarsigtoken-method"></a><span data-ttu-id="00a5f-102">ICorDebugFunction::GetLocalVarSigToken 메서드</span><span class="sxs-lookup"><span data-stu-id="00a5f-102">ICorDebugFunction::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="00a5f-103">이 ICorDebugFunction 인스턴스가 나타내는 함수의 지역 변수 서명에 대 한 메타 데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="00a5f-103">Gets the metadata token for the local variable signature of the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00a5f-104">구문</span><span class="sxs-lookup"><span data-stu-id="00a5f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVarSigToken (  
    [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00a5f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="00a5f-105">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="00a5f-106">제한이 이 함수에 대 한 지역 변수 시그니처의 `mdSignature` 토큰에 대 한 포인터 이거나,이 함수에 지역 변수가 없는 경우 `mdSignatureNil`입니다.</span><span class="sxs-lookup"><span data-stu-id="00a5f-106">[out] A pointer to the `mdSignature` token for the local variable signature of this function, or `mdSignatureNil`, if this function has no local variables.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00a5f-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="00a5f-107">Requirements</span></span>  
 <span data-ttu-id="00a5f-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00a5f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00a5f-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00a5f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00a5f-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00a5f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00a5f-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00a5f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
