---
description: '자세히 알아보기: ICorDebugVariableHome:: GetCode 메서드'
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
ms.openlocfilehash: e3ff96816e580fe3cd1cee782dc5bd4166f08a14
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794639"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="49bbc-103">ICorDebugVariableHome:: GetCode 메서드</span><span class="sxs-lookup"><span data-stu-id="49bbc-103">ICorDebugVariableHome::GetCode Method</span></span>

<span data-ttu-id="49bbc-104">이 [ICorDebugVariableHome](icordebugvariablehome-interface.md) 개체를 포함 하는 "ICorDebugCode" 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="49bbc-104">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49bbc-105">구문</span><span class="sxs-lookup"><span data-stu-id="49bbc-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49bbc-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="49bbc-106">Parameters</span></span>  

 `ppCode`  
 <span data-ttu-id="49bbc-107">제한이 이 [ICorDebugVariableHome](icordebugvariablehome-interface.md) 개체를 포함 하는 "ICorDebugCode" 인스턴스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="49bbc-107">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49bbc-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="49bbc-108">Requirements</span></span>  

 <span data-ttu-id="49bbc-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="49bbc-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49bbc-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="49bbc-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49bbc-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49bbc-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49bbc-112">**.NET Framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49bbc-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49bbc-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49bbc-113">See also</span></span>

- [<span data-ttu-id="49bbc-114">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="49bbc-114">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
