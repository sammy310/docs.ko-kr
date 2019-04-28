---
title: ICorDebugEval2::NewParameterizedObjectNoConstructor 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedObjectNoConstructor
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedObjectNoConstructor
helpviewer_keywords:
- NewParameterizedObjectNoConstructor method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObjectNoConstructor method [.NET Framework debugging]
ms.assetid: f15b5b78-94f4-4eb9-b3b3-a621272f357c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6feef7b1e1f09107cd2a57555df07bebec86effa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667030"
---
# <a name="icordebugeval2newparameterizedobjectnoconstructor-method"></a><span data-ttu-id="435cc-102">ICorDebugEval2::NewParameterizedObjectNoConstructor 메서드</span><span class="sxs-lookup"><span data-stu-id="435cc-102">ICorDebugEval2::NewParameterizedObjectNoConstructor Method</span></span>
<span data-ttu-id="435cc-103">Constructor 메서드를 호출 하려고 하지 않고 지정된 된 클래스의 새 매개 변수가 있는 형식 개체를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="435cc-103">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="435cc-104">구문</span><span class="sxs-lookup"><span data-stu-id="435cc-104">Syntax</span></span>  
  
```  
HRESULT NewParameterizedObjectNoConstructor (  
    [in] ICorDebugClass        *pClass,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="435cc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="435cc-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="435cc-106">[in] 인스턴스화할 수 개체의 클래스를 나타내는 ICorDebugClass 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="435cc-106">[in] A pointer to an ICorDebugClass object that represents the class of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="435cc-107">[in] 형식 인수 수가 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="435cc-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="435cc-108">[in] 포인터의 배열, 각 인스턴스화 중인 개체에 대 한 형식 인수를 나타내는 ICorDebugType 개체를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="435cc-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="435cc-109">설명</span><span class="sxs-lookup"><span data-stu-id="435cc-109">Remarks</span></span>  
 <span data-ttu-id="435cc-110">`NewParameterizedObjectNoConstructor` 메서드 실패 하는 경우 잘못 된 개수의 형식 인수 또는 잘못 된 형식의 형식 인수에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="435cc-110">The `NewParameterizedObjectNoConstructor` method will fail if an incorrect number of type arguments or the wrong types of type arguments are passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="435cc-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="435cc-111">Requirements</span></span>  
 <span data-ttu-id="435cc-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="435cc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="435cc-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="435cc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="435cc-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="435cc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="435cc-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="435cc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
