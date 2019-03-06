---
title: ICorDebugModule::GetFunctionFromToken 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetFunctionFromToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetFunctionFromToken
helpviewer_keywords:
- GetFunctionFromToken method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetFunctionFromToken method [.NET Framework debugging]
ms.assetid: 6fe12194-4ef7-43c1-9570-ade35ccf127a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1af0f8f792c856c0b27b4d3d9ff557bcc5fce82
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500072"
---
# <a name="icordebugmodulegetfunctionfromtoken-method"></a><span data-ttu-id="0025a-102">ICorDebugModule::GetFunctionFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="0025a-102">ICorDebugModule::GetFunctionFromToken Method</span></span>
<span data-ttu-id="0025a-103">메타 데이터 토큰이 지정 된 함수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0025a-103">Gets the function that is specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0025a-104">구문</span><span class="sxs-lookup"><span data-stu-id="0025a-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromToken(  
    [in] mdMethodDef methodDef,  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0025a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0025a-105">Parameters</span></span>  
 `methodDef`  
 <span data-ttu-id="0025a-106">[in] `mdMethodDef` 함수의 메타 데이터를 참조 하는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="0025a-106">[in] A `mdMethodDef` metadata token that references the function's metadata.</span></span>  
  
 `ppFunction`  
 <span data-ttu-id="0025a-107">[out] 함수를 나타내는 ICorDebugFunction 인터페이스 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0025a-107">[out] A pointer to the address of a ICorDebugFunction interface object that represents the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0025a-108">설명</span><span class="sxs-lookup"><span data-stu-id="0025a-108">Remarks</span></span>  
 <span data-ttu-id="0025a-109">합니다 `GetFunctionFromToken` 메서드 값을 전달 하는 경우 CORDBG_E_FUNCTION_NOT_IL HRESULT를 반환 합니다 `methodDef` Microsoft 중간 언어 (MSIL) 메서드를 참조 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0025a-109">The `GetFunctionFromToken` method returns a CORDBG_E_FUNCTION_NOT_IL HRESULT if the value passed in `methodDef` does not refer to a Microsoft intermediate language (MSIL) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0025a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0025a-110">Requirements</span></span>  
 <span data-ttu-id="0025a-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0025a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0025a-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0025a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0025a-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0025a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0025a-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0025a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
