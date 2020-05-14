---
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
ms.openlocfilehash: 8874deede8b46b93df0e298fb3970fa153b51415
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396568"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="4b791-102">ICorDebugVariableHome:: GetLocationType 메서드</span><span class="sxs-lookup"><span data-stu-id="4b791-102">ICorDebugVariableHome::GetLocationType Method</span></span>
<span data-ttu-id="4b791-103">변수의 네이티브 위치 유형을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4b791-103">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b791-104">구문</span><span class="sxs-lookup"><span data-stu-id="4b791-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b791-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4b791-105">Parameters</span></span>  
 `pLocationType`  
 <span data-ttu-id="4b791-106">제한이 변수의 네이티브 위치 형식에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4b791-106">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="4b791-107">자세한 내용은 [VariableLocationType](variablelocationtype-enumeration.md) 열거형을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4b791-107">See the [VariableLocationType](variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b791-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4b791-108">Requirements</span></span>  
 <span data-ttu-id="4b791-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4b791-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b791-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b791-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b791-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b791-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b791-112">**.NET Framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b791-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b791-113">참조</span><span class="sxs-lookup"><span data-stu-id="4b791-113">See also</span></span>

- [<span data-ttu-id="4b791-114">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4b791-114">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
- [<span data-ttu-id="4b791-115">VariableLocationType 열거형</span><span class="sxs-lookup"><span data-stu-id="4b791-115">VariableLocationType Enumeration</span></span>](variablelocationtype-enumeration.md)
