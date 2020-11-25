---
title: PutMethod 함수 (관리 되지 않는 API 참조)
description: PutMethod 함수는 메서드를 만듭니다.
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
ms.openlocfilehash: 8edbb8074573b98c017f98197d370c2ad37db80c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726758"
---
# <a name="putmethod-function"></a><span data-ttu-id="1bab7-103">PutMethod 함수</span><span class="sxs-lookup"><span data-stu-id="1bab7-103">PutMethod function</span></span>

<span data-ttu-id="1bab7-104">메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1bab7-104">Creates a method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="1bab7-105">구문</span><span class="sxs-lookup"><span data-stu-id="1bab7-105">Syntax</span></span>  
  
```cpp  
HRESULT PutMethod (
   [in] int                vFunc,
   [in] IWbemClassObject*  ptr,
   [in] LPCWSTR            wszName,
   [in] LONG               lFlags,
   [in] IWbemClassObject*  pInSignature,
   [in] IWbemClassObject*  pOutSignature
);
```  

## <a name="parameters"></a><span data-ttu-id="1bab7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1bab7-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="1bab7-107">진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1bab7-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="1bab7-108">진행 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1bab7-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="1bab7-109">진행 만들 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1bab7-109">[in] The name of the method to create.</span></span>

`lFlags`  
<span data-ttu-id="1bab7-110">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bab7-110">[in] Reserved.</span></span> <span data-ttu-id="1bab7-111">이 매개 변수는 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bab7-111">This parameter must be 0.</span></span>

`pSignatureIn`  
<span data-ttu-id="1bab7-112">진행 메서드에 대 한 매개 변수를 포함 하는 [__Parameters 시스템 클래스](/windows/desktop/WmiSdk/--parameters) 의 복사본에 대 한 포인터입니다 `in` .</span><span class="sxs-lookup"><span data-stu-id="1bab7-112">[in] A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `in` parameters for the method.</span></span> <span data-ttu-id="1bab7-113">로 설정 되 면이 매개 변수는 무시 됩니다 `null` .</span><span class="sxs-lookup"><span data-stu-id="1bab7-113">This parameter is ignored if set to `null`.</span></span>  

`pSignatureOut`  
<span data-ttu-id="1bab7-114">진행  메서드에 대 한 매개 변수를 포함 하는 [__Parameters 시스템 클래스](/windows/desktop/WmiSdk/--parameters) 의 복사본에 대 한 포인터입니다 `out` .</span><span class="sxs-lookup"><span data-stu-id="1bab7-114">[in]  A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `out` parameters for the method.</span></span> <span data-ttu-id="1bab7-115">로 설정 되 면이 매개 변수는 무시 됩니다 `null` .</span><span class="sxs-lookup"><span data-stu-id="1bab7-115">This parameter is ignored if set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="1bab7-116">반환 값</span><span class="sxs-lookup"><span data-stu-id="1bab7-116">Return value</span></span>

<span data-ttu-id="1bab7-117">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bab7-117">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1bab7-118">상수</span><span class="sxs-lookup"><span data-stu-id="1bab7-118">Constant</span></span>  |<span data-ttu-id="1bab7-119">값</span><span class="sxs-lookup"><span data-stu-id="1bab7-119">Value</span></span>  |<span data-ttu-id="1bab7-120">설명</span><span class="sxs-lookup"><span data-stu-id="1bab7-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="1bab7-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="1bab7-121">0x80041008</span></span> | <span data-ttu-id="1bab7-122">하나 이상의 매개 변수가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1bab7-122">One or more parameters are not valid.</span></span> |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | <span data-ttu-id="1bab7-123">0x80041043</span><span class="sxs-lookup"><span data-stu-id="1bab7-123">0x80041043</span></span> | <span data-ttu-id="1bab7-124">`[in, out]` *Pinsignature* 와 *poutsignature* 개체에 지정 된 메서드 매개 변수는 서로 다른 한정자를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="1bab7-124">The `[in, out]` method parameter specified in both the *pInSignature* and *pOutSignature* objects have different qualifiers.</span></span>
| `WBEM_E_MISSING_PARAMETER_ID` | <span data-ttu-id="1bab7-125">0x80041036</span><span class="sxs-lookup"><span data-stu-id="1bab7-125">0x80041036</span></span> | <span data-ttu-id="1bab7-126">메서드 매개 변수에 **ID** 한정자의 사양이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1bab7-126">A method parameter is missing the specification of the **ID** qualifier.</span></span> |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | <span data-ttu-id="1bab7-127">0x80041038</span><span class="sxs-lookup"><span data-stu-id="1bab7-127">0x80041038</span></span> | <span data-ttu-id="1bab7-128">메서드 매개 변수에 할당 된 ID 계열이 연속 되지 않거나 0에서 시작 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1bab7-128">The ID series that is assigned to the method parameters is not consecutive or does not start at 0.</span></span> |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | <span data-ttu-id="1bab7-129">0x80041039</span><span class="sxs-lookup"><span data-stu-id="1bab7-129">0x80041039</span></span> | <span data-ttu-id="1bab7-130">메서드의 반환 값에는 **ID** 한정자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bab7-130">The return value for a method has an **ID** qualifier.</span></span> |
| `WBEM_E_PROPAGATED_METHOD` | <span data-ttu-id="1bab7-131">0x80041034</span><span class="sxs-lookup"><span data-stu-id="1bab7-131">0x80041034</span></span> | <span data-ttu-id="1bab7-132">부모 클래스에서 기존 메서드 이름을 다시 사용 하려고 했지만 서명이 일치 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1bab7-132">An attempt was made to reuse an existing method name from a parent class, and the signatures did not match.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="1bab7-133">0</span><span class="sxs-lookup"><span data-stu-id="1bab7-133">0</span></span> | <span data-ttu-id="1bab7-134">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1bab7-134">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="1bab7-135">설명</span><span class="sxs-lookup"><span data-stu-id="1bab7-135">Remarks</span></span>

<span data-ttu-id="1bab7-136">이 함수는 [IWbemClassObject::P utMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="1bab7-136">This function wraps a call to the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

<span data-ttu-id="1bab7-137">이 메서드 호출은 `ptr` 가 CIM 클래스 정의 인 경우에만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bab7-137">This method call is only supported if `ptr` is a CIM class definition.</span></span> <span data-ttu-id="1bab7-138">CIM 인스턴스를 가리키는 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 포인터에서 메서드 조작을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1bab7-138">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="1bab7-139">사용자는 이름이 밑줄로 시작 하거나 끝나는 메서드를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1bab7-139">Users cannot create methods with names that begin or end with an underscore.</span></span> <span data-ttu-id="1bab7-140">이는 시스템 클래스 및 속성에 대해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bab7-140">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="1bab7-141">메서드의 경우 `in` 및 `out` 매개 변수는 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 개체의 속성으로 설명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bab7-141">For a method, the `in` and `out` parameters are described as properties in [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) objects.</span></span>

<span data-ttu-id="1bab7-142">`[in/out]`매개 변수는 `pInSignature` 및 매개 변수에서 가리키는 두 개체에 동일한 속성을 추가 하 여 정의할 수 있습니다 `pOutSignature` .</span><span class="sxs-lookup"><span data-stu-id="1bab7-142">An `[in/out]` parameter can be defined by adding the same property to both objects pointed to by the `pInSignature` and `pOutSignature` parameters.</span></span> <span data-ttu-id="1bab7-143">이 경우 속성은 동일한 **ID** 한정자 값을 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bab7-143">In this case, the properties share the same **ID** qualifier value.</span></span>

<span data-ttu-id="1bab7-144">이외의 [__Parameters](/windows/desktop/WmiSdk/--parameters) 클래스 개체의 각 속성에는 `ReturnValue` 매개 변수가 표시 되는 순서를 식별 하는 0부터 시작 하는 숫자 값인 **ID** 한정자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bab7-144">Each property in a [__Parameters](/windows/desktop/WmiSdk/--parameters) class object other than `ReturnValue` must have an **ID** qualifier, a zero-based numeric value that identifies the order in which the parameters appear.</span></span> <span data-ttu-id="1bab7-145">두 매개 변수가 동일한 **id** 값을 가질 수 없으며 **id** 값을 건너뛸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1bab7-145">No two parameters can have the same **ID** value, and no **ID** value can be skipped.</span></span> <span data-ttu-id="1bab7-146">두 조건 중 하나가 발생 하면 `PutMethod` 함수는를 반환 `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bab7-146">If either condition occurs, the `PutMethod` function returns `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span></span>

## <a name="example"></a><span data-ttu-id="1bab7-147">예제</span><span class="sxs-lookup"><span data-stu-id="1bab7-147">Example</span></span>

<span data-ttu-id="1bab7-148">예제를 보려면 [IWbemClassObject::P utMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) 메서드를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1bab7-148">For an example, see the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="1bab7-149">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1bab7-149">Requirements</span></span>  

 <span data-ttu-id="1bab7-150">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bab7-150">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bab7-151">**헤더:** WMINet_Utils idl</span><span class="sxs-lookup"><span data-stu-id="1bab7-151">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="1bab7-152">**.NET Framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1bab7-152">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bab7-153">참조</span><span class="sxs-lookup"><span data-stu-id="1bab7-153">See also</span></span>

- [<span data-ttu-id="1bab7-154">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="1bab7-154">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
