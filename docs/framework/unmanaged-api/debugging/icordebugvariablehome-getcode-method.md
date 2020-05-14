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
ms.openlocfilehash: 87d611a7b6e12a9238b00131326e8205778769e6
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396598"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="40442-102">ICorDebugVariableHome:: GetCode 메서드</span><span class="sxs-lookup"><span data-stu-id="40442-102">ICorDebugVariableHome::GetCode Method</span></span>
<span data-ttu-id="40442-103">이 [ICorDebugVariableHome](icordebugvariablehome-interface.md) 개체를 포함 하는 "ICorDebugCode" 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="40442-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40442-104">구문</span><span class="sxs-lookup"><span data-stu-id="40442-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40442-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="40442-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="40442-106">제한이 이 [ICorDebugVariableHome](icordebugvariablehome-interface.md) 개체를 포함 하는 "ICorDebugCode" 인스턴스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="40442-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40442-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="40442-107">Requirements</span></span>  
 <span data-ttu-id="40442-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40442-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40442-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="40442-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40442-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40442-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40442-111">**.NET Framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40442-111">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40442-112">참조</span><span class="sxs-lookup"><span data-stu-id="40442-112">See also</span></span>

- [<span data-ttu-id="40442-113">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40442-113">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
