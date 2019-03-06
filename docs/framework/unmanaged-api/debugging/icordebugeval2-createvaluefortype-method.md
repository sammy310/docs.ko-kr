---
title: ICorDebugEval2::CreateValueForType 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CreateValueForType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CreateValueForType
helpviewer_keywords:
- CreateValueForType method [.NET Framework debugging]
- ICorDebugEval2::CreateValueForType method [.NET Framework debugging]
ms.assetid: ea38ae20-7e0a-427a-be77-d78fae719d82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b27e40618d6128c21e99745ca45e139a9c21c843
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475036"
---
# <a name="icordebugeval2createvaluefortype-method"></a><span data-ttu-id="21174-102">ICorDebugEval2::CreateValueForType 메서드</span><span class="sxs-lookup"><span data-stu-id="21174-102">ICorDebugEval2::CreateValueForType Method</span></span>
<span data-ttu-id="21174-103">초기 값이 0 또는 null을 사용 하 여 지정 된 형식의 새 ICorDebugValue에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="21174-103">Gets a pointer to a new ICorDebugValue of the specified type, with an initial value of zero or null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21174-104">구문</span><span class="sxs-lookup"><span data-stu-id="21174-104">Syntax</span></span>  
  
```  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21174-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="21174-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="21174-106">[in] 형식을 나타내는 ICorDebugType 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="21174-106">[in] Pointer to an ICorDebugType object that represents the type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="21174-107">[out] 주소에 대 한 포인터는 `ICorDebugValue` 값을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="21174-107">[out] Pointer to the address of an `ICorDebugValue` object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21174-108">설명</span><span class="sxs-lookup"><span data-stu-id="21174-108">Remarks</span></span>  
 <span data-ttu-id="21174-109">`CreateValueForType` 일반화 [icordebugeval:: Createvalue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md) 에서 임의 개체 유형을 지정할 수 있으므로 포함 하 여 생성 된 형식을 같은 `List<int>`합니다.</span><span class="sxs-lookup"><span data-stu-id="21174-109">`CreateValueForType` generalizes [ICorDebugEval::CreateValue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md) by allowing you to specify an arbitrary object type, including constructed types such as `List<int>`.</span></span> <span data-ttu-id="21174-110">이 메서드의 유일한 목적은 함수 실행에 전달 될 수 있는 값을 생성 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="21174-110">The only purpose of this method is to generate a value that can be passed to a function evaluation.</span></span>  
  
 <span data-ttu-id="21174-111">형식이는 클래스 또는 값 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21174-111">The type must be a class or a value type.</span></span> <span data-ttu-id="21174-112">배열 또는 문자열 값을 만들려면이 메서드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="21174-112">You cannot use this method to create array values or string values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21174-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="21174-113">Requirements</span></span>  
 <span data-ttu-id="21174-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="21174-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21174-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="21174-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="21174-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21174-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21174-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21174-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
