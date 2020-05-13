---
title: ICorDebugILCode2::GetLocalVarSigToken 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetLocalVarSigToken
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 17665b77-1342-4115-94fd-9f45b0ecfb0f
topic_type:
- apiref
ms.openlocfilehash: 3b9c2f0e20488826aca202b3ef454104964b8bb9
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210347"
---
# <a name="icordebugilcode2getlocalvarsigtoken-method"></a><span data-ttu-id="0f209-102">ICorDebugILCode2::GetLocalVarSigToken 메서드</span><span class="sxs-lookup"><span data-stu-id="0f209-102">ICorDebugILCode2::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="0f209-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="0f209-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="0f209-104">이 인스턴스로 표시되는 함수의 로컬 변수 서명에 대한 메타데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f209-104">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f209-105">구문</span><span class="sxs-lookup"><span data-stu-id="0f209-105">Syntax</span></span>  
  
```cpp
HRESULT GetLocalVarSigToken(  
   [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f209-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0f209-106">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="0f209-107">[out] 이 함수 로컬 변수 서명의 `mdSignature` 토큰에 대한 포인터이거나, 서명이 없으면(함수에 로컬 변수가 없으면) `mdSignatureNil`입니다.</span><span class="sxs-lookup"><span data-stu-id="0f209-107">[out] A pointer to the `mdSignature` token for the local variable signature for this function, or `mdSignatureNil` if there is no signature (that is, if the function doesn't have any local variables).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f209-108">설명</span><span class="sxs-lookup"><span data-stu-id="0f209-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f209-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0f209-109">Requirements</span></span>  
 <span data-ttu-id="0f209-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f209-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f209-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f209-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f209-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f209-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f209-113">**.NET Framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f209-113">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f209-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f209-114">See also</span></span>

- [<span data-ttu-id="0f209-115">ICorDebugILCode2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0f209-115">ICorDebugILCode2 Interface</span></span>](icordebugilcode2-interface.md)
- [<span data-ttu-id="0f209-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0f209-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
