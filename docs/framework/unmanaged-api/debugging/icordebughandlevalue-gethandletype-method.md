---
title: ICorDebugHandleValue::GetHandleType 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue.GetHandleType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue::GetHandleType
helpviewer_keywords:
- GetHandleType method [.NET Framework debugging]
- ICorDebugHandleValue::GetHandleType method [.NET Framework debugging]
ms.assetid: d5e7b12d-835a-4e86-ae2f-d658d4f1c67c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ecc0b46618cd00ba4442e30c23a7b7e950382fee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775696"
---
# <a name="icordebughandlevaluegethandletype-method"></a><span data-ttu-id="be114-102">ICorDebugHandleValue::GetHandleType 메서드</span><span class="sxs-lookup"><span data-stu-id="be114-102">ICorDebugHandleValue::GetHandleType Method</span></span>
<span data-ttu-id="be114-103">이 ICorDebugHandleValue 개체에서 참조 하는 핸들의 종류를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="be114-103">Gets a value that indicates the kind of handle referenced by this ICorDebugHandleValue object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be114-104">구문</span><span class="sxs-lookup"><span data-stu-id="be114-104">Syntax</span></span>  
  
```  
HRESULT GetHandleType (  
    [out] CorDebugHandleType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be114-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="be114-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="be114-106">[out] 이 핸들의 형식을 나타내는 CorDebugHandleType 열거형의 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="be114-106">[out] A pointer to a value of the CorDebugHandleType enumeration that indicates the type of this handle.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be114-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="be114-107">Requirements</span></span>  
 <span data-ttu-id="be114-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="be114-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be114-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be114-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be114-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be114-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be114-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be114-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
