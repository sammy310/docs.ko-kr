---
title: 'ICorDebugVariableHome:: GetRegister 메서드'
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
ms.openlocfilehash: 7f912f4b13620b567f5aa097604e98112d85f02d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711756"
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="302ef-102">ICorDebugVariableHome:: GetRegister 메서드</span><span class="sxs-lookup"><span data-stu-id="302ef-102">ICorDebugVariableHome::GetRegister Method</span></span>

<span data-ttu-id="302ef-103">위치 형식이 인 변수가 포함 된 레지스터 `VLT_REGISTER` 와 위치 형식이 인 변수에 대 한 기본 레지스터를 가져옵니다 `VLT_REGISTER_RELATIVE` .</span><span class="sxs-lookup"><span data-stu-id="302ef-103">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="302ef-104">구문</span><span class="sxs-lookup"><span data-stu-id="302ef-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="302ef-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="302ef-105">Parameters</span></span>  

 `pRegister`  
 <span data-ttu-id="302ef-106">제한이 의 위치 형식이 있는 변수의 등록을 나타내는 CorDebugRegister 열거형 값 `VLT_REGISTER` 과 위치 형식이 인 변수에 대 한 기본 레지스터입니다 `VLT_REGISTER_RELATIVE` .</span><span class="sxs-lookup"><span data-stu-id="302ef-106">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="302ef-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="302ef-107">Return Value</span></span>  

 <span data-ttu-id="302ef-108">메서드는 다음 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="302ef-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="302ef-109">값</span><span class="sxs-lookup"><span data-stu-id="302ef-109">Value</span></span>|<span data-ttu-id="302ef-110">설명</span><span class="sxs-lookup"><span data-stu-id="302ef-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="302ef-111">변수가 인수가 나타내는 레지스터에 `pRegister` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="302ef-111">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="302ef-112">변수가 레지스터 또는 레지스터 상대 위치에 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="302ef-112">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="302ef-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="302ef-113">Requirements</span></span>  

 <span data-ttu-id="302ef-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="302ef-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="302ef-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="302ef-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="302ef-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="302ef-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="302ef-117">**.NET Framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="302ef-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="302ef-118">참조</span><span class="sxs-lookup"><span data-stu-id="302ef-118">See also</span></span>

- [<span data-ttu-id="302ef-119">VariableLocationType 열거형</span><span class="sxs-lookup"><span data-stu-id="302ef-119">VariableLocationType Enumeration</span></span>](variablelocationtype-enumeration.md)
- [<span data-ttu-id="302ef-120">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="302ef-120">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
