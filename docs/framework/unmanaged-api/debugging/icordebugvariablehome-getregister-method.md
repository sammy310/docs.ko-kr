---
title: ICorDebugVariableHome::GetRegister 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetRegister
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetRegister
helpviewer_keywords:
- ICorDebugVariableHome::GetRegister method [.NET Framework debugging]
- GetRegister method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: a5eecd7b-b04c-4266-bff2-7c8771d519a8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 290647f0e0dcaeae53362762ed7f8e0c2f05a82c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993644"
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="7c79c-102">ICorDebugVariableHome::GetRegister 메서드</span><span class="sxs-lookup"><span data-stu-id="7c79c-102">ICorDebugVariableHome::GetRegister Method</span></span>
<span data-ttu-id="7c79c-103">위치 형식의 변수를 포함 하는 레지스터를 가져옵니다 `VLT_REGISTER`, 및 위치 형식의 변수에 대 한 기본 등록 `VLT_REGISTER_RELATIVE`합니다.</span><span class="sxs-lookup"><span data-stu-id="7c79c-103">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c79c-104">구문</span><span class="sxs-lookup"><span data-stu-id="7c79c-104">Syntax</span></span>  
  
```  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c79c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7c79c-105">Parameters</span></span>  
 `pRegister`  
 <span data-ttu-id="7c79c-106">[out] 위치 형식의 변수에 대 한 등록을 나타내는 CorDebugRegister 열거형 값 `VLT_REGISTER`, 및 위치 형식의 변수에 대 한 기본 등록 `VLT_REGISTER_RELATIVE`합니다.</span><span class="sxs-lookup"><span data-stu-id="7c79c-106">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c79c-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="7c79c-107">Return Value</span></span>  
 <span data-ttu-id="7c79c-108">메서드는 다음 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c79c-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="7c79c-109">값</span><span class="sxs-lookup"><span data-stu-id="7c79c-109">Value</span></span>|<span data-ttu-id="7c79c-110">설명</span><span class="sxs-lookup"><span data-stu-id="7c79c-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="7c79c-111">변수가 가리키는 레지스터는 `pRegister` 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="7c79c-111">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="7c79c-112">변수는 등록 또는 등록에 상대적인 위치에 없는 경우</span><span class="sxs-lookup"><span data-stu-id="7c79c-112">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7c79c-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7c79c-113">Requirements</span></span>  
 <span data-ttu-id="7c79c-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7c79c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c79c-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c79c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c79c-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c79c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c79c-117">**.NET Framework 버전:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c79c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c79c-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="7c79c-118">See also</span></span>

- [<span data-ttu-id="7c79c-119">VariableLocationType 열거형</span><span class="sxs-lookup"><span data-stu-id="7c79c-119">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)
- [<span data-ttu-id="7c79c-120">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7c79c-120">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
