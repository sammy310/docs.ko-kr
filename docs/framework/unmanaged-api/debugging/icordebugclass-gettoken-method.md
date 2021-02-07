---
description: '자세히 알아보기: ICorDebugClass:: GetToken 메서드'
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
ms.openlocfilehash: f87b71800410fc3a95790e6d35cf4bd10a5ce747
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711535"
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="f25cc-103">ICorDebugClass::GetToken 메서드</span><span class="sxs-lookup"><span data-stu-id="f25cc-103">ICorDebugClass::GetToken Method</span></span>

<span data-ttu-id="f25cc-104">`TypeDef`이 클래스의 정의를 참조 하는 메타 데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f25cc-104">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f25cc-105">구문</span><span class="sxs-lookup"><span data-stu-id="f25cc-105">Syntax</span></span>  
  
```cpp  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f25cc-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f25cc-106">Parameters</span></span>  

 `pTypeDef`  
 <span data-ttu-id="f25cc-107">제한이 `mdTypeDef` 이 클래스의 정의를 참조 하는 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f25cc-107">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f25cc-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f25cc-108">Requirements</span></span>  

 <span data-ttu-id="f25cc-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f25cc-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f25cc-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f25cc-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f25cc-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f25cc-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f25cc-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f25cc-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f25cc-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f25cc-113">See also</span></span>

- [<span data-ttu-id="f25cc-114">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f25cc-114">Metadata Interfaces</span></span>](../metadata/metadata-interfaces.md)
