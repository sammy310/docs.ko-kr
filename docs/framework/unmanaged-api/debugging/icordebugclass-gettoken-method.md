---
title: ICorDebugClass::GetToken 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetToken
helpviewer_keywords:
- GetToken method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetToken method [.NET Framework debugging]
ms.assetid: ee5c848a-eac4-4462-b07a-07ccd76a75df
topic_type:
- apiref
ms.openlocfilehash: 6964c931307a40f384ad8a8e355cab0aad575ec6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125769"
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="bc002-102">ICorDebugClass::GetToken 메서드</span><span class="sxs-lookup"><span data-stu-id="bc002-102">ICorDebugClass::GetToken Method</span></span>
<span data-ttu-id="bc002-103">이 클래스의 정의를 참조 하는 `TypeDef` 메타 데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bc002-103">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc002-104">구문</span><span class="sxs-lookup"><span data-stu-id="bc002-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc002-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bc002-105">Parameters</span></span>  
 `pTypeDef`  
 <span data-ttu-id="bc002-106">제한이 이 클래스의 정의를 참조 하는 `mdTypeDef` 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bc002-106">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc002-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bc002-107">Requirements</span></span>  
 <span data-ttu-id="bc002-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc002-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc002-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bc002-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc002-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc002-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc002-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc002-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc002-112">참조</span><span class="sxs-lookup"><span data-stu-id="bc002-112">See also</span></span>

- [<span data-ttu-id="bc002-113">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bc002-113">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
