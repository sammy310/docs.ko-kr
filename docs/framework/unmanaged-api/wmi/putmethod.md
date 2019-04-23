---
title: PutMethod 함수 (관리 되지 않는 API 참조)
description: PutMethod 함수 메서드를 만듭니다.
ms.date: 11/06/2017
api_name:
- PutMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutMethod
helpviewer_keywords:
- PutMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99bc65b0181a7c0ab7877273b3747ece91544f99
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59152505"
---
# <a name="putmethod-function"></a><span data-ttu-id="f027a-103">PutMethod 함수</span><span class="sxs-lookup"><span data-stu-id="f027a-103">PutMethod function</span></span>
<span data-ttu-id="f027a-104">메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f027a-104">Creates a method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="f027a-105">구문</span><span class="sxs-lookup"><span data-stu-id="f027a-105">Syntax</span></span>  
  
```  
HRESULT PutMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*  ptr, 
   [in] LPCWSTR            wszName,
   [in] LONG               lFlags,
   [in] IWbemClassObject*  pInSignature,
   [in] IWbemClassObject*  pOutSignature
); 
```  

## <a name="parameters"></a><span data-ttu-id="f027a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f027a-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="f027a-107">[in] 이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f027a-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="f027a-108">[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="f027a-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="f027a-109">[in] 만들려는 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f027a-109">[in] The name of the method to create.</span></span> 

`lFlags`  
<span data-ttu-id="f027a-110">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f027a-110">[in] Reserved.</span></span> <span data-ttu-id="f027a-111">이 매개 변수는 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f027a-111">This parameter must be 0.</span></span>

`pSignatureIn`  
<span data-ttu-id="f027a-112">[in] 복사본에 대 한 포인터를 [__Parameters 시스템 클래스](/windows/desktop/WmiSdk/--parameters) 포함 하는 `in` 메서드의 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="f027a-112">[in] A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `in` parameters for the method.</span></span> <span data-ttu-id="f027a-113">이 매개 변수는 설정 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="f027a-113">This parameter is ignored if set to `null`.</span></span>  

`pSignatureOut`  
<span data-ttu-id="f027a-114">[in]  복사본에 대 한 포인터를 [__Parameters 시스템 클래스](/windows/desktop/WmiSdk/--parameters) 포함 하는 `out` 메서드의 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="f027a-114">[in]  A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `out` parameters for the method.</span></span> <span data-ttu-id="f027a-115">이 매개 변수는 설정 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="f027a-115">This parameter is ignored if set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="f027a-116">반환 값</span><span class="sxs-lookup"><span data-stu-id="f027a-116">Return value</span></span>

<span data-ttu-id="f027a-117">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="f027a-117">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f027a-118">상수</span><span class="sxs-lookup"><span data-stu-id="f027a-118">Constant</span></span>  |<span data-ttu-id="f027a-119">값</span><span class="sxs-lookup"><span data-stu-id="f027a-119">Value</span></span>  |<span data-ttu-id="f027a-120">설명</span><span class="sxs-lookup"><span data-stu-id="f027a-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="f027a-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="f027a-121">0x80041008</span></span> | <span data-ttu-id="f027a-122">하나 이상의 매개 변수가 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f027a-122">One or more parameters are not valid.</span></span> |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | <span data-ttu-id="f027a-123">0x80041043</span><span class="sxs-lookup"><span data-stu-id="f027a-123">0x80041043</span></span> | <span data-ttu-id="f027a-124">`[in, out]` 둘 다 지정 하는 메서드 매개 변수를 *pInSignature* 하 고 *pOutSignature* 개체에 다른 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="f027a-124">The `[in, out]` method parameter specified in both the *pInSignature* and *pOutSignature* objects have different qualifiers.</span></span>
| `WBEM_E_MISSING_PARAMETER_ID` | <span data-ttu-id="f027a-125">0x80041036</span><span class="sxs-lookup"><span data-stu-id="f027a-125">0x80041036</span></span> | <span data-ttu-id="f027a-126">메서드 매개 변수가 지정 된 **ID** 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="f027a-126">A method parameter is missing the specification of the **ID** qualifier.</span></span> |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | <span data-ttu-id="f027a-127">0x80041038</span><span class="sxs-lookup"><span data-stu-id="f027a-127">0x80041038</span></span> | <span data-ttu-id="f027a-128">메서드 매개 변수에 할당 된 ID 시리즈 연속 아니거나 0으로 시작 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f027a-128">The ID series that is assigned to the method parameters is not consecutive or does not start at 0.</span></span> |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | <span data-ttu-id="f027a-129">0x80041039</span><span class="sxs-lookup"><span data-stu-id="f027a-129">0x80041039</span></span> | <span data-ttu-id="f027a-130">메서드에 대 한 반환 값에는 **ID** 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="f027a-130">The return value for a method has an **ID** qualifier.</span></span> |
| `WBEM_E_PROPAGATED_METHOD` | <span data-ttu-id="f027a-131">0x80041034</span><span class="sxs-lookup"><span data-stu-id="f027a-131">0x80041034</span></span> | <span data-ttu-id="f027a-132">부모 클래스에서 기존 메서드 이름을 다시 사용 하려고 하 고 서명이 일치 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f027a-132">An attempt was made to reuse an existing method name from a parent class, and the signatures did not match.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="f027a-133">0</span><span class="sxs-lookup"><span data-stu-id="f027a-133">0</span></span> | <span data-ttu-id="f027a-134">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f027a-134">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="f027a-135">설명</span><span class="sxs-lookup"><span data-stu-id="f027a-135">Remarks</span></span>

<span data-ttu-id="f027a-136">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) 메서드.</span><span class="sxs-lookup"><span data-stu-id="f027a-136">This function wraps a call to the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

<span data-ttu-id="f027a-137">경우에이 메서드 호출은 사용할 `ptr` CIM 클래스 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="f027a-137">This method call is only supported if `ptr` is a CIM class definition.</span></span> <span data-ttu-id="f027a-138">조작 메서드를 사용할 수 없기 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) CIM 인스턴스를 가리키는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f027a-138">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="f027a-139">사용자가 시작 또는 밑줄로 끝나야 하는 이름을 가진 메서드를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f027a-139">Users cannot create methods with names that begin or end with an underscore.</span></span> <span data-ttu-id="f027a-140">이 시스템 클래스 및 속성에 대해 예약 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f027a-140">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="f027a-141">메서드의 경우는 `in` 하 고 `out` 매개 변수에서 속성으로 설명 됩니다 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f027a-141">For a method, the `in` and `out` parameters are described as properties in [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) objects.</span></span>

<span data-ttu-id="f027a-142">`[in/out]` 에서 가리키는 개체를 모두에 동일한 속성을 추가 하 여 매개 변수를 정의할 수 있습니다 합니다 `pInSignature` 및 `pOutSignature` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="f027a-142">An `[in/out]` parameter can be defined by adding the same property to both objects pointed to by the `pInSignature` and `pOutSignature` parameters.</span></span> <span data-ttu-id="f027a-143">이 경우 속성 공유 동일 **ID** 한정자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f027a-143">In this case, the properties share the same **ID** qualifier value.</span></span>

<span data-ttu-id="f027a-144">각 속성을 [__Parameters](/windows/desktop/WmiSdk/--parameters) 개체 이외의 클래스 `ReturnValue` 있어야를 **ID** 한정자, 매개 변수가 나타나는 순서를 식별 하는 0부터 시작 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f027a-144">Each property in a [__Parameters](/windows/desktop/WmiSdk/--parameters) class object other than `ReturnValue` must have an **ID** qualifier, a zero-based numeric value that identifies the order in which the parameters appear.</span></span> <span data-ttu-id="f027a-145">두 매개 변수 없이 동일한 있을 수 있습니다 **ID** 값 및 no **ID** 값을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f027a-145">No two parameters can have the same **ID** value, and no **ID** value can be skipped.</span></span> <span data-ttu-id="f027a-146">두 조건 중 하나가 발생 하는 경우는 `PutMethod` 함수에서 반환 `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`합니다.</span><span class="sxs-lookup"><span data-stu-id="f027a-146">If either condition occurs, the `PutMethod` function returns `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span></span>

## <a name="example"></a><span data-ttu-id="f027a-147">예제</span><span class="sxs-lookup"><span data-stu-id="f027a-147">Example</span></span>

<span data-ttu-id="f027a-148">예를 들어 참조 된 [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) 메서드.</span><span class="sxs-lookup"><span data-stu-id="f027a-148">For an example, see the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="f027a-149">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f027a-149">Requirements</span></span>  
 <span data-ttu-id="f027a-150">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f027a-150">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f027a-151">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="f027a-151">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f027a-152">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f027a-152">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f027a-153">참고자료</span><span class="sxs-lookup"><span data-stu-id="f027a-153">See also</span></span>

- [<span data-ttu-id="f027a-154">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="f027a-154">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
