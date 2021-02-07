---
description: '자세히 알아보기: ICorDebugGenericValue:: GetValue 메서드'
title: ICorDebugGenericValue::GetValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue::GetValue
helpviewer_keywords:
- ICorDebugGenericValue::GetValue method [.NET Framework debugging]
- GetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: 4e95d7cb-144d-4ccf-8a69-d605f4744be2
topic_type:
- apiref
ms.openlocfilehash: 9c8459ce6a9fb59e934b1ebd355aa091a37b2d7b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661066"
---
# <a name="icordebuggenericvaluegetvalue-method"></a><span data-ttu-id="17dee-103">ICorDebugGenericValue::GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="17dee-103">ICorDebugGenericValue::GetValue Method</span></span>

<span data-ttu-id="17dee-104">이 제네릭의 값을 지정 된 버퍼에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="17dee-104">Copies the value of this generic into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17dee-105">구문</span><span class="sxs-lookup"><span data-stu-id="17dee-105">Syntax</span></span>  
  
```cpp  
HRESULT GetValue (  
    [out] void     *pTo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17dee-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="17dee-106">Parameters</span></span>  

 `pTo`  
 <span data-ttu-id="17dee-107">제한이 이 ICorDebugGenericValue 개체가 나타내는 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="17dee-107">[out] A pointer to the value that is represented by this ICorDebugGenericValue object.</span></span> <span data-ttu-id="17dee-108">값은 단순 형식 또는 참조 형식 (즉, 포인터) 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17dee-108">The value may be a simple type or a reference type (that is, a pointer).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17dee-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="17dee-109">Requirements</span></span>  

 <span data-ttu-id="17dee-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="17dee-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17dee-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="17dee-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="17dee-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17dee-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17dee-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17dee-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
