---
description: '자세히 알아보기: ICorDebugVariableHome:: GetLocationType 메서드'
title: 'ICorDebugVariableHome:: GetLocationType 메서드'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLocationType
helpviewer_keywords:
- ICorDebugVariableHome::GetLocationType method [.NET Framework debugging]
- GetLocationType method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 88027c55-8ec6-4f1e-a55b-7eefdbbc3515
topic_type:
- apiref
ms.openlocfilehash: 6efe9c045641d162be820961ca75c21a2b8fc14b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728797"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="7db37-103">ICorDebugVariableHome:: GetLocationType 메서드</span><span class="sxs-lookup"><span data-stu-id="7db37-103">ICorDebugVariableHome::GetLocationType Method</span></span>

<span data-ttu-id="7db37-104">변수의 네이티브 위치 유형을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7db37-104">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7db37-105">구문</span><span class="sxs-lookup"><span data-stu-id="7db37-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7db37-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7db37-106">Parameters</span></span>  

 `pLocationType`  
 <span data-ttu-id="7db37-107">제한이 변수의 네이티브 위치 형식에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7db37-107">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="7db37-108">자세한 내용은 [VariableLocationType](variablelocationtype-enumeration.md) 열거형을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7db37-108">See the [VariableLocationType](variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7db37-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7db37-109">Requirements</span></span>  

 <span data-ttu-id="7db37-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7db37-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7db37-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7db37-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7db37-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7db37-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7db37-113">**.NET Framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7db37-113">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7db37-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7db37-114">See also</span></span>

- [<span data-ttu-id="7db37-115">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7db37-115">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
- [<span data-ttu-id="7db37-116">VariableLocationType 열거형</span><span class="sxs-lookup"><span data-stu-id="7db37-116">VariableLocationType Enumeration</span></span>](variablelocationtype-enumeration.md)
