---
description: '자세히 알아보기: ICorDebugFunction:: GetClass 메서드'
title: ICorDebugFunction::GetClass 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetClass
helpviewer_keywords:
- GetClass method, ICorDebugFunction interface [.NET Framework debugging]
- ICorDebugFunction::GetClass method [.NET Framework debugging]
ms.assetid: 27967230-144f-40d3-9e23-961d0241abd9
topic_type:
- apiref
ms.openlocfilehash: 09049962082bc51cc47a56b0de591a26c2ef93fc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692591"
---
# <a name="icordebugfunctiongetclass-method"></a><span data-ttu-id="5812b-103">ICorDebugFunction::GetClass 메서드</span><span class="sxs-lookup"><span data-stu-id="5812b-103">ICorDebugFunction::GetClass Method</span></span>

<span data-ttu-id="5812b-104">이 함수가 멤버인 클래스를 나타내는 ICorDebugClass 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5812b-104">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5812b-105">구문</span><span class="sxs-lookup"><span data-stu-id="5812b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5812b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5812b-106">Parameters</span></span>  

 `ppClass`  
 <span data-ttu-id="5812b-107">제한이 클래스를 나타내는 개체의 주소에 대 한 포인터 `ICorDebugClass` 이거나,이 함수가 클래스의 멤버가 아닌 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="5812b-107">[out] A pointer to the address of the `ICorDebugClass` object that represents the class, or null, if this function is not a member of a class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5812b-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5812b-108">Requirements</span></span>  

 <span data-ttu-id="5812b-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5812b-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5812b-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5812b-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5812b-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5812b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5812b-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5812b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
