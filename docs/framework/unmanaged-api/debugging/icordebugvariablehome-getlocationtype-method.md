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
ms.openlocfilehash: 5d33c917ab814083ec2f3a3f3de6bdc264d90b77
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791014"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="c0743-102">ICorDebugVariableHome:: GetLocationType 메서드</span><span class="sxs-lookup"><span data-stu-id="c0743-102">ICorDebugVariableHome::GetLocationType Method</span></span>
<span data-ttu-id="c0743-103">변수의 네이티브 위치 유형을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c0743-103">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0743-104">구문</span><span class="sxs-lookup"><span data-stu-id="c0743-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0743-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c0743-105">Parameters</span></span>  
 `pLocationType`  
 <span data-ttu-id="c0743-106">제한이 변수의 네이티브 위치 형식에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c0743-106">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="c0743-107">자세한 내용은 [VariableLocationType](variablelocationtype-enumeration.md) 열거형을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c0743-107">See the [VariableLocationType](variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0743-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c0743-108">Requirements</span></span>  
 <span data-ttu-id="c0743-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0743-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0743-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0743-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0743-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0743-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0743-112">**.NET Framework 버전:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0743-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0743-113">참조</span><span class="sxs-lookup"><span data-stu-id="c0743-113">See also</span></span>

- [<span data-ttu-id="c0743-114">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c0743-114">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
- [<span data-ttu-id="c0743-115">VariableLocationType 열거형</span><span class="sxs-lookup"><span data-stu-id="c0743-115">VariableLocationType Enumeration</span></span>](variablelocationtype-enumeration.md)
