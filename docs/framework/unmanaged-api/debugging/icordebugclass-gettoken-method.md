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
ms.openlocfilehash: 3433f5f69927afb501c2596571f138e3a69fabb6
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894121"
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="19864-102">ICorDebugClass::GetToken 메서드</span><span class="sxs-lookup"><span data-stu-id="19864-102">ICorDebugClass::GetToken Method</span></span>
<span data-ttu-id="19864-103">이 클래스 `TypeDef` 의 정의를 참조 하는 메타 데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="19864-103">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19864-104">구문</span><span class="sxs-lookup"><span data-stu-id="19864-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19864-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="19864-105">Parameters</span></span>  
 `pTypeDef`  
 <span data-ttu-id="19864-106">제한이 이 클래스의 정의 `mdTypeDef` 를 참조 하는 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="19864-106">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19864-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="19864-107">Requirements</span></span>  
 <span data-ttu-id="19864-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19864-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19864-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="19864-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19864-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19864-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19864-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19864-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19864-112">참조</span><span class="sxs-lookup"><span data-stu-id="19864-112">See also</span></span>

- [<span data-ttu-id="19864-113">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="19864-113">Metadata Interfaces</span></span>](../metadata/metadata-interfaces.md)
