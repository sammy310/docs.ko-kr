---
title: ICorDebugType::GetBase 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetBase
helpviewer_keywords:
- ICorDebugType::GetBase method [.NET Framework debugging]
- GetBase method [.NET Framework debugging]
ms.assetid: f24e1af9-c220-4f79-ae62-4153ec17ea81
topic_type:
- apiref
ms.openlocfilehash: cff527aa7cde6a13667d47d030a0ef7db96ad5ba
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122341"
---
# <a name="icordebugtypegetbase-method"></a><span data-ttu-id="e7184-102">ICorDebugType::GetBase 메서드</span><span class="sxs-lookup"><span data-stu-id="e7184-102">ICorDebugType::GetBase Method</span></span>
<span data-ttu-id="e7184-103">이 `ICorDebugType`나타내는 형식의 기본 형식 (있는 경우)을 나타내는 ICorDebugType에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e7184-103">Gets an interface pointer to an ICorDebugType that represents the base type, if one exists, of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7184-104">구문</span><span class="sxs-lookup"><span data-stu-id="e7184-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7184-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e7184-105">Parameters</span></span>  
 `pBase`  
 <span data-ttu-id="e7184-106">제한이 기본 형식을 나타내는 `ICorDebugType` 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e7184-106">[out] A pointer to the address of an `ICorDebugType` object that represents the base type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7184-107">주의</span><span class="sxs-lookup"><span data-stu-id="e7184-107">Remarks</span></span>  
 <span data-ttu-id="e7184-108">형식에 대 한 기본 형식을 조회 하는 것은 개체 또는 해당 부모 클래스의 모든 필드를 인쇄 하는 등의 일반적인 디버거 기능을 구현 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7184-108">Looking up the base type for a type is useful to implement common debugger functionality, such as printing out all the fields of an object or its parent classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7184-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e7184-109">Requirements</span></span>  
 <span data-ttu-id="e7184-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e7184-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7184-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e7184-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e7184-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7184-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7184-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7184-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
