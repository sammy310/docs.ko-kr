---
description: '자세히 알아보기: ICorDebugVariableHome:: GetRegister 메서드'
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
ms.openlocfilehash: c394d455048cf7451b8320ed72a6aa7adfb3518e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790661"
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="083a7-103">ICorDebugVariableHome:: GetRegister 메서드</span><span class="sxs-lookup"><span data-stu-id="083a7-103">ICorDebugVariableHome::GetRegister Method</span></span>

<span data-ttu-id="083a7-104">위치 형식이 인 변수가 포함 된 레지스터 `VLT_REGISTER` 와 위치 형식이 인 변수에 대 한 기본 레지스터를 가져옵니다 `VLT_REGISTER_RELATIVE` .</span><span class="sxs-lookup"><span data-stu-id="083a7-104">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="083a7-105">구문</span><span class="sxs-lookup"><span data-stu-id="083a7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="083a7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="083a7-106">Parameters</span></span>  

 `pRegister`  
 <span data-ttu-id="083a7-107">제한이 의 위치 형식이 있는 변수의 등록을 나타내는 CorDebugRegister 열거형 값 `VLT_REGISTER` 과 위치 형식이 인 변수에 대 한 기본 레지스터입니다 `VLT_REGISTER_RELATIVE` .</span><span class="sxs-lookup"><span data-stu-id="083a7-107">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="083a7-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="083a7-108">Return Value</span></span>  

 <span data-ttu-id="083a7-109">메서드는 다음 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="083a7-109">The method returns the following values:</span></span>  
  
|<span data-ttu-id="083a7-110">값</span><span class="sxs-lookup"><span data-stu-id="083a7-110">Value</span></span>|<span data-ttu-id="083a7-111">설명</span><span class="sxs-lookup"><span data-stu-id="083a7-111">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="083a7-112">변수가 인수가 나타내는 레지스터에 `pRegister` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="083a7-112">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="083a7-113">변수가 레지스터 또는 레지스터 상대 위치에 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="083a7-113">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="083a7-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="083a7-114">Requirements</span></span>  

 <span data-ttu-id="083a7-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="083a7-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="083a7-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="083a7-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="083a7-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="083a7-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="083a7-118">**.NET Framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="083a7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="083a7-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="083a7-119">See also</span></span>

- [<span data-ttu-id="083a7-120">VariableLocationType 열거형</span><span class="sxs-lookup"><span data-stu-id="083a7-120">VariableLocationType Enumeration</span></span>](variablelocationtype-enumeration.md)
- [<span data-ttu-id="083a7-121">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="083a7-121">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
