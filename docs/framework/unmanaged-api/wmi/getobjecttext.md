---
title: GetObjectText 함수 (관리 되지 않는 API 참조)
description: GetObjectText 함수 MOF 구문에서 개체의 텍스트 렌더링을 반환 합니다.
ms.date: 11/06/2017
api_name:
- GetObjectText
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetObjectText
helpviewer_keywords:
- GetObjectText function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d34cb399ac0e8780c442eeb2e95cebfd0a22ca02
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208321"
---
# <a name="getobjecttext-function"></a><span data-ttu-id="e3285-103">GetObjectText 함수</span><span class="sxs-lookup"><span data-stu-id="e3285-103">GetObjectText function</span></span>
<span data-ttu-id="e3285-104">관리 되는 개체 형식 (MOF) 구문에서 개체의 텍스트 렌더링을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e3285-104">Returns a textual rendering of the object in the Managed Object Format (MOF) syntax.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="e3285-105">구문</span><span class="sxs-lookup"><span data-stu-id="e3285-105">Syntax</span></span>  
  
```  
HRESULT GetObjectText (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
); 
```  

## <a name="parameters"></a><span data-ttu-id="e3285-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e3285-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="e3285-107">[in] 이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3285-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="e3285-108">[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="e3285-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="e3285-109">[in] 일반적으로 0입니다.</span><span class="sxs-lookup"><span data-stu-id="e3285-109">[in] Normally 0.</span></span> <span data-ttu-id="e3285-110">경우 `WBEM_FLAG_NO_FLAVORS` (또는 0x1)를 지정 하면 한정자가 전파 하거나 버전 정보 없이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3285-110">If `WBEM_FLAG_NO_FLAVORS` (or 0x1) is specified, qualifiers are included without propagation or flavor information.</span></span>

`pstrObjectText`   
<span data-ttu-id="e3285-111">[out] 에 대 한 포인터를 `null` 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="e3285-111">[out] A pointer to a `null` on entry.</span></span> <span data-ttu-id="e3285-112">반환 시 새로 할당 된 `BSTR` 포함 하는 개체의 MOF 구문 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3285-112">On return, a newly allocated `BSTR` that contains a MOF syntax rendering of the object.</span></span>  

## <a name="return-value"></a><span data-ttu-id="e3285-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="e3285-113">Return value</span></span>

<span data-ttu-id="e3285-114">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="e3285-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e3285-115">상수</span><span class="sxs-lookup"><span data-stu-id="e3285-115">Constant</span></span>  |<span data-ttu-id="e3285-116">값</span><span class="sxs-lookup"><span data-stu-id="e3285-116">Value</span></span>  |<span data-ttu-id="e3285-117">설명</span><span class="sxs-lookup"><span data-stu-id="e3285-117">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="e3285-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="e3285-118">0x80041001</span></span> | <span data-ttu-id="e3285-119">일반 오류가 발생이 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e3285-119">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e3285-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="e3285-120">0x80041008</span></span> | <span data-ttu-id="e3285-121">매개 변수가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e3285-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="e3285-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="e3285-122">0x80041006</span></span> | <span data-ttu-id="e3285-123">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3285-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="e3285-124">0</span><span class="sxs-lookup"><span data-stu-id="e3285-124">0</span></span> | <span data-ttu-id="e3285-125">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e3285-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="e3285-126">설명</span><span class="sxs-lookup"><span data-stu-id="e3285-126">Remarks</span></span>

<span data-ttu-id="e3285-127">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) 메서드.</span><span class="sxs-lookup"><span data-stu-id="e3285-127">This function wraps a call to the [IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) method.</span></span>

<span data-ttu-id="e3285-128">개체에 대 한 모든 정보 하지만 원래 개체를 다시 만들 수 있게 되기를 MOF 컴파일러에 대 한 충분 한 정보만 반환 하는 MOF 텍스트를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3285-128">The MOF text returned does not contain all the information about the object, but only enough information for the MOF compiler to be able to recreate the original object.</span></span> <span data-ttu-id="e3285-129">예를 들어, 부모 클래스 속성 없거나 전파 된 한정자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3285-129">For instance, no propagated qualifiers or parent class properties are included.</span></span>

<span data-ttu-id="e3285-130">다음 알고리즘을 메서드의 매개 변수와의 텍스트를 다시 만드는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3285-130">The following algorithm is used to reconstruct the text of the parameters of a method:</span></span>

1. <span data-ttu-id="e3285-131">매개 변수는 해당 식별자 값 순서 대로 resequenced 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3285-131">Parameters are resequenced in the order of their identifier values.</span></span>
1. <span data-ttu-id="e3285-132">으로 지정 된 매개 변수 `[in]` 고 `[out]` 단일 매개 변수를 결합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3285-132">Parameters that are specified as `[in]` and `[out]` are combined into a single parameter.</span></span>
 
`pstrObjectText` <span data-ttu-id="e3285-133">에 대 한 포인터 여야 합니다는 `null` 함수를 호출할 때는 하지 포인터를 취소할 수 없습니다 때문에 메서드 호출 하기 전에 잘못 된 문자열을 가리키도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3285-133">must be a pointer to a `null` when the function is called; it must not point to a string that is valid before the method call, because the pointer will not be deallocated.</span></span>

## <a name="requirements"></a><span data-ttu-id="e3285-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e3285-134">Requirements</span></span>  
<span data-ttu-id="e3285-135">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e3285-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3285-136">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e3285-136">**Header:** WMINet_Utils.idl</span></span>  
  
 **<span data-ttu-id="e3285-137">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="e3285-137">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e3285-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="e3285-138">See also</span></span>

- [<span data-ttu-id="e3285-139">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="e3285-139">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
