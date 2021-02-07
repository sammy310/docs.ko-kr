---
description: '자세히 알아보기: ICorDebugEval2:: CreateValueForType 메서드'
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
ms.openlocfilehash: 2a8cd129d6194a4870817eb64b79606c395cb055
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693904"
---
# <a name="icordebugeval2createvaluefortype-method"></a><span data-ttu-id="72457-103">ICorDebugEval2::CreateValueForType 메서드</span><span class="sxs-lookup"><span data-stu-id="72457-103">ICorDebugEval2::CreateValueForType Method</span></span>

<span data-ttu-id="72457-104">초기 값이 0 또는 null 인 지정 된 형식의 새 ICorDebugValue에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="72457-104">Gets a pointer to a new ICorDebugValue of the specified type, with an initial value of zero or null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72457-105">구문</span><span class="sxs-lookup"><span data-stu-id="72457-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72457-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="72457-106">Parameters</span></span>  

 `pType`  
 <span data-ttu-id="72457-107">진행 유형을 나타내는 ICorDebugType 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="72457-107">[in] Pointer to an ICorDebugType object that represents the type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="72457-108">제한이 값을 나타내는 개체의 주소에 대 한 포인터 `ICorDebugValue` 입니다.</span><span class="sxs-lookup"><span data-stu-id="72457-108">[out] Pointer to the address of an `ICorDebugValue` object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72457-109">설명</span><span class="sxs-lookup"><span data-stu-id="72457-109">Remarks</span></span>  

 <span data-ttu-id="72457-110">`CreateValueForType` 일반화 [ICorDebugEval:: CreateValue](icordebugeval-createvalue-method.md) :와 같은 생성 된 형식을 포함 하 여 임의의 개체 형식을 지정할 수 있습니다 `List<int>` .</span><span class="sxs-lookup"><span data-stu-id="72457-110">`CreateValueForType` generalizes [ICorDebugEval::CreateValue](icordebugeval-createvalue-method.md) by allowing you to specify an arbitrary object type, including constructed types such as `List<int>`.</span></span> <span data-ttu-id="72457-111">이 메서드의 유일한 용도는 함수 실행으로 전달 될 수 있는 값을 생성 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="72457-111">The only purpose of this method is to generate a value that can be passed to a function evaluation.</span></span>  
  
 <span data-ttu-id="72457-112">형식은 클래스 또는 값 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72457-112">The type must be a class or a value type.</span></span> <span data-ttu-id="72457-113">이 메서드를 사용 하 여 배열 값 이나 문자열 값을 만들 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="72457-113">You cannot use this method to create array values or string values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72457-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="72457-114">Requirements</span></span>  

 <span data-ttu-id="72457-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="72457-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72457-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72457-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72457-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72457-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72457-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72457-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
