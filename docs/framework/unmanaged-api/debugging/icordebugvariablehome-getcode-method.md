---
title: 'ICorDebugVariableHome:: GetCode 메서드'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetCode
helpviewer_keywords:
- ICorDebugVariableHome::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: ef002890-4a7b-4a5d-abbf-16c60083f794
topic_type:
- apiref
ms.openlocfilehash: 6f5d99e6dc4290ef69c0a0748fe15ae538e83558
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684228"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="dabc8-102">ICorDebugVariableHome:: GetCode 메서드</span><span class="sxs-lookup"><span data-stu-id="dabc8-102">ICorDebugVariableHome::GetCode Method</span></span>

<span data-ttu-id="dabc8-103">이 [ICorDebugVariableHome](icordebugvariablehome-interface.md) 개체를 포함 하는 "ICorDebugCode" 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dabc8-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dabc8-104">구문</span><span class="sxs-lookup"><span data-stu-id="dabc8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dabc8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dabc8-105">Parameters</span></span>  

 `ppCode`  
 <span data-ttu-id="dabc8-106">제한이 이 [ICorDebugVariableHome](icordebugvariablehome-interface.md) 개체를 포함 하는 "ICorDebugCode" 인스턴스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dabc8-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dabc8-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dabc8-107">Requirements</span></span>  

 <span data-ttu-id="dabc8-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dabc8-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dabc8-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dabc8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dabc8-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dabc8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dabc8-111">**.NET Framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dabc8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dabc8-112">참조</span><span class="sxs-lookup"><span data-stu-id="dabc8-112">See also</span></span>

- [<span data-ttu-id="dabc8-113">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dabc8-113">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
